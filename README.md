# Launchpad Qlab
A bridge between Qlab and a Novation Launchpad MK3, intended for music playout for broadcast TV.

May work with other Launchpads (like the X), but it may require some code tweaks.

---
## Installation
```
git clone https://github.com/Eviltechie/Launchpad-Qlab.git
cd Launchpad-Qlab
yarn
yarn start
```

## Config


First couple of lines you should see host and midiPort. Host is the IP of the computer running Qlab. Normally this would be localhost. (This was developed on and will run on Windows, but that's obviously of dubious value because Qlab is Mac only.) Set midiPort to whatever port you see "Launchpad Mini MK3 LPMiniMK3 MIDI In" listed as (on a Mac, it's different on Windows). Midi ports will be listed when you run the program.

---

## How it Works

This works with the cart wall in Qlab. Setup the wall as you like. For broadcast playout I suggest setting the default music cue to "fade and stop all over 1 second" so that it will cross fade between carts. Don't forget to color your buttons too. You can use any size grid you want, up to 8x8.

You will also want to setup a MIDI trigger on each cart corresponding to it's position on the launchpad. (Ignore the top and right row of buttons, the ones with the labels.)

Setup the bottom right most button in the workspace MIDI settings to panic all. (This button will light up red when running.)

If you are dealing with a situation where you need commercial music playout and need to trigger two cuts simultaneiously, this is also supported. Add a cue list, add a group cue in timeline mode, add both your cuts to the group cue, and make sure the group cue has a number. (Remember to uncheck the fade on the music cues and add it to the group cue instead here.) Then you can just add a Start cue to trigger the group cue in the list from the cart wall.

After all this, just start the program and you should see the lights come on to match the colors and positions of the carts. A playing cart will blink. (Does not blink for start cues though.)

You will see log items print to the console. To exit, do Control + C on your keyboard. It will total up play count and times, and print to the console. The log and totals will also be written to a text file.

Don't forget, the Launchpad must be in programmer mode. (Hold session for a second or so, then hit the buttom right orange button, and then session again to exit.)

Also, this program will only read cues on startup. If you move any cues, change tracks, etc., you'll need to restart.

=============

Got questions? File an issue or come find me on the video engineering discord.