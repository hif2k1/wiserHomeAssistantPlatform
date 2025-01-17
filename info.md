[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg)](https://github.com/custom-components/hacs)

{% if prerelease %}
### Please note: This is a Beta version and may have some instabilities.
{% endif %}

{% if installed and version_installed.replace("v", "").0 | int < 3  %}
  ## v3 Upgrade Warning
  This upgrade contains a high number of breaking changes from v2.x.  Please read the [Updating to v3.0](https://github.com/asantaga/wiserHomeAssistantPlatform/tree/master#updating-to-v30---important-please-read) documentation before proceeding.

{% endif %}

This integration allows visibility and control of the Drayton Wiser system in Home Assistant. For information about how to configure and the features included in the integration, please see the [Readme.md](https://github.com/asantaga/wiserHomeAssistantPlatform/blob/master/Readme.Md)


## Functionality 

- Support for [Home Assistant Component Store](https://community.home-assistant.io/t/custom-component-hacs/121727)

- Support for hub discovery and UI config.  No YAML editing.

- Support for multiple hubs
- Support for Wiser Hub, iTRVs, Roomstats, Heating Actuators and SmartPlugs
- Basic sensor support for Dimmable Lights and Shutters

- **Hub (System) Device**
    - Various switches to control hub settings (Away Mode, Comfort Mode, Daylight Saving, Eco Mode, Valve Protection)
    - Button to boost all rooms (time and temp in config)
    - Button to cancel all overrides   
    - Slider to set Away Mode target temperature
    - Sensors for Cloud status, Heating on/off, Heating mode (Normal, Away), Wifi signal.
    - Long Term Statistics sensor for Heating Channel demand % 
    - Many attributes available
    - Heating Operation Mode sensor has attributes to monitor update status

- **Climate Devices**
    - Climate entities for each Room
    - Supports iTRVs, Roomstats and Heating Actuators (for electric heating)
    - Animated icons for the Rooms to let you know which rooms are actually being heated (credit @msp1974)
    - Allows setting of heat mode (Auto, Heat/Manual, Off)
    - Allows setting of temperatures from HA
    - Allows setting of boost temperature using Home Assistant Presets
    - Climate card shows countdown of boost time
    - Allows advancing schedule
    - Allows setting Window Detection
    - Long Term Stats sensors for Target Temp, Current Temp and Demand
    - Many attributes available
    - Fires wiser_room_heating_status_changed event when room starts or stops heating

- **Hot Water**
    - Sensor to show if hot water is on or off
    - Sensor to show operation mode (Auto, Manual, Boost, Override etc)
    - Selector to set hot water mode (Auto, Manual)
    - Button to Boost hot water
    - Button to override hot water
    - Button to cancel hot water overrides

- **iTRV, Roomstat, Heating Actuator, UnderFloorHeating, Smart Plug, Lights & Shutter Devices**
    - Devices for the HeatHub, each iTRV, Roomstat, Heating Actuator, Under Floor Heating Controller, Smart Plug, Light & Shutter
    - Switches for Device Lock and Identify
    - Sensor for battery (if device is battery powered)
    - Sensor for Zigbee signal
    - Switches to set Away Mode action and On/Off for Smart Plug
    - Selector to set mode (Auto, Manual) for Smart Plug
    - Many attributes available

- **Moments**
    - Buttons to activate Moments configured in the Wiser App

- **Services**
    - Supports standard services for entity types
      - i.e. climate.set_temperature, climate.set_preset, climate.set_hvac_mode, button.press, select.option, switch.turn_on, light.turn_on, cover.set_position etc
    - The following custom services are available for use with automation
    - Service `boost_heating` : Provides ability to boost the heating in a particular room
    - Service `boost_hotwater` : Provides ability to boost the heating in a particular room
    - Service `get_schedule/set_schedule/copy_schedule/assign_schedule`: Provides ability to get/set/copy/assign schedules for rooms, hotwater, lights and shutters
    - Service `set_device_mode`: Provides ability to set the mode of a specific smartplug, hot water, light or shutter. It can be set to either `manual` or `auto` , the latter means it follows any schedule set.
    - Service `remove_orphaned_entries`: Provides ability to remove HA devices for rooms/devices that have been removed from your hub.  Must have no entities.
    - Service `output_hub_json`: Provides ability to output hub json to 3 anonymised files to enable easier debugging


## Sample Images

![](https://github.com/asantaga/wiserHomeAssistantPlatform/raw/master/docs/screenshot.PNG)

![](https://github.com/asantaga/wiserHomeAssistantPlatform/raw/master/docs/hub.PNG)

![](https://github.com/asantaga/wiserHomeAssistantPlatform/raw/master/docs/room.PNG)

![](https://github.com/asantaga/wiserHomeAssistantPlatform/raw/master/docs/trv.PNG)

![](https://github.com/asantaga/wiserHomeAssistantPlatform/raw/master/docs/roomstat.PNG)

![](https://github.com/asantaga/wiserHomeAssistantPlatform/raw/master/docs/smartplug.PNG)

![](https://github.com/asantaga/wiserHomeAssistantPlatform/raw/master/docs/heatingactuator.PNG)
