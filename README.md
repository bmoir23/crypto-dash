Track cryptocurrencies on a connected screen using this dashboard from https://coinmarketcap.com/

![dash](https://i.ibb.co/wQxrLzp/20210128-115828.jpg)

## Hardware required

The list of items you’ll need is also included below:

- Raspberry Pi 3B/3B+, 4 or 400 (**Note:** this project will not work with the Pi Zero or older devices with < 1GB RAM)
- 16GB Micro-SD Card (we recommend Sandisk Extreme Pro SD cards)
- Display (TV/Monitor via HDMI)
- Micro-USB cable
- Power supply

## Setup and configuration

You can deploy this project to a new balenaCloud application in one click using the button below:

[![](https://balena.io/deploy.svg)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/phil-d-wilson/crypto-dash)


## Changing displayed content

### Loading a URL

To configure the URL displayed by webkit, set the **`LAUNCH_URL`** environment
variable. If nothing is set, balenaDash will display the [browser block](https://github.com/balenablocks/browser#choosing-what-to-display) local webpage.

### Switching URLs quickly using your web browser or Slack

Your balenaDash device is also running a small webserver on port 8080. The screen will show the URL configured at `LAUNCH_URL` normally, but the webserver allows you to put other URLs on screen quickly and easily. If you tell balenaCloud to expose your device's public URL, then you can even control it with Slack (or `curl`, or anything that can use webhooks). [More details](https://github.com/mozz100/tohora/blob/master/README.md)

## Automate backlight switching

To use automatic backlight switching you’ll need to configure a few service variables for the scheduler service.

`ENABLE_BACKLIGHT_TIMER=1`
`BACKLIGHT_ON=0 8 * * *`
`BACKLIGHT_OFF=0 23 * * *`

The `BACKLIGHT_ON` and `BACKLIGHT_OFF` variables accept standard cron syntax; take a look at https://crontab.guru if you’re not familiar. For more instructions check out [our blog post](https://www.balena.io/blog/automate-the-backlight-timer-on-your-balenadash-display/).

To change the timezone for the scheduler, set the `TZ` service variable to something from the [TZ database list](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones).

## Become a balena poweruser

Want to learn more about what makes balena work? Try one of our [masterclasses](https://www.balena.io/docs/learn/more/masterclasses/overview/). Each lesson is a self-contained, deeply detailed walkthrough on core skills to be successful with your next edge project.

Check them out at our [docs](https://www.balena.io/docs/learn/more/masterclasses/overview/). Also, reach out to us on the [Forums](https://forums.balena.io/) if you need help.
