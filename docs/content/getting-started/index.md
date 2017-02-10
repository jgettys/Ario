---
date: 2017-01-09T00:11:02+01:00
title: Getting started
weight: 10
---

## Installation

### Installing Dome Slit Controller

To ensure "fail safe" operation of the dome, an Arduino based dome
slit controller is installed in a small box on the dome, along with a
battery able to open and close the dome. The Arduino drives a motor
controller to control the slit motor. A solar panel can be installed
on the outside of the dome to recharge the battery.

We recommend deep cycle marine batteries for this purpose, with enough
capacity that long periods of cloudy daytime weather do not interfere
with dome operations.

(XXX battery sensor?)

The dome slit controller Arduino communicates to the dome controller
Arduino via a wireless connection (XXX what type?). A "keep alive"
command is sent periodically to it from the dome controller; if it
fails for any reason to recieve this keep alive signal, it will
automatically close the dome. (XXX after a short delay???)

The dome slit controller Arduino is also connected to a (XXX what
type?) rain/mist sensor mounted on the outside of the dome. If rain or
mist is detected, the dome will be automatically closed (unless
inhibited).  This signal is also relayed to the dome controller.  The
sensor should be mounted outside the dome so that after a suitable
delay of no rain or mist sensed (XXX how long?), observing can be restarted.

### Install Dome Controller & Raspberry Pi system.

The dome controller Arduino and Raspberry Pi is mounted in a box in
the dome and powered from observatory power (or from POE???). It
communicates via wireless to the dome slit controller.

Your dome encoder must be mounted so that the encoder will detect dome motion.
The dome encoder is connected to the dome control Arduino.

A USB interface is provided to enable ASCOM and Indi operation.

(Someday I'll do ASCOM and Indi from the Pi.)

There are four USB connectors on the Raspberry Pi. These are used for:
1.  USB Webcam for interior    (alternatively, Ethernet web cams can be used)
2.  USB Webcam for exterior/sky (alternatively, Ethernet web cams can be used)
3.  ...

The Ethernet connector for the Raspberry Pi is connected to the
observatory's network.

### Install Weather Station

Choose an appropriate weather station for your purposes from those
[supported by WeeWX](http://www.weewx.com/hardware.html).

You should select a station which supports interior temperature and
humidity; these are used to warn of dewing conditions and cause an
automatic shutdown. Most convenient are those stations which report
these values wirelessly to a base station, allowing for flexible
placement of these sensors.

Some weather stations use Ethernet to report their results and may
need additional configuration, but this also provides the maximum
flexibility in weather station placement, since USB cables are limited
to less that 5 meters.

WeeWX will keep a database of your weather information, and can be
configured to report your weather to one or more popular weather
services such as [Weather
Underground](https://www.wunderground.com/weatherstation/overview.asp),
[Open Weather Map](https://openweathermap.org/stations), and other
weather services. Weather information is very useful in interpreting your
data later.

### Install Interior Humidity and Temperature Sensors

If you have a known location that tends to dew before other locations
in your observatory dome, install the interior humidity and
temperature sensors there.

### Install Interior and Exterior Cameras

An interior camera is important to confirm that the telescope is
pointing where you think it is, independently of your TCS (telescope
control program).

An exterior camera is very useful for monitoring sky conditions.

## Setup

Install software.

## Configuration

Edit the *XXXX file* for your system.

Configure WeeWX for your weather station.

Make a backup of your Raspberry Pi's flash card and save in a safe place
where you can find it.

Note that database writes can limit the length of lifetime of your
Raspberry Pi's flash card if this database locally on the Raspberry
Pi's flash card. If you configure a remote database on a computer
system (preferably one with regular backups), this problem can be
entirely avoided. Alternatively, configure the database onto a disk
drive you add to the Raspberry Pi via a USB port.

## Backups

Make a backup of your Raspberry Pi's flash card and save in a safe place
where you can find it.

The following packages are necessary for preservation of your configuration:
* XXX package list here.

The following files are modified from Raspbian to support this installation:
* XXX file list here.

## Options

### Github integration

If your project is hosted on GitHub, add the repository link to the
configuration. If the `provider` equals **GitHub**, the Material theme will
add a download and star button, and display the number of stars:

```toml
[params]
  # Repository
  provider = "GitHub"
  repo_url = "https://github.com/jgettys/Ario"
```

### Adding a logo

If your project has a logo, you can add it to the drawer/navigation by defining
the variable `logo`. Ideally, the image of your logo should have
rectangular shape with a minimum resolution of 128x128 and leave some room
towards the edges. The logo will also be used as a web application icon on iOS.
Either save your logo somewhere in the `static/` folder and reference the file relative to this location or use an external URL:

```toml
[params]
  logo = "images/logo.png"
```

### Adding a custom favicon

Favicons are small small icons that are displayed in the tabs right next to the title of the current page. As with the logo above you need to save your favicon in `static/` and link it relative to this folder or use an external URL:

```toml
[params]
  favicon = "favicon.ico"
```

### Google Analytics

You can enable Google Analytics by replacing `UA-XXXXXXXX-X` with your own tracking code.

```toml
googleAnalytics = "UA-XXXXXXXX-X"
```

### Small tweaks

This theme provides a simple way for making small adjustments, that is changing
some margins, centering text, etc. The `custom_css` and `custom_js` option allow you to add further CSS and JS files. They can either reside locally in the `/static` folder or on an external server, e.g. a CDN. In both cases use either the relative path to `/static` or the absolute URL to the external ressource.


```toml
[params]
  # Custom assets
  custom_css = [
    "foo.css",
    "bar.css"
  ]

  custom_js  = ["buzz.js"]
```

### Changing the color palette

Material defines a default hue for every primary and accent color on Google's
material design [color palette][]. This makes it very easy to change the overall look of the theme. Just set the variables `palette.primary` and `palette.accent` to one of the colors defined in the palette:

```toml
[params.palette]
  primary = "red"
  accent  = "light-green"
```

Color names can be written upper- or lowercase but must match the names of the
material design [color palette](http://www.materialui.co/colors). Valid values are: _red_, _pink_, _purple_, _deep purple_, _indigo_, _blue_, _light-blue_, _cyan_, _teal_, _green_, _light-green_,
_lime_, _yellow_, _amber_, _orange_, _deep-orange_, _brown_, _grey_ and
_blue-grey_. The last three colors can only be used as a primary color.

![Color palette](/images/colors.png)

If the color is set via this configuration, an additional CSS file called
`palettes.css` is included that defines the color palettes.

### Changing the font family

Material uses the [Ubuntu font family](http://font.ubuntu.com) by default, specifically the regular sans-serif type for text and the monospaced type for code. Both fonts are loaded from [Google Fonts](https://www.google.com/fonts) and can be easily changed to other fonts, like for example Google's own [Roboto font](https://www.google.com/fonts/specimen/Roboto):

```toml
[params.font]
  text = "Roboto"
  code = "Roboto Mono"
```

The text font will be loaded in font-weights 400 and **700**, the monospaced
font in regular weight.

### Syntax highlighting

This theme uses the popular [Highlight.js](https://highlightjs.org/)
library to colorize code examples. The default theme is called
`Github` with a few small tweaks. You can link our own theme if you
like. Again, store your stylesheet in the `static/` folder and set the
relative path in the config file:

```toml
[params]
  # Syntax highlighting theme
  highlight_css  = "path/to/theme.css"
```

### Adding a GitHub and Twitter account

If you have a GitHub and/or Twitter account, you can add links to your
accounts to the drawer by setting the variables `github` and
`twitter` respectively:

``` toml
[social]
  twitter = ""
  github  = "digitalcraftsman"
```

### Adding menu entries

Once you created your first content files you can link them manually in the sidebar on the left. A menu entry has the following schema:

```toml
[[menu.main]]
  name   = "Material"
  url    = "/"
  weight = 0
  pre    = ""
```

`name` is the title displayed in the menu and `url` the relative URL to the content. The `weight` attribute allows you to modify the order of the menu entries. A menu entry appears further down the more weight you add. The `pre` attribute is optional and allows you to *pre*pend elements to a menu link, e.g. an icon.

Instead of just linking a single file you can enhance the sidebar by creating a nested menu. This way you can list all pages of a section instead of linking them one by one (without nesting).

You need extend the frontmatter of each file content file in a section slightly. The snippet below registers this content file as 'child' of a menu entry that already exists.

```yaml
menu:
  main:
    parent: Material
    identifier: <link name>
    weight: 0
```

`main` specifies to which menu the content file should be added. `main` is the only menu in this theme by default. `parent` let's you register this content file to an existing menu entry, in this case the `Material` link. Note that the parent in the frontmatter needs to match the name in `config.toml`.

`identifier` is the link that is shown in the menu. Ideally you choose the same name for the `identifier` and the `title` of the page. Again, `weight` allows you to change the order of the nested links in a section.

### Markdown extensions

Hugo uses [Blackfriday](https://github.com/russross/blackfriday) to process your content. For a detailed description of all options take a look at the [Blackfriday configuration](http://gohugo.io/overview/configuration/#configure-blackfriday-rendering) section in the Hugo documentation.

```toml
[blackfriday]
  smartypants = true
  fractions = true
  smartDashes = true
  plainIDAnchors = true
```
