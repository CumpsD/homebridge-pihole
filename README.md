# Homebridge Pi-hole [![verified-by-homebridge](https://badgen.net/badge/homebridge/verified/purple)](https://github.com/homebridge/homebridge/wiki/Verified-Plugins)

[![npm](https://img.shields.io/npm/v/homebridge-pihole.svg)](https://www.npmjs.com/package/homebridge-pihole)
[![npm](https://img.shields.io/npm/dt/homebridge-pihole.svg)](https://www.npmjs.com/package/homebridge-pihole)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/8bf5a87dc8a84df6a15deb699d43ee2b)](https://www.codacy.com/manual/arendruni/homebridge-pihole)
[![Build Status](https://github.com/arendruni/homebridge-pihole/workflows/Main/badge.svg?branch=master)](https://github.com/arendruni/homebridge-pihole/actions?query=workflow%3AMain)
[![MIT license](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

[Pi-hole](https://github.com/pi-hole/pi-hole) plugin for Homebridge

## Requirements

- [Homebridge](https://github.com/nfarina/homebridge) - _HomeKit support for the impatient_
- [Pi-hole](https://github.com/pi-hole/pi-hole) - _A black hole for Internet advertisements_

## Installation

1. Install this plugin `npm install -g homebridge-pihole`
2. Update your configuration file. See sample-config.json in this repository for a sample.

See the Pi-hole [installation section](https://github.com/pi-hole/pi-hole#one-step-automated-install) for more details.

## Configuration

There are the following options:

- `name` Required. Accessory name, default is _Pi-hole_.

### Pi-hole Configuration

- `auth` Pi-hole auth token.
- `host` Pi-hole host, default is `localhost`.
- `port` Pi-hole port, default is `80`.
- `ssl` If the Pi-hole server should be connected to with SSL.
- `baseDirectory` The directory where Pi-hole is found on the server, default is `/admin/`.
- `time` How long Pi-hole will be disabled, in seconds, default is 0 that means permanently disabled.
- `logLevel` Logging level, three different levels: 0: logging disabled, 1: logs only HTTP errors, 2: logs each HTTP response. Default is set to 1.

### Device Information

- `manufacturer` Custom manufacturer, default is _Raspberry Pi_.
- `model` Custom model, default is _Pi-hole_.
- `serial-number` Should be a 9 digit number in the string format _123-456-789_.

See the [sample-config.json](sample-config.json) file to see an example of how to configure the accessory. In the example the configured accessory will disable Pi-hole for a time interval of two minutes (120 seconds).

## How to get a Pi-hole authentication token

1. Login into your Pi-hole Admin Console.
2. Navigate to the _Settings_ page and then to the _API / Web interface_ tab.
3. At the bottom of the page click on the _Show API Token_ button, a popup window will ask for confirmation, go ahead and click on _Yes, show API token_.
4. A new window will open showing a QR code, copy the _Raw API Token_ below the QR code.
5. Paste your API token in the homebridge configuration file.
