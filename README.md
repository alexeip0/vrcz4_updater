# vrcz4_updater
Home Assistant scripts to manage Leviton VRCZ4[-Mx] controllers.

**Supported features:**

- associating the same switch/light with different controllers
- LED indicators reflect the state of the associated load (Green - on, Off -off)
- Up/Down buttons control the intensity of the last load triggered on this controller
  (only if the load is of a light-type)
  
**Z-Wave Configuration:**

For each VRCZ4 controller configure the following settings in Zwave JS UI:

1. Make sure all 4 groups point to your primary Zwave controller.
   
   _Controller(Nook)_ in the example below.

   This seems to be default for VRCZ4 controllers, but has to be done manually for VRCZ4-Mx ones.
   
![vrcz4-groups](https://github.com/alexeip0/vrcz4_updater/assets/32853933/e204dcb2-7e31-4b98-8be6-6e54ac344b2e)

2. Make sure all 8 _Associated Scene IDs_ are assigned corresponding number,
   i.e. Associated Scene ID(x) -> x
   
![vrcz4-scene-config](https://github.com/alexeip0/vrcz4_updater/assets/32853933/6a77b1df-5467-42ff-8e93-f29159196d25)

**Installation:**

The following assumes you have figured out <device_id> of your controllers and <device_id>/<entity_id> of your lights/switches.
Various ways of doing this are listed [here](https://community.home-assistant.io/t/device-id-entity-id-where-to-find/289230/11) (easiest, imo, creating a new dummy automation and viewing it as YAML).

1. Create new script "UpdateLevitonControllers" and paste there content of update_contollers_script.yaml
   - modify 'dev_db' variable at the top of the script per instructions there.
   - for every controller device_id that you specified in 'dev_db' create input_number named
     'input_number.<device_id>' with initial value of 0, maximum value of 3, step 1

2. Create new script "UpdateLevitonLEDs" and paste there content of update_leds_script.yaml

3. Create new script "SwitchTurnOn" and paste there content of switch_turn_on_script.yaml

4. Create new script "SwitchTurnOff" and paste there content of switch_turn_off_script.yaml

5. Create new automation "Controller Activation" and paste there content of controller_automation.yaml
   - fix up device_ids and/or add more scene_activation triggers using UI
     (you should have one trigger for every controller you specified in 'dev_db' above)

6. Create new automation "Switch Activation" and paste there content of switch_automation.yaml
   - fix up device_ids/entity_ids and/or add more switches/light triggers using UI
     (you should have one trigger for every switch/light you specified in 'dev_db' above)

7. Create new automation "Controller Level" and paste there content of controller_level_automation.yaml
