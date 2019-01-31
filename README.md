# Harbor installer #

Harbor installer is a command to install or update harbor in your existing project, or create a new harbor project.

## Install to your system ##

### Mac / Linux ###

First clone this repo to your computer.

`git clone git@github.com:BRACKETS-by-TRIAD/harbor-installer.git`

Create harbor as global command (please change /path/to/this/harbor-installer to your path where you have cloned this repo)

`ln -s /path/to/this/harbor-installer/harbor /usr/local/bin/harbor`

If the command does not work, try to use sudo. Then you can call `harbor` from everywhere.

### Windows ###

Try by yourself and update this readme.

## Installing harbor (docker) ##

To install harbor to your existing project, first go to your project directory.

`cd /path/to/your/project/`

To install craftable|laravel|php (nginx, php, postgres db, testing postgres db, node, redis) to your project, run

`harbor install craftable|laravel|php`

To install ionic (node) to your project, run

`harbor install ionic`

## Updating harbor (docker) ##

To update harbor in your project, run 

`harbor update`

in your working directory and confirm all overrides. This will update harbor based on current harbor type.

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

Harbor provides docker configuration for your project. It is based on vessel by Fideloper LLC - https://vessel.shippingdocker.com/. It consist of
 
* nginx container, 
* php container, 
* postgres container, 
* testing postgres container,
* node container,
* redis container

This script handles the current instance. To create new, install or update harbor, use harbor installer.

### Let's init laravel / craftable ###

If you have an existing laravel / craftable project and you have not initialize this project, run 

`harbor init`

which will setup some .env variables, install required packages and will run npm

### Starting a harbor (docker) ###

To start the docker environment use:

`harbor start`

This will start all the docker containers and set up network and volumes correctly. So now we can play around with empty PostgreSQL or php. Now you can point your browser to the http://localhost and you should be able to see a default `/` route mapped to public/index.php.

### Rebuild a harbor (docker) ###

In case you change some env values for docker, or changes some docker file or other configuration, you should run

`harbor rebuild`

NOTE: To rebuild images use `-i|--images`, to destroy volumes use `-v|--volumes` 

### Daily usage ###

In this section you can find all commands supported by harbor:

`harbor start` will start all containers based on docker-compose.yml file.

`harbor stop` will stop and destroy all containers.

`harbor restart`will stop and destroy and then starts again all containers.

`harbor rebuild` will stop and destroy all containers then starts again all containers, build them if changes has been made.

`harbor artisan` OR `harbor art` will pass all additional arguments to php container to php artisan command, e.g. `harbor art make:migration` goes to php docker container and call `php artisan make:migration`.

`harbor composer` OR `harbor comp` will pass all additional arguments to php container to composer command, e.g. `harbor comp require brackets/craftable` goes to php docker container and call `composer require brackets/craftable`.

`harbor test` will run phpunit tests on new php container. All additional arguments are passed to phpunit.

`harbor npm` will run npm command on node container and pass all additional arguments to npm.

`harbor yarn` will run yarn command on node container and pass all additional arguments to yarn.

`harbor gulp` will run gulp command on node container from node modules and pass all additional arguments to gulp.

`harbor psql` will run psql command on pgsql container with username and host form .env file and pass all additional arguments to psql command.

`harbor pg_dump` will run pg_dump command on pgsql container with username and host form .env file and pass all additional arguments to pg_dump command.

### Install command (use with care) ###

`harbor new laravel` will install laravel application to current folder. See [new laravel project](#laravel), it is the recommended way.

`harbor new craftable` will install craftable application to current folder. See [new craftable project](#craftable), it is the recommended way.

### SSH keys ###

To use ssh keys in php container, copy your keys to ./docker/php/ssh. You have to restart container after adding keys. SSH keys may be required for some git repositories.

## Harbor for ionic ##

Harbor provides docker configuration for your ionic project. It consist of node container.

### Starting a harbor ionic serve (in docker) ###

To start the docker environment with ionic use:

`harbor ionic-serve`

This will start the docker container and start also ionic serve for development.

### Daily usage ###

In this section you can find all commands supported by harbor ionic.

`harbor rebuild` will stop and destroy all containers then starts again all containers, build them if changes has been made.

`harbor ionic` will run ionic serve command on node container.

`harbor npm` will run npm command on node container and pass all additional arguments to npm.

`harbor yarn` will run yarn command on node container and pass all additional arguments to yarn.

`harbor gulp` will run gulp command on node container from node modules and pass all additional arguments to gulp.