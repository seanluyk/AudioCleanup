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
| mv [file name/path] [new file name/path]   | move file location and/or change file name <br/> e.g. “mv old.wav /SoundFX/new.wav” |
| up/down arrow   | scroll through previous commands |
  



### 1.2 Show the directory (folder) you are currently working in
- In <b>Terminal</b> type:
~~~shell
pwd
~~~

- This <i>prints</i> your current working directory. It is like map ("You are HERE") that shows you where you are located in your file system at a given moment.
- The pwd command is useful because when working with files in Terminal, you need to give the computer instructions based on your current location.
- It will return something like this:

<img width="414" alt="Screen Shot 2021-07-27 at 1 41 26 PM" src="https://user-images.githubusercontent.com/13421476/127217431-398b7c90-a35f-4530-877a-5aef1c93751f.png">


### 1.3 List files in current directory
- In <b>Terminal</b> type:
~~~shell
ls
~~~
- This <i>lists</i> the files in the folder where you are located.
- You can even see "hidden" files by typing "ls -a"

### 1.4 Navigate to the folder that contains the sound files you want to work with
- In <b>Terminal</b> type:
~~~shell
cd ~/Desktop/SoX-Archive
~~~
- This changes directory or <i>moves</i> you into a new folder using the directions you provide.
- You can also move up one level by typing "cd .."
- You can also navigate to the previous directory (i.e. go back) by typing "cd -"

### 1.5 List files in the archive folder
- In <b>Terminal</b> type:
~~~shell
ls
~~~
- Now you should see the files in our corpus.

<img width="582" alt="Screen Shot 2021-07-27 at 1 33 37 PM" src="https://user-images.githubusercontent.com/13421476/127216916-b2baa327-9b9a-4c2a-9a7c-ef5c59cf65b0.png">


### 1.6 Rename file
- In <b>Terminal</b> type:
~~~shell
mv bbc_rain---rai_nhu0506113 rain.wav
~~~
- This command is used to <i>rename</i> and <i>move</i> files.
- The file is now named "rain.wav" (much easier to remember!)

**TIP: To automatically insert the file name/path, click and drag the file from Finder into Terminal.

- You can also <i>copy</i> files by typing "cp [file name/path] [new path]"
- You can then <i>delete</i> the file by typing "rm [file name/path]"

  
### 1.7 Create folder
- In <b>Terminal</b> type:
~~~shell
mkdir soundfx
~~~
- This <i>creates a new folder</i>, which we've named "soundfx"
  
### 1.8 Move files into folder
- In <b>Terminal</b> type:
~~~shell
mv rain.wav /soundfx/rain.wav
~~~
- This <i>moves</i> our sound file called "rain.wav" into the folder "soundfx"

### 1.9 Scroll through previous commands
- In <b>Terminal</b>, use the up/down arrows to scroll through your command history
- Execute previous commands by hitting Enter (saving you time!)
- You can also wipe the Terminal window clean by typing "clear"

**TIP: Even after you have "cleared" the Terminal screen, you can still scroll through previous commands
