# Kint plugin for Craft CMS

Adds Kint, an in-app PHP debugger, for use in Twig and PHP.

## Installation

To install Kint, follow these steps:

1. Download & unzip the file and place the `kint` directory into your `craft/plugins` directory
2.  -OR- do a `git clone https://github.com/mildlygeeky/craft_kint.git` directly into your `craft/plugins` folder.  You can then update it with `git pull`
3. Install plugin in the Craft Control Panel under Settings > Plugins
4. The plugin folder should be named `kint` for Craft to see it.  GitHub recently started appending `-master` (the branch name) to the name of the folder for zip file downloads.

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

{{ craft.kint.d(someTwigVariable) }}

This is the simplest usage, and will output an interactive debugger for the variable passed in.

#### dd (dump and die)

{{ craft.kint.dd(someTwigVariable) }}

This works the same way as the d (dump) command, except it will cause output to end immediately after the debugger is returned.

#### s (simple dump)

{{ craft.kint.s(someTwigVariable) }}

This works essentially the same way as the built-in Twig dump method, and returns a plain text debugging output.

#### sd (simple dump and die)

{{ craft.kint.s(someTwigVariable) }}

Same as above, but with output ending immediately after the plain text debugging output is returned.

#### time (point-in-time memory usage and timestamp)

{{ craft.kint.time }}

Basic reporting of memory usage at the time that the command is run, as well as a timestamp. If used multiple times,
it will also report the time since it was last called and average duration.

### Services

All of the above functions are also exposed through services, though Kint does put its functions
into PHP un-namespaced as well. In the future I may try to fork it and just expose everything though
one central object to keep things clean.

## Kint Changelog

### 1.0.0 -- 2016.02.15

* Initial release

## Credit

* Thank you to Rokas Šleinius, the developer of Kint - he welcomes donations at [Kint's website](http://raveren.github.io/kint/)
* Icon created by Lemon Liu from the Noun Project

Brought to you by [Mildly Geeky](https://www.mildlygeeky.com)
