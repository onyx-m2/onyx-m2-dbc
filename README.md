# Onyx M2 DBC File

This repo contains the DBC file used by the Onyx M2 Project for my Tesla Model 3. This
file originated from an unknown source, and has been updated by me for a couple of years
now, using the research shared on Tesla Owners Online forum. I've attempted to preserve
the naming convention (which presumably originates from Tesla), but in many places, I've
had to make up names for signals.

## Loading Dynamically

To load this DBC dynamically, use the GitHub's RAW file access,

`https://raw.githubusercontent.com/onyx-m2/onyx-m2-dbc/master/tesla_model3.dbc`

and use the Onyx M2 DBC tools to parse it.

## Updating

I'll be updating this repo as incrementally as possible as new changes are detected
in the car's signals. The version number at the top of the file refers to the car's
software build the updates were tested on. This obviously isn't a guaranty that the
data is correct.

I've got a webhook setup on this repo to automatically redeploy my instance of the
server when the dbc file updated on master. If you want to do the same for your
server, you could fork this repo and set that up. This would also allow you to update
on your schedule (which might be good if our cars don't get software updates at the
same time).

## Credit

Most of the community work to decode the signals is discussed in the mega-thread
https://teslaownersonline.com/threads/diagnostic-port-and-data-access.7502/.

Much of the investigation work was performed by Josh Wardell, and he maintains his
own DBC file at https://github.com/joshwardell/model3dbc.

## Disclaimer

This is not an official document from Tesla, and there's no guaranty this data will
work for your car.

_Use at your own risk!_

And never, ever, attempt to use this data to write messages to the CANbus. The intent
of this project is simply to read the data and build nice displays, not control and/or
circumvent the car's security features or any of its systems.

## Change Log

A rough history of updates to the DBC file.

- Oct 2019: Added unix and system time signals"
- May 2020: Added many definitions adapted from joshwardell's file"
- Jul 2020: Energy buffers update for 2020.20.X"
- Jul 2020: Updates for 2020.24.X"
- Nov 2020: Updates for 2020.40.X, UI_status moved from 12 to 851"
- Oct 2021: Updates for 2021.24.4"
- Apr 2024: Big update with partial support for stuff has changed in the last few
  few years. Also a big cleanup of dead code, and I'm now running a validator that
  found some syntax issues my home built DBC parser didn't care about.

## Todo

- Figure out what up with inverter temp; my old ones still for me, but others have them at 1493(R) and 1366(F) now
- The brake temps don't work anymore
