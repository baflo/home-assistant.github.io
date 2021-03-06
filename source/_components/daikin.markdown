---
layout: page
title: "Daikin AC"
description: "Instructions on how to integrate Hive devices with Home Assistant."
date: 2017-12-10 21:00
sidebar: false
comments: false
sharing: true
footer: true
logo: N/A
ha_category: Climate
ha_release: 0.59
ha_iot_class: "Local Polling"
---

### Description ###

The component integrates Daikin air conditioning systems into Home Assistant.

To automatically add all your Daikin devices (ACs and associated sensors) into your Home Assistant installation, add the following to your 'configuration.yaml' file:

<p class='note warning'>
    Please note, the Daikin platform integrates **ONLY the european versions of Daikin ACs (models BRP069A41, 42, 43, 45)** into Home Assistant
</p>

```yaml
# Example configuration.yaml entry
daikin:
  hosts:
    - 192.168.4.161

  monitored_conditions:
    - inside_temperature  
    - outside_temperature  
    
```

{% configuration %}
hosts:
  description: List of IP addresses or hostnames.
  required: true
  type: array
monitored_conditions:
  description: List of items you want to monitor for each device.
  required: false
  detault: All conditions
  type: list
  keys:
    inside_temperature:
      description: The current temperature measured inside the house.
    outside_temperature:
      description: The current temperature measured outside the house.      
{% endconfiguration %}

<p class='note warning'>
    Please note that some AC devices may report outside temperature only when they are turned on.
</p>


The Daikin Home Assistant platform currently supports the following Hive devices:

- [Climate](/components/climate.daikin)
- [Sensor](/components/sensor.daikin)
