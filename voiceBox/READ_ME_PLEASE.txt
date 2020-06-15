
 VoiceBox - a package of scripts _mainly_ by Brian Wolven, but with help from
	    Jens Arnold and Joerg. Brian is the one responsible for any
	    mistakes. =)
 
 Simple directions - just run voiceBox.hta and read the directions therein.

 Not-so-simple directions - read below.



 VoiceBox is a package of scripts to automatically generate audio clips
 containing the names of all files and/or folders in a directory tree for use
 with the "Talkbox" feature, available to users of the Rockbox open source
 firmware for various digital audio players. Talkbox permits the device to
 speak the names of the folders (and now files, as well) as one navigates the
 directory structure on the device, thus permitting "eyes-free" use for those
 for whom the usual visual navigation is difficult or simply inadvisable.

 Required components (should all be located in a single folder):

 1) voiceBox.hta    - what you actually execute via GUI - no drag and drop

 2) voiceBox.wsf    - what you actually execute, supports drag and drop 

 3) voiceUtils.vbs  - "library" of functions and subroutines

 4) lame.exe        - does the mp3 encoding. Easily obtained with google. =)
                      (for the Archos line of mp3 players)

 5) rbspeexenc.exe  - does the (raw) speex encoding (for all newer DAPs like
                      irivers, ipods etc)
                       

 Optional components (should/will be in the same folder as above):

 5) voiceBox.ini    - edit true/false in here to change options, if necessary.
                      This file will be created with some default settings if
		      it does not exist.

 6) rockbox400.png, - optional graphics for the HTA and an icon for your
    rockboxicon.ico   voiceBox shortcuts

 7) voiceBox.log    - Log file produced by the voiceBox script - may be useful
                      for debugging purposes if you encounter difficulties

 USAGE:

  You now have several different options for running voiceBox.

  1) Run voiceBox.hta. Select your processing options and the desired path,
     THEN ...

  2) Click on the 'Run voiceBox' button in the HTA (HTml Application),
     OR ...

  3) Choose to save a shortcut. You may then use the shortcut to run the
     voiceBox script (voiceBox.wsf) with the path and options specified at the
     time the shortcut was created. Multiple shortcuts with different options
     and/or paths may be saved for later use, e.g., save one shortcut that
     voices only folders, one that voices both files and folders, etc.
     Shortcuts are created on the desktop by default, but you can stick them
     anywhere you'd like (on your computer, that is...).

  You can also drag and drop folders onto the voiceBox.wsf script. Each of the
  following methods will use the settings in voiceBox.ini, unless you override
  them with a command line argument. I'm not going to list all the command line
  arguments; you can save a shortcut and then examine the properties if you
  really want to run things that way. Do note that when you run the HTA, the
  options selected there are immediately transferred to the voiceBox.ini file.
  You can thus use the HTA to change the default settings for voiceBox.wsf, or
  simply open voiceBox.ini in a text editor and do it manually.

   1) Drag and drop the desired files and/or folders to be voiced onto the
      voiceBox.wsf script, or onto a shortcut to that script.

   2) Execute the script in your file manager; enter the desired file or folder
      at the prompt.

   3) Run the script from the command line:
   
      > wscript voiceBox.wsf
   
      Enter the desired file or folder at the prompt.

   3) Run the script from the command line, giving the file and folder names as
      arguments. Quote all names containing spaces:

     > wscript voiceBox.wsf M:\Playlists "M:\Misc\Some Playlist.m3u"

 OUTPUTS:

 A log of the targets encountered (files and folders) and the actions taken is
 written in the file voiceBox.log. You may safely delete this file if all goes
 well. If you encounter problems, the contents may be useful in figuring out
 what happened. 

 IMPORTANT:

 This script will generate clips for speaking folder names if the variable
 VoiceFolders is set to "True" (the default initial configuration) in
 voiceBox.ini.

 This script will also generate clips for speaking of file names with certain
 extensions (.mp3, .m3u, and .cfg) if the variable VoiceFiles is set to "True"
 (the default initial configuration) in voiceBox.ini. Either variable may be
 changed to  "False" if you do not want to generate clips for the corresponding
 type.

 You may also wish to change the settings for booleans 'RemoveWav' and
 'Overwrite*' in the voiceBox.ini file. If you're generating clips for the
 first time or you are updating existing clips and have not changed voice
 settings, leave Overwrite_dotTalk set to False (it should be set that way when
 you get these files) to skip pre-existing files and only add new content.

 You may also choose to leave the generated WAV files on disk and experiment
 with varying settings for the Lame encoder; in this case you should change
 Overwrite_dotWav and RemoveWav to False, and Overwrite_dotTalk to True.

 The default configuration has Overwrite_dotWav and RemoveWav set to true and
 Overwrite_dotTalk set to False, creating WAV files and then converting them to
 MP3's for every folder (if VoiceFolders is True) and file (if VoiceFiles is
 True) only if a clip does not already exist, and then deleting the WAV files.

 GENERAL INFO:

 The script now sets only the language:

    Set spkr.Voice = spkr.GetVoices("Language=409").Item(0)

 The voice will then default to that selected in the Speech applet of your
 control panel, allowing you to choose from any voice (including higher-quality
 non-Microsoft offerings) installed on your system.

 Audio clips are captured and stored in wave format, then converted into MP3
 format by a third party application (lame). If you execute the script from the
 top level of your music file hierarchy while your Archos device is connected to
 your PC, then the resulting audio clips will be generated and stored in the
 correct location for use with the Talkbox feature.  Alternatively, if you
 mirror your music folder structure from your PC to your Archos device, you can
 just run the script on the PC and then update the files on your Archos with
 your usual synchronization routine. You will need to place a copy of the lame
 executable (lame.exe, ~191 kB) in the same folder as this script, or
 alternatively edit the path specified by the variable
 'encodeApp' in VoiceUtils.vbs.

 A log of all the commands executed by the script is written to the file
 voiceBox.log in the folder containing this script.

 NOTE: If you don't already have them installed, you may obtain the SAPI speech
 runtime routines, and the Lernout & Hauspie TTS3000 Text-to-Speech Engines at
 http://www.microsoft.com/msagent/downloads/user.asp

 Helpful hint from Aman Singer:

   If you're looking for a relatively small package that will install
   SAPI 5.1 (contains Microsoft Mike and Mary voices) on your system,
   try SayPad from http://inspiredcode.net/4VisImp.htm 

 Many thanks to Eric Phelps (http://www.ericphelps.com/scripting) for providing
 working examples of the text-to-wave implementation in VBScript, and to Joerg
 and the Rockbox team for making it all possible in the first place.
