<p align="center">
<img src="https://github.com/home-assistant/assets/blob/master/misc/loading-screen.gif" width="250" height="250" />
</p>

[![Continuous integration](https://github.com/tetsuo13/home-assistant-config/actions/workflows/ci.yml/badge.svg)](https://github.com/tetsuo13/home-assistant-config/actions/workflows/ci.yml)

- [Devices](#devices)
- [Automations](#automations)
- [Custom Components](#custom-components)
- [Screenshots](#screenshots)
- [Other Noteable Configurations](#other-noteable-configurations)

This is the configuration used in my [Home Assistant](https://home-assistant.io/) (HA) setup.

Runs on a [Raspberry Pi 3B](https://www.raspberrypi.org/products/raspberry-pi-3-model-b/) using [Home Assistant Operating System](https://github.com/home-assistant/operating-system).

# Devices

## Hubs

| Device | Connection | Home Assistant |
| ------ | ---------- | -------------- |
| [Aeotec Z-Stick Gen5](https://aeotec.com/products/aeotec-z-stick-gen5/) (ZW090-A) | USB | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js/) |
| [Philips Hue Bridge](https://www.philips-hue.com/en-us/p/hue-bridge/046677458478) | Ethernet | [Philips Hue](https://www.home-assistant.io/integrations/hue) |

## Lighting

| Device | Connection | Home Assistant |
| ------ | ---------- | -------------- |
| Litake LED Strip Lights (WIFIDD328) | Wi-Fi | [Flux LED/MagicLight](https://www.home-assistant.io/integrations/flux_led/) |
| [Philips Hue white and color ambience bulb](https://www.philips-hue.com/en-us/p/hue-white-and-color-ambiance-1-pack-e26/046677562984#overview) | Hue Hub (Zigbee) | [Philips Hue](https://www.home-assistant.io/integrations/hue) |
| [Philips Hue white ambience bulb](https://www.philips-hue.com/en-us/p/hue-white-1-pack-a21-e26/046677557805) | Hue Hub (Zigbee) | [Philips Hue](https://www.home-assistant.io/integrations/hue) |

## Climate

| Device | Connection | Home Assistant |
| ------ | ---------- | -------------- |
| [Ecobee 4](https://www.ecobee.com/en-us/smart-thermostats/smart-wifi-thermostat-with-voice-control/) (EB-STATE4-01) | Wi-Fi | [ecobee](https://www.home-assistant.io/integrations/ecobee) |
| [Ecobee room sensor](https://www.ecobee.com/en-us/accessories/smart-temperature-occupancy-sensor/) | ecobee | [ecobee](https://www.home-assistant.io/integrations/ecobee) |

## Sensors & Switches

| Device | Connection | Home Assistant |
| ------ | ---------- | -------------- |
| [Belkin Wemo Mini Smart Plug](https://www.belkin.com/us/support-article?articleNum=226110) (F7C063fc) | Wi-Fi | [Belkin WeMo](https://www.home-assistant.io/integrations/wemo) |
| [Ecolink Door & Window Sensor](https://discoverecolink.com/product/z-wave-door-window-sensor-oem/) (DW-ZWAVE2.5-ECO) | Z-Wave JS | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js) |
| [Fibaro Z-Wave Flood Sensor](https://www.fibaro.com/en/products/flood-sensor/) (FGFS-101) | Z-Wave JS | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js) |
| [First Alert Smoke & CO Alarm](https://www.resideo.com/us/en/products/security/alarms/combo-smoke-carbon-monoxide-alarms/zcombo-wireless-smoke-carbon-monoxide-alarm-works-with-zwave-ring-zcombo/) | Z-Wave JS | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js) |
| [GE Enbrighten Z-Wave In-Wall Smart Switch](https://byjasco.com/ge-enbrighten-z-wave-plus-smart-switch-quickfit-and-simplewire) | Z-Wave JS | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js) |
| [GE Z-Wave In-Wall Smart Fan Control](https://byjasco.com/enbrighten-z-wave-in-wall-smart-fan-control-white-almond) | Z-Wave JS | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js) |
| [TP-Link Kasa Smart Plug](https://www.tp-link.com/us/home-networking/smart-plug/hs103/) (HS103VS) | Wi-Fi | [TP-Link](https://www.home-assistant.io/integrations/tplink/) |
| [ZOOZ 4-in-1 sensor](https://www.getzooz.com/zooz-zse40-4-in-1-sensor/) (ZSE40) | Z-Wave JS | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js) |
| [ZOOZ Double Switch](https://www.getzooz.com/zooz-zen30-double-switch/) (ZEN30) | Z-Wave JS | [Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js) |

## Cameras

| Device | Connection | Home Assistant |
| ------ | ---------- | -------------- |
| Amcrest PoE Camera (IP5M) | Ethernet | [Dahua](https://github.com/rroller/dahua) |
| [Amcrest Video Doorbell](https://amcrest.com/4mp-wifi-camera-doorbell-ad410.html) (AD410) | Wi-Fi | [Amcrest](https://www.home-assistant.io/integrations/amcrest/) |

## Media

| Device | Connection | Home Assistant |
| ------ | ---------- | -------------- |
| [Sonos WiFi bookshelf speaker](https://www.sonos.com/en-us/symfonisk-by-sonos-and-ikea) (SYMFONISK) | Wi-Fi | [Sonos](https://www.home-assistant.io/integrations/sonos) |

# Automations

Christmas lights automations aren't available year-round (they're added when the tree goes up, removed again when the tree goes down). See previous years in [#40](https://github.com/tetsuo13/home-assistant-config/pull/40), [#15](https://github.com/tetsuo13/home-assistant-config/pull/15) and [c013a7c](https://github.com/tetsuo13/home-assistant-config/commit/c013a7c10aa19f6366598c1a0cd125f82ec8b465) on what was done.

## [Door Automations](automation/doors.yaml)

Opening and closing doors causes an announcement to be made through all of the Sonos speakers. A chime is played first to grab attention followed by a TTS announcement. See the [`sonos_say`](components/scripts/sonos.yaml) script on how this is done.

The primary automation is to announce which door was used however this is overridden during several months where a the TTS announcement is replaced by playing an audio file from the [`www/audio`](www/audio) directory instead. The months are:

* October: goulish sounds and howling wolf
* November: turkey gobble
* December: sleigh bells

There's also the birthday binary sensor which, when enabled, causes a birthday jingle to be played instead of the TTS announcement or special month sound. This binary sensor should take precedence over all other events. The days are held in [`secrets.yaml.dist`](secrets.yaml.dist) in the `birthday_evaluator` key, as a Python array of month and day values. Since it wasn't possible to parse a secret value into a template, the entire template was set as the secret value.

The [`sonos_play_file`](components/scripts/sonos.yaml) script used to play audio files to all Sonos speakers. It has logic to never broadcast to the office speaker during business hours (Monday - Friday, 8am - 5pm).

## [Motion Automations](automation/motion.yaml)

Guest bathroom lights turn on when motion is detected, they turn back off after a few minutes of no motion. Overnight, the lights only turn on at a low brightness to prevent blindness. If the fan is on, it'll turn off after a few minutes after the lights have turned off.

### Motion Detection with Cameras

The front door camera takes care of sending notifications using the Amcrest Smart Home app (one of the few services connected to the cloud). The icon shown on the automations tab of the dashboard just controls whether or not the camera should notify the Amcrest app.

For the other camera, when motion is detected a snapshot is taken and a notification is sent to the Companion App using a URL to the snapshot that's accessible from the Internet. By default these snapshots are only accessible from the intranet which makes them largely useless when not at home (see [standard attachments](https://companion.home-assistant.io/docs/notifications/notification-attachments/#parameters) documentation for Companion App). The snapshots are created in the `www/images/snapshots` directory so that viewing them doesn't require authentication. Considering that authentication isn't a requirement and an attacker could potentially guess filenames by iterating through past date and times should they discover the publically accessible URL to the server, an additional component is added to the filename to dramatically increase the possible combinations of characters. This doesn't stop a motivated attacker from eventually finding a valid filename, just makes it more apparent in the logs of a brute-force attack.

Camera snapshots are made available for review in the Media section of Home Assistant. This was done because notifications sent to the Companion App are ephemeral: you view them at the moment of notification, swipe it away, and have no ability to view it again unless going to the NVR. While the images from the Media browser can be manually deleted there's a scheduled shell script that will automatically delete images older than a few days.

The Home Assistant server isn't on the Internet but instead sits behind a reverse proxy with only the camera snapshots directory exposed. Example relevant Nginx config:

```nginx
server {
  location ~ ^/snapshots/([a-z\.\-0-9_]+\.jpg)$ {
    proxy_pass            http://192.168.1.1:8123/local/images/snapshots/$1;
    proxy_set_header      X-Real-IP        $remote_addr;
    proxy_set_header      X-Forwarded-For  $proxy_add_x_forwarded_for;
    proxy_set_header      Host             $http_host;
  }

  # Fallback for all other requests. Return 403 Forbidden.
  location / {
    return 403;
  }
}
```

## [Smoke Alarm Automations](automation/smoke_alarms.yaml)

When a smoke alarm detects smoke or carbon monoxide, an announcement is made over all Sonos speakers, an email is sent, and a notification on the mobile app is sent. Then all available lights are turned on.

## [Fan Automations](automation/fans.yaml)

Air purifier isn't smart but it's plugged into a Wemo smart plug. Air purifier is intended to run overnight. Automation cuts power in the morning to turn it off and another automation task turns power back on however someone must still manually press the "on" button on the air purifier unit to actually turn it on. Toggling power to the dumb air purifier is preferable to some of the much more expensive smart air purifiers out there.

## [Light Automations](automation/lights.yaml)

There are automations to gradually fade on bedside lamps on weekday mornings, turn off before leaving for work, gradually fade on again at sundown, and gradually fade off by bedtime. Similar automations to handle outside lights.

The "Live" light is a bulb connected to a Wi-Fi switch that's meant to be on when Microsoft Teams is in a call. Determining the status of Teams is done by calling a RESTful service which returns a simple JSON result that's interpretted as either true or false. The responsibility of determining the status of Teams is offloaded to [Teams Status Pub](https://github.com/tetsuo13/TeamsStatusPub).

# Custom Components

There are some custom components in use. See the [README](custom_components/README.md) file in the [`custom_components`](custom_components) directory for more details.

# Screenshots

![UI](screenshots/home.png "Home page")
![UI](screenshots/automations.png "Automations")

# Links

This repo tries to adhere to the [YAML Style Guide](https://developers.home-assistant.io/docs/documenting/yaml-style-guide) at the Home Assistant Developer Docs.

## Other Noteable Configurations

The [examples](https://www.home-assistant.io/examples/) at Home Assistant's web site were extremely helpful in seeing how others got started however below is a list, in no special order, of other configurations that were particularly inspiring:

* https://github.com/geekofweek/homeassistant
* https://github.com/scstraus/home-assistant-config
* https://github.com/mcaminiti/homeassistant

