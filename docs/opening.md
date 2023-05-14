# Opening checklist

* Log the level of the water tank. The water tank is located down the stairs heading toward the bedrooms, in the utility room on the right. The light to this room is (most inconveniently!) located on the left side of the doorway. Measure the water level by opening the valve to the gauge marked "in. H2O", which is located just above the water pump. The clear tubing will also match the level in the tank. Navigate to the Log page, click the "New post" button, and start the log entry for your trip.

* Measure the water level each day and refill if the tank goes below 1/4 of the way full; instructions for filling the tank are taped to the front of the tank itself. At the end of your trip finalize your log entry and compute how much water your group used.

* Prepare the water system. Turn on the water pump with circuit breaker 8 on panel M. Flush both toilets, which helps avoid the dreaded sewer backup! Check the level of the water tank on a daily basis so as to avoid the (also dreaded) low water alarm. Do not turn on the water heater.

* Prepare heat and air conditioning. Each room on the north side of the observatory has a thermostat for heat. The thermostats for the day room and the bedrooms have both a temperature set point and an on/off switch on the side. The thermostats should be off when no one is at the observatory. If you need heat, turn the thermostat on (if necessary) and set the heat to your liking. If the daytime outside temperature is above about 85 degrees you can turn on the air conditioner. Uncover the vents in the covered area on the outside of the building (just north of the main entrance) and then turn on the AC circuit breakers. Remember to replace the covers before you leave MRO.

* Prime the foot pump. Open the sink cabinet, place the tubing into the blue jug.

* Prepare the camera. Navigate to this IP address. Connect to the camera, set the camera temperature to -82 degrees, and press Cool. It should take approximately ten minutes for the camera to indicate this temperature, but possibly half an hour till it's stable.

* Setup the Filter Wheel. In Evora, connect to the filter wheel, and then press Home. Ensure your directory follows Home > name of your first filter. If the filter status in the bottom right corner says "FAILED", press the Home button again.

* Initialize the Telescope. Launch Bifrost, click Initialize Telescope Systems, and confirm that the control room paddle is set to 'set' (not slew). In the dome turn on the telescope with the key on the RA skirt. Check that four green LED lights illuminate in the telescope's mount. One is the Xbox receiver for the dome paddle, but three of them indicate functioning of the telescope motor drives. If one or more of these LEDs are red, turn off the telescope and restart the Bifrost software. Do not proceed to the next step until all LED lights in the telescope pier are green.

* Confirm that the telescope is at the zenith. If the telescope has been properly parked, it is pointed at zenith. If you're not sure, use the bubble level and the hand paddle to bring to telescope to zenith. Resist the urge to make small adjustments--if the telescope appears to be very near zenith, it was almost certainly properly parked! ONLY correct for gross offsets, as you will more finely tune the pointing at a later stage. After you have confirmed that the telescope is pointed at zenith, click the Load Zenith Coordinates button and then Update Telescope Coordinates. This will update the telescope's RA to the LST, and its DEC to the latitude of MRO: 46:57:04.2.

* Open the dome at about sunset. From the power unit in the northeast corner of the dome, plug the upper shutter power cable (round end) into the appropriate socket located below the dome motor; you will need to rotate the plug, as well as rotate its locking ring to fully seal it into position. Once it is connected, push and hold the upper shutter control switch to open the upper door. After the upper shutter has moved a few inches, you can open the lower shutter by plugging in its (standard 3-prong) power cord and pushing on the lower shutter power switch located on the righthand side of the dome motor until the lower shutter is fully deployed. Unplug the 3-prong power cord when the lower half is fully deployed. The upper shutter will stop automatically, at which point you can unplug its power cord. Restow the cables using the carabiners attached to each power cord. Each of the carabiners should snap onto the U bracket which is mounted above the dome shutter motor -- make sure the plugs don't hang down, otherwise they might get caught as the dome rotates.

* Remove the telescope covers. First, confirm that the telescope is pointing at the zenith and that the Current RA and DEC in Bifrost are correct, then move the telescope to cover position with the Slew to Cover Position button. Make sure the data cables are free to move before moving the telescope. ALWAYS watch the lines when moving the telescope!!! Use the ladder on the southeast end of the dome floor to remove the cover to the main telescope, as well as the 6" finder on the east side of the telescope. Store both covers on the table south of the telescope pier.

* Take bias exposures. A bias exposure at this time will verify that the camera has cooled down and is functioning properly. If all is well, continue.

* Take twilight flats. Move the telescope approximately 20 degrees east of the zenith (west for morning flats).

* Fine tune the telescope pointing. Load the list of bright stars for pointing ("pointing_stars.txt") in Bifrost, select your target, turn on tracking, slew, and then center the star in your field of view. Update the telescope's pointing with the Update Pointing to Target button. If the telescope was not parked properly, or the zenith was not set properly, your target may not appear in the camera's field of view initially. If this happens, use the 6" finder telescope on the east side of the telescope to center the star so that you can image it with your camera. Then center the star and update pointing as described above.

* Focus the telescope on a faint star. Use the finder to find a dimmer star. Once you have found a focus position that minimizes the apparent size of the PSF of your stars, set the telescope's focus to that position. Note that as the temperature changes over the course of the night, the best focus position will also change, which may necessitate a refocusing of the instrument.

* Take your images. Remember to watch the lines when slewing, and go outside and check the sky on a regular basis.

* At the end of the night, shutdown the camera and close Evora. Select Stop in Evora's Temperature Controls. Once the temperature has warmed to above 0 C, press Camera Menu > Shutdown, Filter menu > Disconnect, and close the Evora window.

* Cover and park the telescope. Use the Slew to Cover Position button and carefully replace the telescope covers, then press Park Telescope to move the telescope back to the parked (zenith) position.

* Turn off the telescope and close Bifrost. The key is on the telescope skirt. Then simply close the Bifrost.

* Close the dome. Use the hand control paddle to rotate the dome to its home position. Plug in both cables and close the shutters. The lower shutter must be fully closed before the upper shutter reach it. The upper shutter will stop automatically when it's fully closed. Unplug both cables.
