# Harbor Global #

Harbor global is a command to add or update harbor in your project.

## Install to your system ##

### Mac/Linux ###

Create harbor as global command

`ln -s /path/to/this/harbor-global/harbor /usr/local/bin/harbor`

If the command does not work, try to use sudo. Then you can call `harbor` from everywhere.

### Windows ###

Try by yourself and update this readme.  

## Adding harbor (docker) ##

To add harbor (nginx, php, postgres db, testing postgres db, node, redis) to your project, go to project directory and run

`harbor add`

To add harbor ionic (node) to your project, go to project directory and run

`harbor add ionic`

## Updating harbor (docker) ##

To update harbor in your project, run 

`harbor update`

in your working directory and confirm all overrides.

To update harbor ionic in your project, run 

`harbor update ionic`

in your working directory and confirm all overrides.





