# vrcz4_updater
Home Assistant script to update Leviton VRCZ4[-Mx] controllers

Setup:

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
