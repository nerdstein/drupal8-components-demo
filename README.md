[![Join the chat at https://gitter.im/pattern-lab/php](https://badges.gitter.im/pattern-lab/php.png)](https://gitter.im/pattern-lab/php) [![Docs](https://img.shields.io/badge/docs-master-brightgreen.svg?style=flat)](http://drupal-lab.readthedocs.io)

# Drupal Lab

A sample Drupal 8 site with a Pattern Lab Twig powered theme.

**All commands starting with `bash` are run from root of repo; all that start with `drupal` are ran from `web/`**

## Setup

### Prerequisites

- `composer` installed
- node js installed - supported node versions: 0.12.x, 4.x, 5.x, and 6.x using npm 2.x or 3.x.

### Site Install

		bash scripts/site-setup.sh

When it asks if you want to merge or replace stuff, select merge.

## Usage

### Run Drupal & Pattern Lab Servers

In two Terminal tabs, run:

<<<<<<< cd6b4dfc73515c7dde48ef375abcc155fdb1927d
1. Run `composer run server --timeout=0`
1. Run `npm start` in `web/themes/dashing/`
=======
1. Run `composer run-script server`
2. Run `npm install -g gulp` 
2. Run `npm start` in `web/themes/dashing/`
>>>>>>> Testing changes to twig files

### Drupal Credentials

- Username: `admin`
- Password: `admin`

### Rebuild

		bash scripts/site-reinstall.sh

### Cache Rebuilds

		../vendor/bin/drupal cr all

### Theme & Pattern Lab

All commands are run from root of theme in `web/themes/dashing/`. An `npm install` was ran in `site-setup.sh` script, run `npm install` if you don't see `node_modules/` or have errors.

To compile theme (CSS & Pattern Lab):

		npm run compile

To execute watches on Scss and Pattern Lab along with a server for Pattern Lab, run:

		npm start

#### How to build your own

##### Simple, pre-packaged Drupal Theme with Twig Pattern Lab 

		drush dl patternlab

That will download a Drupal Theme ready to go: [GitHub repo](https://github.com/phase2/pattern-lab-drupal-theme) ~ [Drupal.org project page](https://www.drupal.org/project/patternlab).

##### Custom configured Drupal Theme with Twig Pattern Lab

Here's a collection of the tools used to build this site; go make something cool with them!

- [Pattern Lab 2.0 - Drupal Edition](https://github.com/pattern-lab/edition-php-drupal-standard) - this collection of tools super charges what could be done with Pattern Lab 1.0 and is made up of these pieces:
	- [Twig Engine for Pattern Lab](https://github.com/pattern-lab/patternengine-php-twig) - instead of the traditional Mustache engine in Pattern Lab 1.0, this uses Twig, which is much more powerfule, and is template language in Drupal 8!
	- [Drupal Twig Components plugin](https://github.com/pattern-lab/plugin-drupal-twig-components) - this adds extra functionality to Pattern Lab's Twig Engine, and let's use the essential `link` & `trans` Twig Functions; among many more!
	- [Data Transform plugin](https://github.com/aleksip/plugin-data-transform) - this super charges the JSON/YAML Pattern Sidecar data files to effectively let you pre-process data before rendering Twig templates. Incredibly powerful & flexible. Made by the awesome [Aleksi Peebles](http://www.aleksip.net).

The above tools give us a Twig powered, Drupal-aware Pattern Lab and can be spun up with:
	
		composer create-project pattern-lab/edition-drupal-standard

We've made a Drupal theme called [Pattern Lab Starter](https://github.com/phase2/pattern-lab-starter) that integrates the above Pattern Lab Drupal Edition along with [Gulp tasks](https://github.com/phase2/p2-theme-core) for common theme needs. 

## Configuration

After making changes, run `../vendor/bin/drupal config:export -y` and commit the files. If you just pulled or are deploying, run `../vendor/bin/drupal config:import -y` to pull configuration changes present in the yaml files in `web/sites/default/config/sync/` into the database. Very similar to Features in Drupal 7.

## Install Drupal Modules

To install a new Drupal module, run this:

    composer require drupal/MODULE_NAME:8.*

After enabling, do a `../vendor/bin/drupal config:export -y`.

## Who's behind this?

Built with love at [Phase2](https://phase2technology.com) by [Evan Lovely](https://twitter.com/EvanLovely), [Anne Sturdivant](https://twitter.com/anniegreens), and [Chris Bloom](https://twitter.com/illepic). Most of the work to make this possible happened over at the [Pattern Lab GitHub org](https://github.com/pattern-lab) with collaboration from [Dave Olsen](https://twitter.com/dmolsen) & [Aleksi Peebles](https://twitter.com/aleksip). Special thanks to Kellye Rogers and Frank Febbraro for supporting this internal project and wanting to share it with the community!
