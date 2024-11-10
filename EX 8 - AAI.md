<H4>Aashima Nazreen S</H4>
<H4>212221240002</H4>
<H4>EX. NO.8</H4>
<H4>DATE: 21.10.24</H4>
<H1 ALIGN =CENTER>Implementation of Speech Recognition</H1>

## Aim:
 To implement the conversion of live speech to text.<BR>
## Algorithm:
#### Step 1: 
Import the speech_recognition library<Br>
#### Step 2: 
Initialize the Recognizer<Br>
#### Step 3: 
Create an instance of the Recognizer class, which will be used for recognizing speech.<Br>
#### Step 4: 
Set the duration for audio capture<Br>
#### Step 5: 
Define a variable to specify the duration (in seconds) for which the program will capture audio from the microphone.<Br>
#### Step 6: 
Display a message in the console to prompt the user to speak.<Br>
#### Step 7: 
Capture audio from the default microphone<Br>
#### Step 9: 
Use the default microphone as the audio source.<Br>
#### Step 10: 
Record audio for the specified duration using the Recognizer instance.<Br>
#### Step 11: 
Perform speech recognition with exceptional handling:<Br>
•	Attempt to recognize speech from the captured audio using the Google Speech Recognition service.<Br>
•	If successful, print the recognized text.<Br>
•	Handle specific exceptions: If the recognition result is unknown or if there is an issue with the request to the Google Speech Recognition service, print corresponding error messages.<Br>
•	A generic exception block captures any other unexpected errors.<Br>
## Program:

```python
pip install SpeechRecognition
pip install pyaudio

import speech_recognition as sr
r = sr.Recognizer()

duration = 15
print("Say something:")

with sr.Microphone() as source :
    audio_data = r.listen(source,timeout = duration)

try:
    text = r.recognize_google(audio_data)
    print("You said:", text)
except sr.UnknownValueError:
    print("Sorry, could not understand audio")
except sr.RequestError as e:
    print(f'Error with the request to Google Speech Recognition service: {e}')
except Exception as e:
    print(f'Error: {e}')
```

## Output:
![image](https://github.com/user-attachments/assets/579ff590-957b-42e9-b4fe-6a6027a1f54a)

## Result:
Thus, we have implemented a program that will transcribe the audio file in the file variable and print the transcribed text on the console, one line at a time.
