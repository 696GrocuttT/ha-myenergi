# myenergi for Home Assistant

[![GitHub Release][releases-shield]][releases]
[![GitHub Activity][commits-shield]][commits]
[![License][license-shield]](LICENSE)

[![pre-commit][pre-commit-shield]][pre-commit]
[![Black][black-shield]][black]

[![hacs][hacsbadge]][hacs]
[![Project Maintenance][maintenance-shield]][user_profile]
[![BuyMeCoffee][buymecoffeebadge]][buymecoffee]

[![Discord][discord-shield]][discord]
[![Community Forum][forum-shield]][forum]

myenergi custom component for [Home Assistant](https://home-assistant.io)
This component will make all [myenergi](https://myenergi.com) devices connected to your hub acessible in Home Assistant.
The energy sensors are fully compatible with the energy dashboard in Home Assistant.

It will create HA devices depending on what you have installed:

- Hub

  - Grid power sensor (W)
  - Grid voltage sensor (V)
  - Grid frequency sensor (Hz)
  - Genertion power sensor (W)
  - Charging/heating power sensor (W)
  - Home power today sensor (W), power that is not charging, heating, generation and export.
  - Energy generated today sensor (kWh)
  - Energy exported today sensor (kWh)
  - Energy imported today sensor (kWh)
  - Green energy today sensor (kWh), this is the amount of generated energy that was used for charging or heating instead of being exported

- Zappi

  - Charge mode selector that let you switch between Stopped, Fast, Eco and Eco+ charge modes
  - Charge added this session sensor (kWh)
  - Energy consumed today sensor (kWh)
  - Energy diverted today sensor (kWh)
  - Power sensors for internal and external CT clamps (W)
  - Plug status sensor
  - Charger status sensor
  - Minumum green level number input
  - Service to start boost (provide boost amount in kWh as paramter)
  - Service to start smart boost (provide boost amount in kWh and desired finished time as paramters)

- Eddi

  - Power sensors for internal and external CT clamps (W)
  - Temperature sensors if fitted

- Harvi

  - Power sensors for internal and external CT clamps (W)

Talking to the myenergi API using the [pymyenergi python library](https://github.com/cjne/pymyenergi)

**This component will set up the following platforms.**

| Platform | Description                                         |
| -------- | --------------------------------------------------- |
| `sensor` | Provides various readings for your myenergi devices |
| `select` | Configure devices                                   |
| `number` | Configure devices                                   |

![example][logo]

## HACS Installation

1. Search for myenergi in HACS
2. Install

## Manual Installation

1. Using the tool of choice open the directory (folder) for your HA configuration (where you find `configuration.yaml`).
2. If you do not have a `custom_components` directory (folder) there, you need to create it.
3. In the `custom_components` directory (folder) create a new folder called `myenergi`.
4. Download _all_ the files from the `custom_components/myenergi/` directory (folder) in this repository.
5. Place the files you downloaded in the new directory (folder) you created.
6. Restart Home Assistant
7. In the HA UI go to "Configuration" -> "Integrations" click "+" and search for "myenergi"

Using your HA configuration directory (folder) as a starting point you should now also have this:

```text
custom_components/myenergi/translations/en.json
custom_components/myenergi/translations/fr.json
custom_components/myenergi/translations/nb.json
custom_components/myenergi/translations/sensor.en.json
custom_components/myenergi/translations/sensor.fr.json
custom_components/myenergi/translations/sensor.nb.json
custom_components/myenergi/__init__.py
custom_components/myenergi/config_flow.py
custom_components/myenergi/const.py
custom_components/myenergi/manifest.json
custom_components/myenergi/sensor.py
custom_components/myenergi/number.py
custom_components/myenergi/select.py
```

## Configuration is done in the UI

<!---->

## Contributions are welcome!

If you want to contribute to this please read the [Contribution guidelines](CONTRIBUTING.md)

## Credits

This project was generated from [@oncleben31](https://github.com/oncleben31)'s [Home Assistant Custom Component Cookiecutter](https://github.com/oncleben31/cookiecutter-homeassistant-custom-component) template.

Code template was mainly taken from [@Ludeeus](https://github.com/ludeeus)'s [integration_blueprint][integration_blueprint] template

---

[integration_blueprint]: https://github.com/custom-components/integration_blueprint
[black]: https://github.com/psf/black
[black-shield]: https://img.shields.io/badge/code%20style-black-000000.svg?style=for-the-badge
[buymecoffee]: https://www.buymeacoffee.com/cjne.coffee
[buymecoffeebadge]: https://img.shields.io/badge/buy%20me%20a%20coffee-donate-yellow.svg?style=for-the-badge
[commits-shield]: https://img.shields.io/github/commit-activity/y/cjne/ha-myenergi.svg?style=for-the-badge
[commits]: https://github.com/cjne/ha-myenergi/commits/main
[hacs]: https://hacs.xyz
[hacsbadge]: https://img.shields.io/badge/HACS-Default-41BDF5.svg?style=for-the-badge
[discord]: https://discord.gg/Qa5fW2R
[discord-shield]: https://img.shields.io/discord/330944238910963714.svg?style=for-the-badge
[logo]: logo@2x.png
[forum-shield]: https://img.shields.io/badge/community-forum-brightgreen.svg?style=for-the-badge
[forum]: https://community.home-assistant.io/
[license-shield]: https://img.shields.io/github/license/cjne/ha-myenergi.svg?style=for-the-badge
[maintenance-shield]: https://img.shields.io/badge/maintainer-%40cjne-blue.svg?style=for-the-badge
[pre-commit]: https://github.com/pre-commit/pre-commit
[pre-commit-shield]: https://img.shields.io/badge/pre--commit-enabled-brightgreen?style=for-the-badge
[releases-shield]: https://img.shields.io/github/release/cjne/ha-myenergi.svg?style=for-the-badge
[releases]: https://github.com/cjne/ha-myenergi/releases
[user_profile]: https://github.com/cjne
[myenergi_library]: https://github.com/cjne/pymyenergi
