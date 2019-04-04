<p align="center">
<img src="https://github.com/home-assistant/home-assistant-assets/blob/master/loading-screen.gif" />
</p>

This is the configuration used in my [Home Assistant](https://home-assistant.io/) setup.

The [Cookbook](https://www.home-assistant.io/cookbook/) at Home Assistant's web site was extremely helpful in seeing how others got started.

```
docker run --detach --restart=always \
--name="home-assistant" \
--volume=/etc/home-assistant:/config \
--volume=/etc/localtime:/etc/localtime:ro \
--net=host \
--device /dev/ttyACM0 \
homeassistant/home-assistant
```

# Devices

## Lighting

* [Philips Hue Bridge](https://www2.meethue.com/en-us/p/hue-bridge/046677458478) (BSB002)
* [Philips Hue white and color ambience bulb](https://www2.meethue.com/en-us/p/hue-white-and-color-ambiance-single-bulb-e26/046677464486) (LCT016)
* [Philips Hue white ambience bulb](https://www2.meethue.com/en-us/p/hue-single-bulb-e26/046677461003) (LWB014)

## Climate

* [Ecobee 4](https://www.ecobee.com/ecobee4/) (EB-STATE4-01)

## Sensor / Switch

* [Aeotec Z-Stick Gen5](https://aeotec.com/z-wave-usb-stick) (ZW090)
* [Belkin Wemo Mini Smart Plug](https://www.belkin.com/us/p/P-F7C063/) (F7C063fc)
* [Ecobee room sensor](https://www.ecobee.com/room-sensors/) (BK4G)
* [Fibaro Z-Wave Flood Sensor](https://www.fibaro.com/en/products/flood-sensor/) (FGFS-101)

