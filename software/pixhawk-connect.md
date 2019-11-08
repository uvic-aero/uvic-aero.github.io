# OBC Serial Connection to Pixhawk setup

The OBC (a raspberry pi) can be configured to communicate with the Pixhawk over a serial connection. This allows the OBC to retrieve telemetry data from the pixhawk.

## Setting up the Pi

[This ardupilot wiki page](http://ardupilot.org/dev/docs/raspberry-pi-via-mavlink.html) details how to set up a serial connection between the Raspberry Pi and Pixhawk.

### Installing dependencies for OBC

Before starting make sure you have pip installed and are in a Python virtual environement.

`apt-get install python-dev`

Finally install all the remaining OBC requirements

`pip install -r requirements.txt`
