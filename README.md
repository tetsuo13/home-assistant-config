<p align="center">
<img src="https://github.com/home-assistant/home-assistant-assets/blob/master/loading-screen.gif" />
</p>

This is the [Home Assistant](https://home-assistant.io/) configuration used in my Home Assistant setup.

The [Cookbook](https://www.home-assistant.io/cookbook/) at Home Assistant's web site was extremely helpful in seeing how others got started.

```
docker run --detach --restart=always \
--name="home-assistant" \
--volume=/etc/home-assistant:/config \
--volume=/etc/localtime:/etc/localtime:ro \
--net=host \
homeassistant/home-assistant
```

# Connected Devices

## WiFi Connected Devices

* __[Belkin Wemo Mini Smart Plug](https://www.belkin.com/us/p/P-F7C063/)__ (F7C063fc)

## Philips Hue Devices

* __[Philips Hue white and color ambience bulb](https://www2.meethue.com/en-us/p/hue-white-and-color-ambiance-single-bulb-e26/046677464486)__ (LCT016)
* __[Philips Hue white ambience bulb](https://www2.meethue.com/en-us/p/hue-single-bulb-e26/046677461003)__ (LWB014)

## Hardwired Devices

* __[Philips Hue Bridge](https://www2.meethue.com/en-us/p/hue-bridge/046677458478)__ (BSB002)

