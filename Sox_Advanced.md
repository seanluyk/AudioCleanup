## Exercise 2: SoX Advanced

Batch Processing

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

- Save File as cleanSound.sh

### 3.1 Execute Script on Multiple Files

- In Terminal, navigate to the archive folder
~~~shell
cd /Users/chelseamiya/Desktop/archive
~~~
- Create a new folder called "cleanFiles"
~~~shell
mkdir cleanFiles
~~~
- Navigate to the folder with the files you want to process
~~~shell
cd radio
~~~
- Paste the following code into Terminal and hit enter:
~~~shell
for i in *.wav; do ./cleanSound.sh "${i}" cleanFiles/"${i}"; done
~~~
