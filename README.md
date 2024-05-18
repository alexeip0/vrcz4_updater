# vrcz4_updater
Home Assistant script to update Leviton VRCZ4[-Mx] controllers

Setup:

1. Create new script "UpdateLevitonControllers" and paste there content of update_contollers_script.yaml
   - modify 'deb_db' variable at the top of the script per instructions there.

2. Create new script "UpdateLevitonLEDs" and paste there content of update_leds_script.yaml

3. Create new automation "Controller Activation" and paste there content of controller_automation.yaml
   - fix up device_ids and/or add more scene_activation triggers using UI

4. Create new automation "Switch Activation" and paste there content of switch_automation.yaml
   - fix up device_ids/entity_ids and/or add more switches/light triggers using UI
