# lutron_caseta

RA3 Support for HA

modified lutron_caseta HA Integration for testing unreleased pylutron-caseta module

Install the contents of this repository into the config/custome_components/lutron-caseta folder in your HA installation.

This custom_component will override the lutron_caseta integration that is part of HA, to allow testing of the latest pylutron-caseta module in my danaues/pylutron-caseta#dev repository.

Adds support for the RA3 Processor
- Switches and Dimmers
- Sunnata Keypads
- Occupancy Sensing

Work in progress:
 - LEDs
 - Scenes

Installation:

1. Install the Custom Component
    Clone this repository into your config/custom_components folder

2. Manually install the unreleased version of pylutron-caseta inside the homeassistant container

    go to your console on your HA system
    you should have the "ha > " prompt
    enter the command "login", and you get a "#" prompt
    enter the command "docker exec -it $(docker ps -f name=homeassistant -q) bash" and you get a "bash-5.1#" prompt
    enter the command "pip uninstall pylutron-caseta" and answer "y" when asked to proceed (or it will skip if not installed)
    enter the command "pip install git+https://github.com/danaues/pylutron-caseta@testing"
    restart home assistant using the HA web interface or client
    add the "Lutron Caseta" integration using the HA web interface or client
