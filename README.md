
# PiRadioInterface v1.0

A simple but effective interface for controlling your repeater, simplex node, remote transceiver or similar from a Raspberry Pi board using audio and I/O ports.

Initially developed for duplex or simplex repeater control with SvxLink (http://www.svxlink.org/).


## The finished board on top of a Raspberry Pi 3B+ using SvxLink

![App Screenshot](https://github.com/sa0azt/PiRadioInterface/blob/main/piradioint_svxlink.jpg)


## Documentation

### Schematic

[Schematic - v1.0](https://github.com/sa0azt/PiRadioInterface/blob/main/piradioint_sch.pdf)

### Installation

#### Audio codec drivers

With a fresh installation of the latest Raspbian OS, add an overlay at the end of the file for the WM8960 Audio codec in /boot/config.txt

```bash
dtoverlay=wm8960-soundcard
```

Note that the WM8960 drivers where implemented in the Raspbian OS kernel v5.4 and will not work with older versions without further configuration.

After the audio codec is enabled and shown in AlsaMixer, don't forget to unmute the sound to "Left & Right PCM Mixer".

#### GPIO pinouts

The following IO ports (used by the RJ45 connectors) are mapped below

```bash
OUT1 <-> gpio22
OUT2 <-> gpio27
OUT3 <-> gpio17

IN1 <-> gpio23
IN2 <-> gpio24
IN3 <-> gpio25
```

#### Svxlink GPIO configuration

Follow the instructions at https://github.com/sm0svx/svxlink/wiki/InstallBinRaspbian#gpio-configuration-not-verified-instruction

#### 1-Wire interface

To enable the communication with 1-wire sensors, add the following line at the end of /boot/config.txt

```bash
dtoverlay=w1-gpio
```

### FAQ

#### Can I buy this board assembled and ready?

Currently working on a simple PayPal site for international purchases, stay tuned!

If you can't wait - drop me an email at mattias (at) hivako.se and ask for a paypal invoice.

#### Can this board be used with Svxlink?

Yes, the board is initially developed for use with Svxlink (http://www.svxlink.org)

#### Can this board be used with other software, like Echolink & Allstar?

The short answer is yes, as long as audio and general purpose IO ports is enough, then you can use whatever software you want.

## License

[GPLv3](https://choosealicense.com/licenses/gpl-3.0/)

