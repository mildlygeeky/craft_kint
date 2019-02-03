# Kint plugin for Craft CMS (Craft 2.x version)

Adds Kint, an in-app PHP debugger, to Craft CMS for use in Twig and PHP.

![Screenshot](kint/resources/screenshots/screenshot.png)

## Installation

To install Kint, follow these steps:

1. Download & unzip the file and place the `kint` directory into your `craft/plugins` directory
2.  -OR- do a `git clone https://github.com/mildlygeeky/craft_kint.git` directly into your `craft/plugins` folder.  You can then update it with `git pull`
3. Install plugin in the Craft Control Panel under Settings > Plugins

Kint works on Craft 2.4.x and Craft 2.5.x.

## Kint Overview

Kint is an interactive debugger for PHP applications. Full documentation is available at http://raveren.github.io/kint/.

Its advantages include that it can be run out of devMode (though you would not want to use it in a public setting), and
it is interactive, with keyboard shortcuts to expand and collapse objects, separates content from methods, etc.

## Configuring Kint

No configuration required, but you can set the theme that Kint will use within the plugin's settings screen.

## Using Kint

### Templating

#### d (dump)

`{{ d(someTwigVariable) }}` or `{{ craft.kint.d(someTwigVariable) }}`

This is the simplest usage, and will output an interactive debugger for the variable passed in.

#### dd (dump and die)

`{{ dd(someTwigVariable) }}` or `{{ craft.kint.dd(someTwigVariable) }}`

This works the same way as the d (dump) command, except it will cause output to end immediately after the debugger is returned.

#### s (simple dump)

`{{ s(someTwigVariable) }}` or `{{ craft.kint.s(someTwigVariable) }}`

This works essentially the same way as the built-in Twig dump method, and returns a plain text debugging output.

#### sd (simple dump and die)

`{{ sd(someTwigVariable) }}` or `{{ craft.kint.sd(someTwigVariable) }}`

Same as above, but with output ending immediately after the plain text debugging output is returned.

#### time (point-in-time memory usage and timestamp)

`{{ time() }}` or `{{ craft.kint.time }}`

Basic reporting of memory usage at the time that the command is run, as well as a timestamp. If used multiple times,
it will also report the time since it was last called and average duration.

### Services

All of the above functions are also exposed through services, though Kint does put its functions
into PHP un-namespaced as well. In the future I may try to fork it and just expose everything though
one central object to keep things clean.

## Kint Changelog

### 1.0.0 -- 2016.02.15

* Initial release

### 1.0.1 -- 2016.02.15

* Fixed issue that caused crash when a theme was not selected from settings page

### 1.0.2 -- 2016.02.16

* Fixed issue where raw JS could be shown on page if script tags with double-quotes were used
* Removed reference to Kint's path being included below the debugger

### 1.1.0 -- 2016.02.16

* Added Twig functions `d`, `dd`, `s`, `sd`, and `time` for easier usage

## Credit

* Thank you to Rokas Šleinius, the developer of Kint - he welcomes donations at [Kint's website](http://raveren.github.io/kint/)
* Icon created by Lemon Liu from the Noun Project

Brought to you by [Mildly Geeky](https://www.mildlygeeky.com)
