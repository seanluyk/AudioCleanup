## Exercise 2: SoX Basics

### 2.1 Get metadata about an audio file
- Open **Terminal**
- Navigate to your workshop audio files using the command line
- In **Terminal** type:
~~~shell
sox thunder.wav -n stat
~~~
- This provides you with some very basic stats which may be useful/interesting to you
- You can also use the soxi command to get information from the file header. In **Terminal** type:
~~~shell
soxi thunder.wav
~~~
 - This returns information found in the file's header (e.g. channels, bit rate, duration)
 - You can also type multiple file names after the main stat/soxi commands to get stats returned for multiple files at once for the purposes of comparison:
 ~~~shell
 soxi thunder.wav bbc_rain---rai_nhu0506113.wav
 sox thunder.wav bbc_rain---rai_nhu0506113.wav -n stat
 ~~~
 ### 2.2 Remix an audio file
- In SoX it is possible to remix audio files in interesting ways
- For example, you may want to turn a monaural file into a dual mono file, which mimics stereo
- In **Terminal** type:
~~~shell
sox bbc_rain---rai_nhu0506113.wav rain.wav remix 1 1,1
~~~ 
- The first (comma separated) number specifies which channels to remix. The second indicates that two mono channels are to be created
### 2.3 Combine multiple audio files
- In SoX there are multiple methods for combining audio files, which we'll experiment with below to create a storm from our thunder and rain files:
#### Concatenate files
- In **Terminal** type:
~~~shell
sox --combine concatenate thunder.wav rain.wav storm.wav
~~~
- Hear the result by typing:
~~~shell
play storm.wav
~~~
- You can stop playback by typing CTRL+C
- You can even play files back in reverse! Type:
~~~shell
play storm.wav reverse
~~~
#### Merge Files
- In **Terminal** type:
~~~shell
sox -m thunder.wav rain.wav storm2.wav
~~~ 
- This will create one file that mixes the other files together
- Play back the file you created using the merge command and note the difference between the file produced using the concatenate command
### 2.4 Modify files
- SoX had many commands that allow you to easily modify files using the command line. Today we'll work with some basic ones:
#### Pad a recording with silence
- In **Terminal** type:
~~~shell
sox storm2.wav stormpad.wav \
pad  5 [amount of silence HH:MM:SS to add at the beginning of your file] [amount of silence HH:MM:SS to add at the end of your file]  
~~~ 
#### Apply a fade in/fade out
- Similar to the pad command, the fade command can be used to add fade-ins/outs to a file:
- In **Terminal** type:
~~~shell
sox stormpad.wav stormfade.wav \
fade 5 [fade-in position HH:MM:SS] 2:00 [fade out start HH:MM:SS]
~~~
#### Trim
- Used for cutting sections of an audio file
- Specify how much to trim from start and end of file (*where the file should end)
- Use 0 as first parameter is not trimming from start
- Navigate to the radio directory
- celeb1.wav has ~11 seconds of unnecessary silence at the beginning we'd like to trim
- In **Terminal** type:
~~~shell
sox celeb1.wav celeb1trim.wav \
trim 11 [beginning value in HH:MM:SS] 3:30 [end value in HH:MM:SS]
~~~ 
- You can also set fade in and out times automatically by including stati right in the command:
- In **Terminal** type: 
~~~shell
sox celeb1.wav celeb1trim2.wav fade t 10 $(soxi -d in.wav) 10
~~~ 
