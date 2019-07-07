# What is this?

This is a .xm file that should be used as a template in Milkytracker for those who are making .mod files to be used in GBT Player. I'm going to be mentioning GBT Player's name a lot, if you're a GB Studio user then you should know that GB Studio relies on GBT Player for music playback.

# Why do I need a template?

GBT Player does not read custom sampledata from the .mod file you're making. GBT Player has a bunch of pre-baked instruments to be called upon, so you're just writing the note, instrument # and effect data with the .mod format. This .xm file contains instruments that are essentially examples of what you will hear when your .mod file is played back with GBT Player. Normally composers can load "template.mod" provided with GBT Player to get all of these example instruments, but if you're a Milkytracker user like me you'll soon discover that Milkytracker corrupts .mod files if they are saved in Milkytracker. A corrupted .mod sounds like fast, high-pitched squeaks followed by silence when played by GBT Player.

The way to work around this is simply using "save as" to turn a .mod file into a .xm file, and then only pressing "save" in the .xm file format. When you want to test your song you'd press "save as" to turn your .xm file into a .mod file for GBT Player. This .xm template has this first step done for you so you can just get to using the template as intended, although you will still have to "save as" to .mod when testing your song. I also added a few things specific to composing with GBT Player.

## tldr;

Saving an .xm file is safe, saving as a .mod file is safe (that's how you export your song) just *never* hit "save" on a .mod file in Milkytracker.

## Things changed from template.mod

In channels 1 and 2 I put effect C00 on the first row to silence these two tracks. They're pesky channels that otherwise play a default note on their own if their volume isn't controlled on the first row of the song. Feel free to start your song with notes on either of these channels and replace C00 with Cxx or another effect (if you're okay with max volume instead.) Milkytracker says not to use the volume column in .mod, but it is capable of (usually+) converting volume data to Cxx. For newcomers I would stick to writing volume changes as Cxx to get the hang of writing one effect at a time for a channel. For instance, putting volume data such as 40 at the same time as another effect like E8F on the same row will just overwrite the effect to be C40.

I also added F07 to channel 4 because it's the only channel that can set the song's tempo silently on the first row. 99% of songs will want to put effect F on channel 4 to start the song. Project settings aren't read by GBT Player at all, so just use F to set your song's speed instead of adjusting it on Milkytracker's interface. You can still set effect F on channels 1 or 2 later on in the song.

+I have sometimes noticed things like volume data not getting carried over when going from .mod to .xm to .mod but this hasn't happened for a while and I don't know what caused this originally. New file .xm to .mod carries over volume data perfectly. I need to test this more to know for sure.

## Some tempo stuff to know

Tempo is only used to emulate refresh rates and won't be read by GBT Player, so leave it at 130 BPM if you're using GB Studio 1.1.0 or no changes to its music playback have been made since 1.1.0.

If your in-game speed differs too greatly from your tracker and you want to emulate the in-game speed better, adjust your project tempo to better match what you're hearing in-game. Songs with F04 or faster (F01 is the fastest) will sound more accurate in the tracker with a project tempo of 150 BPM to emulate the 50hz screen of the Gameboy. I can't fully explain why 150 BPM is the magic number, but this shouldn't matter so much as long as you test your song often enough.

## Some volume Stuff to know

Effect and instrument parameters work in hexadecimal. We have 28 instruments from 1 to 4, 8 to F (15) and 10 to 1F (31). Meanwhile, C40 is max volume, C20 is 50% volume, C08 is 12.5% volume, and so forth. Don't enter 1, 2, 3, 4 etc. for volume because:

Channels 1 and 2 only show volume changes in steps of 4
`0, 4, 8, C, 10, 14, 18, 1C, 20, etc.`

3C also is the same as 40 for some reason

Channel 3 only shows volume changes in steps of 16
`0, 10, 20, 30, 40`

Channel 4 shows the full range of volume changes but rarely will this be used

# Credits

This template was created by Ember#1765 / DeerTears on Github/itch.io

Thanks to:
MelonadeM for being an all-knowing GBT guide
richardLULZ for assisting with music docs and code review
chris for making GB Studio
GB Studio community for being awesome!
and AntonioND for making GBT Player
