# Harbor Installer #

Harbor installer is a command to install, update harbor in your existing project, or create a new harbor project.

## Install to your system ##

### Mac/Linux ###

First clone this repo to your computer.

`git clone git@bitbucket.org:TRIAD-Advertising/harbor-installer.git`

Create harbor as global command (please change /path/to/this/harbor-installer to your path where you have cloned this repo)

`ln -s /path/to/this/harbor-installer/harbor /usr/local/bin/harbor`

If the command does not work, try to use sudo. Then you can call `harbor` from everywhere.

### Windows ###

Try by yourself and update this readme.

## Installing harbor (docker) ##

To install harbor to your existing project, first go to your project directory.

`cd /path/to/your/project/`

To install php (nginx, php, postgres db, testing postgres db, node, redis) to your project, run

`harbor install php`

To install ionic (node) to your project, run

`harbor install ionic`

## Updating harbor (docker) ##

To update harbor in your project, run 

`harbor update`

in your working directory and confirm all overrides. This will update harbor based on current harbor or harbor-ionic file.

## New harbor project (docker) ##

To create a new harbor project, you can choose from multiple environments: `craftable`, `laravel`, `ionic` or `empty`.

#### Craftable ####

To create craftable environment, run 

`harbor new craftable /path/to/your/project/`

which will create the dir, install harbor (php) and run locally craftable new to prepare the app.

#### Laravel ####

To create laravel environment, run 

`harbor new laravel /path/to/your/project/`

which will create the dir, install harbor (php) and run locally laravel new to prepare the app.

#### Ionic ####

To create ionic environment, run 

`harbor new ionic /path/to/your/project/`

which will create the dir, install harbor (ionic) and run locally ionic start to prepare the app.

#### Empty ####

To create empty php environment, run 

`harbor new empty /path/to/your/project/`

which will create the dir, install harbor (php), but nothing else.