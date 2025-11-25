# Installation-of-Vosk-speech-recognition-model-in-kdenlive-Any-Language-
Installation process for Vosk and some Python modules using pip, and bug fixes when testing the speech recognition model. 

# First Step
The first step is to install the voice recognition model for the language of your choice from the official Alpha Cephei website: 
> https://alphacephei.com/vosk/models

# Second Step
Open Kdenlive and go to the bar at the bottom of the screen under “Project” and click there:
> Project ‣ Subtitle ‣ Add Subtitle ‣ Voice recognition
<img src="https://github.com/Yisusdev2005/Installation-of-Vosk-speech-recognition-model-in-kdenlive-Any-Language-/blob/main/1.jpeg" width="80%"/>
Click there
<img src="https://github.com/Yisusdev2005/Installation-of-Vosk-speech-recognition-model-in-kdenlive-Any-Language-/blob/main/2.jpeg" width="80%"/>

# Third Step
Now, you must check the “Custom model folder” box and paste the directory of the same kdenlive configuration folder (in $USER it should be the name of your current session) so that the speech recognition model integrates better:
> /home/$USER/.local/share/kdenlive
<img src="https://github.com/Yisusdev2005/Installation-of-Vosk-speech-recognition-model-in-kdenlive-Any-Language-/blob/main/3.jpeg" width="80%"/>

# Fourth step
Once you get here, drag the downloaded `.zip` file of the model into the empty space below:
