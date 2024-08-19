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

To understand how this circuit works, see [this video by Ralph S Bacon](https://www.youtube.com/watch?v=g1rbIG2BO0U) or [this blog post by Indrek Luuk](https://circuitjournal.com/arduino-auto-power-off). 

The project adds an RC circuit to give the microcontroller time to boot, allowing for very short button presses to turn the power supply on. This allows, for example, for reed switches (like [this one from Adafruit](https://www.adafruit.com/product/2384) with a contact time of ~2ms) to be used.

# Version Naming #

`<AMPS>-<INPUT-VOLTAGE-MAX>-<INPUT-VOLTAGE-MIN>-<OUTPUT-VOLTAGE>-<LED>`


