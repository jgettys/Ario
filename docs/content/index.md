---
date: 2017-02-08T21:07:13+01:00
title: ATMoB Domus Dome Controller
type: index
weight: 0
---

## Modern, Open Source Design

Domus is a modern dome control system, intended to enable fully
automatic operation of a modern telescope, based on an elaboration of
the excellent work of Gerry Rozema's [NexDome system](https://github.com/grozzie2/NexDome).

Domus is very inexpensive and adaptable and is built from widely available components and all software and firmware is open source.

## Features

* "Fail Safe" operation: Domus is designed to enable safe unattended operation of a telescope. As such, the observatory must "fail safe" in case of:
    * Rain or mist conditions
    * Excessive Wind
    * Dewing conditions
* Adaptability to local telescope system
    * Wireless slit controller, enabling battery powered operation of the slit closing mechanism; no power and the dome will still be safed
    * Dome control via [ASCOM](http://ascom-standards.org), for Windows users
    * Dome control via [Indi](http://indilib.org/), for Linux and MacIntosh users
    * Dome control and customization via Web application
* Adaptability to a large variety of weather equipment, by using the [WeeWX](http://www.weewx.com/) software package
    * These include a large variety of USB weather stations, as well as some Ethernet based weather stations.
    * Custom rain/mist sensor, for "fail safe" operation of the dome

See the [getting started guide]({{< relref "getting-started/index.md" >}}) for instructions how to get
Domus up and running.

## Components

* Dome Slit Opening/Closing Mechanism
* Dome Rotation Mechanism
* Dome control electronics
* WeeWX weather software
* Weather station (select appropriate station from those supported by WeeWX)
* Raspberry Pi controller
    * To enable integration of the WeeWX weather system,
    * remote dome control,
    * interior and exterior cameras,
    * "fail safe" operation, so that malfunction of the telescope computer will not inhibit safing of the telescope.
    * (optional) local GPS stratum zero NTP server, to provide good time to the local observing environment
* Raspbian OS, configured for "headless" remote use via ssh or web operation
  
## Acknowledgements

Gerry Rozema designed the excellent [NexDome controller](https://github.com/grozzie2/NexDome)

Charlie Gettys designed the dome slit mechanism, with kibitzing from Jim Gettys, Alan Sliski, and [Bruce Berger](http://www.medomakretreatcenter.com/bruceberger.php).

[Alan Sliski](http://www.theskyscrapers.org/alan-sliski) designed the dome rotation mechanism and encoder, and the electronics for controlling the slit and dome, and integrated the weather sensor.

[Jim Gettys](https://en.wikipedia.org/wiki/Jim_Gettys) put together the control server, based on a Raspberry Pi, the WeeWX software, and glue.

The Web site design is due to the Hugo site generator, using the Material docs theme.

Furthermore, thanks to [Steve Francia](https://gihub.com/spf13) for creating Hugo and the [awesome community](https://github.com/spf13/hugo/graphs/contributors) around the project.
