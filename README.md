# Twinkly Home Assistant
[![hacs_badge][hacs-shield]][hacs]

Twinkly integration for home assistant

# Installation
Install with [HACS](https://github.com/custom-components/hacs) or follow these instructions for manual installation:

- Copy `/python_scripts/twinkly.py` to your `/config/python_scripts/`
- Add the following `switch` to `/config/configuration.yaml`
- Replace TWINKLY_IP_HERE with the IP address of your Twinkly lights (3 occurrences)

```
switch:
  - platform: command_line
    switches:
      twinkly:
        command_on: "python3 /config/python_scripts/twinkly.py TWINKLY_IP_HERE on"
        command_off: "python3 /config/python_scripts/twinkly.py TWINKLY_IP_HERE off" 
        command_state: "python3 /config/python_scripts/twinkly.py TWINKLY_IP_HERE state"
        value_template: "{{ value == \"1\" }}"
        friendly_name: Twinkly
```

[hacs-shield]: https://img.shields.io/badge/HACS-Default-orange.svg
[hacs]: https://github.com/custom-components/hacs
