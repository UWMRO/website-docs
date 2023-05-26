## `telescope-pi`

The `telescope-pi` computer is a Raspberry Pi located inside the white electronics box in the telescope tube. Currently it provides a small [TCP server](https://github.com/UWMRO/evora-wheel) that controls the filter wheel. The Raspberry Pi is connected over USB to a Phidgets motor controller that moves the filter wheel, and over USB-to-serial to an Arduino that reads the Hall effect sensors that encode the position of the wheel.

| Setting  | Value                    |
| :------- | :----------------------- |
| IP       | 72.233.250.84/26         |
| Hostname | telescope-pi.mro.cwu.edu |
| Gateway  | 72.233.250.65            |
| User     | mrouser                  |
| Password | \<usual-password\>       |

### Software

`telescope-pi` only runs the [evora-wheel](https://github.com/UWMRO/evora-wheel) as a Docker container. The container is configured to always restart. The wheel server can be accessed on port 9999 and accepts the following commands

| Command | Action                                                         |
| :------ | :------------------------------------------------------------- |
| get     | Returns the 0-indexed position of the wheel                    |
| move X  | Moves the wheel to the X position                              |
| home    | Homes the wheel (after homing the wheel will be at position 0) |

After a command has been accepted, the server returns `OK` followed by comma-separated return values, if applicable. For example, `get` will return `OK,5`. If an error occurs, the server will return `ERR,<error-description>` where `<error-description>` is a human-readable description of the error. After a command has been processed, the server always closes the connection to the client.

### Updating and restarting the software

The easiest way to restart the software is power cycle the Raspberry Pi. The server will start again after booting. To update the software or restart it from the command line, ssh to `mrouser@72.233.250.84` and execute `run-wheel`. This will stop the current container, pull for new Docker images, and create a new container that with restart policy `always`.

### Setting up `telescope-pi`

To set up a new `telescope-pi` from scratch, start with a blank micro SD card (16 GB should be enough). Flash the desired OS. The current `telescope-pi` uses the headless server [Raspberry Pi OS 22.04 LTS](https://ubuntu.com/download/raspberry-pi) which can be installed using the [Raspberry Pi Imager](https://www.raspberrypi.com/software/). During this stage you may want to click on the gearbox icon and set up the hostname, enable SSH, and defined the username and password.

You will need to connect the Raspberry Pi with the newly flashed memory card to a router with a DHCP server and determine the assigned IP. With a computer in the same network ssh to the RPi with `ssh mrouser@<assigned-IP>`. Once inside the computer, follow these steps:

1) Set up Docker. Generally follow [these instructions](https://docs.docker.com/engine/install/debian/#install-using-the-repository). Once you have confirmed that `sudo docker run hello-world`, allow the `mrouser` user to access the Docker daemon by doing `sudo usermod -a -G docker mrouser`.

2) Edit `~mrouser/.bashrc` and add the following line at the end

    ```bash
    alias run-wheel='docker stop evora-wheel; docker rm evora-wheel; docker pull ghcr.io/uwmro/evora-wheel:latest && docker run -d -it -p 9999:9999 --name evora-wheel --restart always ghcr.io/uwmro/evora-wheel'
    ```

    This alias will stop the currently running `evora-wheel` container, remove it, pull for a new image of the product, and then run it with restart policy `always` and expose it to port 9999 of the host computer.

3) Log out of the RPi and log in again. Then run `run-wheel`. It should pull a new image and finally run the container. Connecting to the server at this point will fail since it is not connected to the filter wheel.

4) Change the network configuration. Edit the file `/etc/dhcpcd.conf` and add the following at the bottom

    ```bash
    interface eth0
    static ip_address=72.233.250.84/26
    static routers=72.233.250.65
    static domain_name_servers=8.8.8.8 8.8.4.4
    ```

    Note that once you restart the RPi with this configuration you won't be able to access it again unless you're at MRO or you configure a network in the 72.233.250.0/26 range.
