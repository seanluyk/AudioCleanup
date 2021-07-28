## Exercise 2: SoX Advanced

## Batch Processing

### 3.1 Adjusting Settings
You will need to tweak settings depending on the quality of the clip (e.g. noisy vs clean).
For best results, test and adjust the settings for a single clip in a collection before executing on the entire batch.

### 3.1 Create script
- Open TextEdit on Mac (or any text editor)
- Click File > New
- Choose Format > Make Plain Text
- Paste the following code into file:
~~~shell
#!/bin/bash

WAV_IN=$1
WAV_OUT=$2

sox -S $WAV_IN $WAV_OUT silence 1 0.1 0.1% reverse silence 1 0.1 0.1% reverse
~~~
- The "silence" tool has three elements: [position in clip] [length of silence] [percentage of volume that "counts" as silence]
  - BONUS QUESTION: Can you "read" the command above? Is there anything you don't recognize?
- Save File as cleanSound.sh

### 3.1 Execute Script on Multiple Files

- In <b>Terminal</b>, navigate to the archive folder
~~~shell
cd /Users/chelseamiya/Desktop/soxArchive
~~~
- Create a new folder called "cleanFiles"
~~~shell
mkdir cleanFiles
~~~
- Navigate to the folder with the files you want to process
~~~shell
cd radio
~~~
- Paste the following code into <b>Terminal</b> and hit enter:
~~~shell
for i in *.wav; do ../cleanSound.sh "${i}" ../cleanFiles/"${i}"; done
~~~
  - BONUS QUESTION: Can you "read" the command? Is there anything you don't recognize? What do the two dots mean?
  - How would you execute this command on a single file?

<b>*Note: Permission Errors</b>
- You may encounter a permission error when trying to execute the script.
- To give permission to execute the script in the file, type “chmod +x [filepath/name]” into <b>Terminal</b> and hit enter:

~~~shell
chmod +x ../cleanSound.sh
~~~


## Other Features

### 4.1 Reduce file size

~~~shell
sox in.wav -r 48k out.wav remix 1,2
~~~
- This initiates sox (sox), opens the file (in.wav), lowers the audio sample rate to 48k (-r 48k), writes to the new file (out.wav), and converts from stereo to mono (remix 1,2)
