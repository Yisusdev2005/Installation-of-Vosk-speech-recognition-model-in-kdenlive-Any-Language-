# Installation-of-Vosk-speech-recognition-model-in-kdenlive-Any-Language-
Installation process for Vosk and some Python modules using pip, and bug fixes when testing the speech recognition model. 

# First Step
The first step is to install the voice recognition model for the language of your choice from the official Alpha Cephei website: 
> https://alphacephei.com/vosk/models

# Second Step
Open Kdenlive and go to the bar at the bottom of the screen under `Project` and click there:
> Project ‣ Subtitle ‣ Add Subtitle ‣ Voice recognition

<img src="https://github.com/Yisusdev2005/Installation-of-Vosk-speech-recognition-model-in-kdenlive-Any-Language-/blob/main/1.jpeg" width="80%"/>

Click there

<img src="https://github.com/Yisusdev2005/Installation-of-Vosk-speech-recognition-model-in-kdenlive-Any-Language-/blob/main/2.jpeg" width="80%"/>

# Third Step
Now, you must check the `Custom model folder` box and paste the directory of the same kdenlive configuration folder (in $USER it should be the name of your current session) so that the speech recognition model integrates better:
> /home/$USER/.local/share/kdenlive

<img src="https://github.com/Yisusdev2005/Installation-of-Vosk-speech-recognition-model-in-kdenlive-Any-Language-/blob/main/3.jpeg" width="80%"/>

# Fourth step
Once here, drag the downloaded `.zip` file of the model into the empty space below and wait a few moments until it has uploaded, then close everything:

![til](https://github.com/Yisusdev2005/Installation-of-Vosk-speech-recognition-model-in-kdenlive-Any-Language-/blob/main/Preview.gif)

# Fifth Step
You will need to install these Python modules (required) on your system:
> sudo apt install python3-pip python3-venv python3-srt python3-pysrt python3-setuptools

Then, go to the Kdenlive directory: `/home/$USER/.local/share/kdenlive`
And here you must create a virtual or Python development environment (Use the `pwd` command to find out the full path of the directory if you are already in it from the file manager) to install the “Vosk” recognition model with this command:
> python3 -m venv /home/$USER/.local/share/kdenlive

Once all this is done, all that remains is to activate the environment and install the modules with pip for voice recognition:
> source /home/$USER/.local/share/kdenlive/bin/activate
> pip install srt srt-equalizer vosk setuptools

# Sixth Step
We're almost done setting everything up, but keep in mind that if you close everything and open the program, it won't work because the environment is disabled and it won't recognize Vosk.

So let's create a bash script to automate everything, from activating the environment created with the installed modules to running Kdenlive.

- First, let's use nano to create a .sh file in any directory we want:
  
  > cd Documentos/
  
  > nano kdenlive_venv.sh
  
- Here we are going to paste the following content into the `.sh` file already created with nano:

<pre>#!/bin/bash

#The kdenlive directory path
VENV_PATH="/home/$USER/.local/share/kdenlive"

#The command to activate the environment
source "$VENV_PATH/bin/activate"

#The command for execute kdenlive
exec kdenlive</pre>

- You give permissions with execution using `chmod`:
  
> chmod +x kdenlive_venv.sh

- Finally, we just go to the dkenlive `.desktop` file or executable file, open it with nano or whatever text editor you have installed, find the `Exec` line, and replace it with the `.sh` file we just created on nano:
  
  > Exec=full/path/to/script/kdenlive_venv.sh %U

And that's it! Kdenlive is now ready to automatically subtitle your audio tracks :)
