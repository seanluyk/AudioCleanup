## Exercise 2: SoX Basics

### Get metadata about an audio file
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
 soxi thunder.wav rain.wav
 sox thunder.wav rain.wav -n stat
 ~~~
 ### Remix an audio file
- In SoX it is possible to remix audio files in interesting ways
- For example, you may want to turn a monaural file into a dual mono file, which mimics stereo. Note that rain2.wav is file where we are ouputting the dual mono file to
- In **Terminal** type:
~~~shell
sox rain.wav rain2.wav remix 1 1,1
~~~ 
- The first (comma separated) number specifies which channels to remix. The second indicates that two mono channels are to be created
### Combine multiple audio files
- In SoX there are multiple methods for combining audio files, which we'll experiment with below to create a storm from our thunder and rain files:
#### Concatenate files
- In **Terminal** type:
~~~shell
sox --combine concatenate thunder.wav rain2.wav storm.wav
~~~
- Hear the result by typing:
~~~shell
play storm.wav
~~~
- You can also apply reverb:
~~~shell
sox play storm2.wav reverb
~~~
- You can stop playback by typing CTRL+C
- You can even play files back in reverse! Type:
~~~shell
play storm.wav reverse
~~~
#### Mix Files
- In **Terminal** type:
~~~shell
sox -m thunder.wav rain2.wav storm2.wav
~~~ 
- This will create one file that mixes the other files together
- Play back the file you created using the merge command and note the difference between the file produced using the concatenate command
### Modify files
- SoX had many commands that allow you to easily modify files using the command line. Today we'll work with some basic ones:
#### Pad a recording with silence
- In **Terminal** type:
~~~shell
sox storm2.wav stormpad.wav pad  5 [amount of silence HH:MM:SS to add at the beginning of your file] 5 [amount of silence HH:MM:SS to add at the end of your file]  
~~~ 
#### Trim
- Used for cutting sections of an audio file
- Specify how much to trim from start and end of file (i.e. where the file should end)
- Use 0 as first parameter if not trimming from start of file
- We can remove the silence we added to stormpad.wav. We can trim at the end of the file, but won't today
- In **Terminal** type:
~~~shell
sox stormpad.wav stormtrim.wav trim 5 [beginning value in HH:MM:SS] [end value in HH:MM:SS]
~~~ 
#### Apply a fade in/fade out
- Similar to the pad command, the fade command can be used to add fade-ins/outs to a file:
- In **Terminal** type:
~~~shell
sox stormtrim.wav stormfade.wav fade 5 [fade-in position HH:MM:SS] 2:00 [fade out start HH:MM:SS]
~~~
- You can also set fade in and out times automatically by calculating the duration of the file using soxi
- Optionally, you can also specify the type of fade (q for quarter of a sine wave, h for half a sine wave, t for linear (‘triangular’) slope, l for logarithmic, and p for inverted parabola. The default is logarithmic.)
- In **Terminal** type: 
~~~shell
sox stormtrim.wav stormtrim2.wav fade t 5 $(soxi -d stormtrim.wav) 5
~~~ 
#### Synthesize Sound
- Sox can also be used to synthesize sound waves (sine, square, triangle, sawtooth, trapetz (trapezoidal), exp (exponential), whitenoise, pinknoise, and brownnoise)
~~~shell
sox -n sine.wav synth 1.0 sine  1000.0
~~~ 
