# Disconnecting Power Supply #

The disconnecting power supply (for lack of a better name) is a simple way to make a project running on a battery for a long period of time.

This project was inspired by [this video by Ralph S Bacon](https://www.youtube.com/watch?v=g1rbIG2BO0U) and [this blog post by Indrek Luuk](https://circuitjournal.com/arduino-auto-power-off). 

This works with projects that: 

- run periodically (not constantly)
- are triggered by an outside input, like a button press
- are compatible with the supply's voltage and amperage limitations

## Usage Example ##

This project could be used to make a battery powered device that sends an alert when mail is delivered. 

For wiring, the input power is connected to a 9v battery. Then the output power and ground are connected to the micro controller. Connect the power supply's keep-alive to a pin on the micro controller. Connect the trigger pin and the ground pin to a switch that closes when the mailbox door is opened (ex: a gravity switch). 

Next, program a micro controller to send a message when it is powered on. Then add a line so that the first thing your program does is raise the keep-alive pin high to make sure the power supply remains on, and then at the end of your program, after the message is sent, add code to lower the keep-alive pin to 0v to disconnect the battery.

## How it works ##

# Version Naming #

<LED><AMPS>-<INPUT-VOLTAGE-MAX>-<INPUT-VOLTAGE-MIN>-<OUTPUT-VOLTAGE>


