# Cessna 208B Improvement Mod for Microsoft Flight Simulator

A community mod for the Cessna 208B Grand Caravan, which aims to fix many of the issues present in the stock version.
Feel free to contribute to this mod! Create an issue or fork and create a pull request! Discussion about this mod takes place in the [official forum](https://forums.flightsimulator.com/t/c208b-grand-caravan-ex-mods-general/322172?u=magrainaone)

**The mod isn't working?** This is usually due to a conflict with another mod in the community folder. The best thing is to remove all other mods and then add them one by one to see what causes the conflict. If you think that you found the legitimate bug or something that is missing, please describe and submit it at https://github.com/SheepCreativeSoftware/msfs2020-C208-Improvment-Mod/issues. With the exact reproduction scenario. Saying that feature A does not work, usually is not enough to reproduce and fix the issue. 

**Based on Sim version 1.29.30.0 (SU11)**

***Engine and Flight Model***
- Corrected Different Values according to POH
- Reverse thrust is strengthened and has a noticeable effect on the plane
- 4 minutes of engine overstress (operating above max torque limit) causes the CAS message about metal chips in the oil and increases the probability of engine failure.
The average time of engine failure after metal chips appearance is 100 minutes. The event is random so you may not experience engine failure if you are gentle with the throttle.
If the engine is kept overstressed the probability of engine failure increases. Each second of keeping the engine above the torque limit decreases the expected engine failure time by 8 seconds.  
You can disable/enable engine failures in the MSFS Assistance Options.

***Aircraft Handling***
- More control while taxiing, tighter turning circle
- the throttle lever has been improved and can work in two modes: <br>_normal mode_ - where the controller axis moves the throttle lever from idle position to full power. It is the default mode set during the first load of the aircraft. <br>_expert mode_ - where the controller axis allows to set the throttle lever from full reverse through idle position to full power. The idle position is in the middle and it has a small range of dead zone implemented that makes the throttle stick to the idle position for a small range of controller input. That  helps to set the idle position without too much struggle.<br>
  You can change the throttle lever mode by assigning a button to the THROTTLE REVERSE THRUST TOGGLE event. The throttle selected mode of the throttle is remembered between flights.
- The emergency power lever has been implemented in a simplified way. When used it overrides all throttle settings. Regular throttle is having no effect until the Emergency power lever is set back to normal position.

***Systems & Avionics***
- Works with Stock G1000 and WT G1000 NXi Avionics
- Added CAS annunciations, Systems Page, improved engine readouts, fuel indication
- The cruize torque bug does not longer disappear for RPMS slightly above 1900 
- Avionics Reversionary Mode Enabled
- Additional Voice Alerts
- Autopilot and instrument fixes
- Yaw Damper Working
- More accurate start-up

***Electric System***
- The electric system of Cessna has been modified to reflect the real aircraft configuration. The battery is connected to an always-hot battery bus. The Master Battery Switch disconnects the battery bus from the main power distribution bus of the aircraft.
- Interior cabin lights are connected directly to the battery bus and are powered independently of the master battery switch position. A pilot can switch on the cabin lights and there should be enough ambient light in the cockpit to operate without a torch.
- Cessna is equipped with a combined started-generator unit. The unit works in starter mode if the engine is below 46% Ng, and in generator mode for Ng above 46%. The generator is connected to the power distribution bus of the aircraft through a contactor. The gen switch allows disconnecting the generator's contactor if required by emergency procedure or to check the operation of the standby alternator during the runup.
- The startup switch allows the initiation of the engine startup procedure. The start switch operates only if the engine is below 46% Ng, if the engine operates above 46% the starter switch does not interact with any aircraft systems. Putting it to the start position powers the engine igniters, disconnects the generator contractor, and powers the engine starter. The starter is disabled automatically when the engine reaches 46% Ng. After reaching stable engine operation pilot can put the starter switch to the off position. It disables the ignition system and connects the generator contractor.
- The starter is one of the most power-demanding components on the aircraft. The battery provides the power to start the engine in most realistic scenarios. The current drawn by the starter depends on the external temperature. For temperatures below -20C the starter takes 3500W while above 20C the consumption drops to 2500W. The minimum voltage required to run the starter is 24V.
- The Mod improves the battery, generator, and stand-by alternator current indications on PFD/MFD. A negative value of the battery current indicates that the battery is discharging. A positive battery current means the battery is charging. The charging current is dependent on the battery current capacity. The indicated charging current decreases to zero with the battery reaching full capacity. However, for simplicity, the charging time is not adequate and is usually much shorter.
- All knobs used to regulate the light intensity also impact the light current consumption. The dimmer the light the less current is drawn from the battery or generators.

***Anti Ice System***  Alpha state - testing needed
- Anti Ice system has been extended. The Cessna simulates the existence of the fluid-based anti-ice system which is distributed over an aircraft body to prevent or minimize ice formation.
- The tank for anti-ice fluid can hold 20.8 gallons of the liquid and its level can be monitored on PFD/MFD below other engine parameters
- Anti ice system can be put to normal, high, and max anti-ice mode which gradually increases the amount of anti-ice fluid distribution. The first switch allows putting the system into Normal or High mode. Max flow can be enabled by a spring-loaded momentary switch. It works for 120 seconds and then the system returns to either normal or high mode. Similarly, the Windshield switch allows to enables the distribution of anti-ice fluid on the front glass. Unlike in a real airplane, the windshield anti-ice system works for 120 seconds when triggered.
- In the norm and high anti-ice mode, the anti-ice fluid pumps work in cycles of 10 seconds on followed by 10 seconds off. In high icing conditions, putting the anti-ice system does not affect the aircraft. It is to simulate the need of switching the icing to high mode. The high icing condition area has been presented below on the chart as gray area. In the Max flow mode, the system operates continuously consuming most anti-ice fluid per minute.
- In case of failure of the primary system, the backup switch allows using of a backup pump. If the backup switch is turned on the two primary anti-ice switches do not affect the aircraft. The system works in high mode with the additional distribution of fluid on the windshield.
- because of the simulator limitation, the anti-ice system cannot work only using electric power. Anti-ice system will work only when the engine is running.
![image](https://user-images.githubusercontent.com/27411874/153745793-37f19d22-9daf-4f3b-ab1e-8e6420392ac3.png)
https://www.researchgate.net/publication/269212570_Overview_and_risk_assessment_of_icing_for_transport_category_aircraft_and_components
- In high icing condition stall sensor can become inoperational if not heated. After 5 minutes of ice accumulation, the stall sensor either silently stops operating or becomes permanently triggered. The way it fails is random each time. After failure, the only way of recovery is to enable the stall sensor heater. Melting down the ice does not happen immediately, it takes between 60 - 120 seconds for the stall sensor to become operational again depending on the amount of ice accumulated on the sensor.

***Miscellaneous***
- Improved lighting and textures
- All panel potentiometers work
- Added some inoperative Switches
- Fixed Cabin lights

Based on the work of [C208-MSFS2020-Fix](https://github.com/Exp232/C208-MSFS2020-Fix), [msfs2020-C208-Improvment-Mod](https://github.com/SheepCreativeSoftware/msfs2020-C208-Improvment-Mod) and [dgtlanlg/C208B-mod](https://github.com/dgtlanlg/C208B-mod)

Thanks to everyone who has contributed, and to PilotTrev for sharing his knowledge and first-hand experience.

----

## Known Issues and Limitations
- Anti Ice fluid is refilled only at the start of the new flight
- If your garmin screen is dark use avionics knob to turn the brightness up

----

## Compatibility
- Users are recommended to use the mod together with **Working Title's G1000 NXi** (available on Sim Marketplace).
- The mod was not tested with VR at all. The compatibility with VR si unknown.
- Not compatible (not tested) with other mods which modify the C208 Grand Caravan EX

----

## Download

***[Latest Release v2212.2](https://github.com/SheepCreativeSoftware/msfs2020-C208-Improvment-Mod/releases/latest)***

### How to install

1. Delete any previous versions.
2. Extract the Zip Archive
3. Copy the "C208B-mod" folder into the Community Folder.

----

## License
Microsoft Flight Simulator © Microsoft Corporation.  
Cessna 208B Grand Caravan EX Improvement Mod was created under Microsoft's "[Game Content Usage Rules](https://www.xbox.com/en-US/developers/rules)" using assets from Microsoft Flight Simulator and it is not endorsed by or affiliated with Microsoft.
