# Harbor installer #

Harbor installer is a command to install or update harbor in your existing project, or create a new harbor project.

## Install to your system ##

### Mac / Linux ###

First clone this repo to your computer.

`git clone git@github.com:BRACKETS-by-TRIAD/harbor-installer.git`

If you already have harbor installer installed in your system, please pull the latest version

`git pull origin master` 

Create harbor as global command (please change /path/to/this/harbor-installer to your path where you have cloned this repo)

`ln -s /path/to/this/harbor-installer/harbor /usr/local/bin/harbor`

If the command does not work, try to use sudo. Then you can call `harbor` from everywhere.

### Windows ###

Try by yourself and update this readme.

## Installing harbor (docker) ##

To install harbor to your existing project, first go to your project directory.

`cd /path/to/your/project/`

To install craftable|laravel|php (nginx, php, db, testing db, node, redis) to your project, run

`harbor install craftable|laravel|php`

To install ionic (node) to your project, run

`harbor install ionic`

## Updating harbor (docker) ##

To update harbor in your project, run 

`harbor update`

in your working directory and confirm all overrides. This will update harbor based on current harbor type. It is not possible to automatically update to major version, sorry.

## New harbor project (docker) ##

To create a new harbor project, you can choose from multiple environments: `craftable`, `laravel`, `php` or `ionic`.

#### Craftable ####

To create craftable environment, run 

`harbor new craftable /path/to/your/project/`

which will create the dir, install harbor (craftable) and run locally craftable new to prepare the app.

#### Laravel ####

To create laravel environment, run 

`harbor new laravel /path/to/your/project/`

which will create the dir, install harbor (laravel) and run locally laravel new to prepare the app.

#### Php ####

To create empty php environment, run 

`harbor new php /path/to/your/project/`

which will create the dir, install harbor (php), but nothing else.

#### Ionic ####

To create ionic environment, run 

`harbor new ionic /path/to/your/project/`

which will create the dir, install harbor (ionic) and run locally ionic start to prepare the app.

## Harbor for laravel / craftable / php ##

For more info about harbor commands, please consult `harbor-README.md` in your project.