# docker-crashplan

This uses [JrCs/docker-crashplan](https://github.com/JrCs/docker-crashplan) but has some extra config scripts:

* Docker-compose script
* Windows script to connect to remote instance or local instance from Windows

## Docker-compose script

This just replaces the need to add settings in run line. Instead just use

    docker-compose up -d

Although, you will need to first edit the docker-compose.yml file to ensure matches your requirements.

To build the docker image from the compose file you do:

    docker-compose build

Although this will automatically be done by the up command if required.

## Windows script

This is a simple vbscript that lets you choose between local and remote crashplan instances. You will need to 
copy this script onto you windows computer to run. 

To allow access to the remove crashplan instance you will first need to find out the remote host Authentication 
Token and use the configure remote instance option when you run the script. 

To get the remote host Authentication Token just enter the following the remote (docker) machine:

    sudo docker exec -it dockercrashplan_crashplan_1 head /var/crashplan/id/.ui_info

This should give you some output similar to the following:

    4243,bf183d97-4007-48de-bae7-a5872e06f92c,0.0.0.0

The text between the two commas is the remote host Authentication Token to enter in the Windows script.


