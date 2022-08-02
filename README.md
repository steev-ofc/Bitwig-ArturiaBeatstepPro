Bitwig controller script for Arturia Beatstep Pro.

The script:
  * creates 3 note inputs: sequencer 1, sequencer 2, and drum
  * uses the midi channels of 1, 2, and 10 for each of the Arturia Beatstep Pro's sequencers
  * expects control mode to be channel 3, which enables
    * encoders 1-8 control cursor device parameters
    * encoders 9-16 control cursor device macros
    * steps 1 / 2 are previous track / next track
    * steps 3 / 4 are previous device / next device on selected track
    * steps 5 / 6 close / open preset browser for selected device
    * steps 7 / 8 are previous / next preset in preset browser
    * step 9 toggles cursor device off / on
    * top row pads 1,2,3 toggle record arm, solo, mute for selected track
    * bottom row pads 1 / 2 decrease / increase selected track volume
  * supports clock sync from Bitwig; set sync to USB mode on Arturia Beatstep Pro

For the encoders and step buttons to work correctly, you need to load the "ArturiaBeatstepBitwig.beatsteppro" template on your Arturia Beatstep Pro via Arturia's MIDI Control Center software.
This is the default factory template with the following modifications:

  * the encoder knobs are configured to send relative increment/decrement values for knob turns; this enables proper control of device params and macros within Bitwig.
  * the step buttons are configured to send CCs to both MIDI and USB ports (factory template doesn't send to USB+MIDI, just MIDI)

**Installation**

  1. Copy the Steev directory to your Bitwig Controller Scripts directory.

     (On MacOS this is `~/Documents/Bitwig Studio/Controller Scripts`)
     (On Windows this is `%USERPROFILE%\Documents\Bitwig Studio\Controller Scripts`)
     (On Linux this is `~/Bitwig Studio/Controller Scripts`)

  2. Load the "ArturiaBeatstepPro.beatsteppro" template on your Arturia Beatstep Pro via Arturia's MIDI Control Center software.


  3. Open Bitwig and navigate to the Settings tab, then locate the "Controllers" section, , click the "Add Controller" option, choose Steev from the drop down list, then Arturia Beatstep Pro and click "Add". 


  4. Be sure that your Arturia Beatstep Pro is setted in the following way:

     USER - MIDI CH 16			IF NOT	Press CONTROL MODE, hold CHAN and select 16 on the step sequencer.
     SEQUENCER 1 - MIDI CH 1		IF NOT	Press SEQUENCER 1, hold CHAN and select 1 on the step sequencer.
     SEQUENCER 2 - MIDI CH 2		IF NOT	Press SEQUENCER 2, hold CHAN and select 2 on the step sequencer.
     DRUM - MIDI CH 10			IF NOT	Press DRUM, hold CHAN and select 10 on the step sequencer.
