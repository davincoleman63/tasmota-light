# tasmota-cottage
Tasmota config for the cottage at Teign Rd

Used to contol a pump.
Beep when the power is supplied 3 beeps
Wait for power to stabilise before enabling power to pump - 30 seconds
Immediately disconnect the pump if the tank level drops too low
Beep to warn tank is low - every seconds
Wait for the tank to fill before re-enabling the pump - suggest 15 minutes.
Long beep when the pump is re-enabled.

Ensure relay is off when starting up under all circumstances. Don't assume there is enough water in the tank. Check at startup.

There are 2 sensors - tank and pump to indicate the pump is on. The pump is not on if the pressure switch has reached correct pressure. This should be reported back to Home Assistant.

Use the push button to control power to the pump regardless of whether there is enough water in tank. Turn off pump after minute if tank too low and pump power is on.

## Files
- config.dmp: Tasmota config
- rules.txt: Tasmota rules

## esp8266 pinout

- GPIO0 - push button3
- GPIO5 - buzzer
- GPIO12 - Switch1 / Tank / Inverse
- GPIO13 - Switch2 / Pump / Inverse
- GPIO14 - Relay / Power1

## timeouts

- Power On - 30 secs
- Tank On - 10 minutes
- Button state - 10 secs
