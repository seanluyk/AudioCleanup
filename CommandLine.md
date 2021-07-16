## Exercise 1: Intro to Command Line

### 1.1 Open Terminal

On Mac
1) Hit Cmd + spacebar (to open search)
2) Search “terminal.”
3) Open the Terminal app.


### Terminal Commands: Quick Guide
| Command      | Action |
| ----------- | ----------- |
| pwd    | show directory you are currently located in   |
| ls   | list files in current directory  |
| cd [file path]   | change directories <br/> e.g. “cd Documents”   |
| cd -   | navigate to previous directory |
| ~/   | navigate from root directory  <br/> e.g. “cd ~/Desktop/SoundFiles”  |
| mkdir [folder name]   | create folder  <br/> e.g. “mkdir SoundFX”  |
| mv [file name/location] [new filename/location]   | move file location and/or change file name <br/> e.g. “mv old.wav /SoundFX/new.wav” |
| up/down arrow   | scroll through previous commands |
  



### 1.2 Show the directory (folder) you are currently located in

~~~shell
pwd
~~~


### 1.3 List files in current directory

~~~shell
ls
~~~

### 1.4 Navigate to the folder that contains the sound files you want to work with

~~~shell
cd ~/Desktop/archive
~~~

### 1.5 List files in the archive folder

~~~shell
ls
~~~

### 1.6 Rename file

~~~shell
mv bbc_rain---rai_nhu0506113 rain.wav
~~~

**TIP: Drag the file from Finder into Terminal to insert the file name/path.
That way, you don't have to type it out by hand!


### 1.7 Create folder

~~~shell
mkdir soundfx
~~~

### 1.8 Move files into folder

~~~shell
mv rain.wav /soundfx/rain.wav
~~~
