# Experiment-5--Implementation-of-Speech-Recognition

## Aim:
 Construct a python program to implement speech recognition.
## EQUIPMENTS REQUIRED:
Hardware – PCs
Anaconda – Python 3.7 Installation / Google Colab /Jupiter Notebook
## Algorithm:
Step 1:Import the speech_recognition module as sr.<br>
Step 2:Assign a string variable "file" with the name of the audio file that you want to transcribe.<br>
Step 3:Create an instance of the Recognizer class called "r".<br>
Step 4:Use the AudioFile() method of sr to create an AudioFile object with the audio file name passed as an argument.<br>
Step 5:Use the record() method of r to read the audio data from the AudioFile object and store it in the variable "audio".<br>
Step 6:Use the recognize_google() method of r to transcribe the audio data stored in the "audio" variable.<br>
Step 7:Print the transcribed text on the console if the transcribe process was successful.<br>
Step 8:Handle any potential errors during the transcribing process. If the audio is not clear, print "not clear". If there's an error while trying to retrieve the transcribed text from the Google speech recognizer, print "Couldnt get results from google speech recognizer".<br>

## Program:
```
import speech_recognition as sr

# Assign a string variable "file" with the name of the audio file that you want to transcribe.
file = "Voice.wav"

# Create an instance of the Recognizer class called "r".
r = sr.Recognizer()

# Use the AudioFile() method of sr to create an AudioFile object with the audio file name passed as an argument.
with sr.AudioFile(file) as source:
    audio = r.record(source)

# Use the recognize_google() method of r to transcribe the audio data stored in the "audio" variable.
try:
    text = r.recognize_google(audio)
except sr.UnknownValueError:
    print("Not clear")
except sr.RequestError as e:
    print("Couldn't get results from Google Speech Recognition service; {0}".format(e))

# Print the text in the next lines.
for line in text.splitlines():
    print(line)
```

## Output:
![image](https://github.com/Harshini1331/Experiment-5--Implementation-of-Speech-Recognition/assets/75235554/5843f413-e914-4cc8-b0eb-ad403de44a75)

## Result:
Thus, we have implemented a program that will transcribe the audio file in the file variable and print the transcribed text on the console, one line at a time.
