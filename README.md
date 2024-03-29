# homeassistant_irrigationcaddy
Config files for controlling irrgationcaddy sprinkler system from homeassistant.
Thanks to the homeassistant forums where most of this information can also be found (https://community.home-assistant.io/t/garden-irrigation/1950).

Some notes on irrgationcaddy (as of now the company making this product is shut down, so no API docs are available):

1. curl -X POST http://ip_of_irrigationcaddy/status.json returns a json where the boolean value of "allowRun" specifies is the System is ON or OFF
2. curl -X POST http://ip_of_irrigationcaddy/status.json also returns if any sprinkler zones are currenlty running in the boolean value for "running"
3. curl -X POST -d 'run=run' http://ip_of_irrigationcaddy/runSprinklers.htm turns the Sprinkler System to ON (this does not actually start a Run)
4. curl -X POST -d 'stop=off' http://ip_of_irrigationcaddy/stopSprinklers.htm turns the Sprinkler System to OFF
5. curl -X POST -d 'pgmNum=1&doProgram=1&runNow=true' http://ip_of_irrigationcaddy/runProgram.htm starts a Program (same as Run Now on the Program interface of IrrigationCaddy)  
6. curl -X POST -d 'stop=active' http://ip_of_irrigationcaddy/stopSprinklers.htm stops an active zone. As of now if a program has 5 zones, this will have to be called 5 times to completely turn off the system. Appreciate it if you let me know of a better solution!

Thanks to the following github projetcs/contributors for research and work done on this. The samples in theese projects below have excellent code snippets:

mrbalky/irrigationcaddy - Simple scripts for IrrigationCaddy

khawkes/indigo-irrigationcaddy - Forked from whizzosoftware/indigo-irrigationcaddy-plugin on bitbucket.

tjotala/IrrigationCaddy - Simple library for interacting with IrrigationCaddy sprinkler controllers

whizzosoftware/indigo-irrigationcaddy-plugin

skonves/Konves.IrrigationCaddy - c# client library for KGControls' Irrigation Caddy




