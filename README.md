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

```python
import speech_recognition as sr

def transcribe_speech(file_path):
    # Create a recognizer object
    r = sr.Recognizer()

    # Load the audio file
    with sr.AudioFile(file_path) as source:
        # Read the entire audio file
        audio = r.record(source)

    try:
        # Use the recognizer to convert speech to text
        text = r.recognize_google(audio)
        return text
    except sr.UnknownValueError:
        print("Could not understand audio")
    except sr.RequestError as e:
        print("Could not request results; {0}".format(e))

# Provide the path to the MP3 file you want to convert
file_path = "kumaravelan.wav"

# Call the function to transcribe speech
transcribed_text = transcribe_speech(file_path)

# Print the transcribed text
print("Transcribed text:")
print(transcribed_text)

```
## Output:
![image](https://github.com/Kumaravel655/speech_recognition/assets/75235334/4342226c-3ab2-434e-a010-20aad31e7cbe)

## Result:
Thus, we have implemented a program that will transcribe the audio file in the file variable and print the transcribed text on the console, one line at a time.
