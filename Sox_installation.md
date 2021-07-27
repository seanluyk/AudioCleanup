## SoX Installation Options
### Linux/Mac
The easiest way to install SoX in these environments is using [Homebrew](https://brew.sh/):
- Open **Terminal**
  - Hit Cmd + spacebar (to open search)
  - Search “terminal.”
  - Open the Terminal app.
<img width="264" alt="Screen Shot 2021-07-27 at 4 42 26 PM" src="https://user-images.githubusercontent.com/13421476/127237775-d99b3f6e-8bb9-4dfa-8137-1c3493b787ce.png">

- A window (the Terminal "shell") will pop-up that looks something like this:
<img width="499" alt="Screen Shot 2021-07-27 at 4 53 31 PM" src="https://user-images.githubusercontent.com/13421476/127237815-c315e6bc-8f3a-472a-9b83-84d68ef9b8bc.png">


- Install **Homebrew**
  - In <b>Terminal</b>, copy and paste the following text and hit Enter:
~~~shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
~~~
- Install **SoX**

  - After Homebrew has finished installing, copy and paste the following text and hit Enter:
~~~shell
brew install sox
~~~
### Windows
- Install the executable file from [SourceForge](https://sourceforge.net/projects/sox/files/sox/14.4.2/)
- If you're not familiar with using the command prompt in Windows, refer to these [instructions for using SoX in Windows](https://courses.cs.washington.edu/courses/cse373/12sp/homework/1/soxusage.txt)
