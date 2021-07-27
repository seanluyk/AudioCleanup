## Exercise 2: SoX Basics

### 2.1 Get metadata about an audio file
- Open **Terminal**
- Navigate to your workshop audio files using the command line
- In **Terminal** type:
~~~shell
sox filename.wav -n stat
~~~
- This provides you with some very basic stats which may be useful/interesting to you
- You can also use the soxi command to get information from the file header. In **Terminal** type:
~~~shell
soxi filename.wav
~~~
 - This returns information found in the file's header (e.g. channels, bit rate, duration)
 - You can also type multiple file names after the main stat/soxi commands to get stats returned for multiple files at once for the purposes of comparison:
 ~~~shell
 soxi filename1.wav filename2.wav
 sox filename1.wav filename2.wav -n stat
 ~~~
### 2.2 Combine multiple audio files
- In SoX there are multiple methods for combining audio files, which we'll experiment with below:
#### Concatenate files
- In **Terminal** type:
~~~shell
sox --combine concatenate inputfile1.wav inputfile2.wav outputfile.wav
~~~
- Hear the result by typing:
~~~shell
play outputfile.wav
~~~
- You can stop playback by typing CTRL+C
- You can even play files back in reverse! Type:
~~~shell
play outputfile.wav reverse
~~~
#### Merge Files
- In **Terminal** type:
~~~shell
sox -m inputfile1.wav inputfile2.wav outputfile.wav
~~~ 
- This will create one file that mixes the other files together
- Let's combine rain.wav with thunder.wav to create a storm
- Using the remix command, you can also mix individual channels from multiple files together very easily, although we won't work on this today
- Play back the file you created using the merge command
### 2.3 Modify files
- SoX had many commands that allow you to easily modify files using the command line. Today we'll work with some basic ones:
#### Pad a recording with silence
- In **Terminal** type:
~~~shell
sox filename1.wav outputfile.wav \
pad [amount of silence HH:MM:SS to add at the beginning of your file] [amount of silence HH:MM:SS to add at the end of your file]  
~~~ 
#### Apply a fade in/fade out
- Similar to the pad command, the fade command can be used to add fade-ins/outs to a file:
- In **Terminal** type:
~~~shell
sox filename1.wav filename2.wav outputfile.wav \
fade [fade-in position HH:MM:SS] [fade out start HH:MM:SS]
~~~
