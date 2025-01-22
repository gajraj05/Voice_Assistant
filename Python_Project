import pyttsx3
import speech_recognition as sr
import webbrowser
import datetime
import pyjokes
import os
import time

#convert speech into text
def speech_text():
    recognizer = sr.Recognizer()
    with sr.Microphone() as source:
        print("Listening...")
        recognizer.adjust_for_ambient_noise(source)
        audio = recognizer.listen(source)
        #listening completed and printing output further
        try:
           print("Recognizing...")
           data = recognizer.recognize_google(audio)
           print(data)
           return data
        except sr.UnknownValueError:
           print(" Can't Understand")
                
#Calling the function
#speech_text()

#text speaking by the system  (text to speech)
def SpeechTOText(x):
    engine = pyttsx3.init()
    #voices(men/women)
    voices =engine.getProperty('voices')
    engine.setProperty('voice',voices[1].id)  #selecting voice of [0]->men, [1]->women
    rate =engine.getProperty('rate')  #rate is used for voice speed
    engine.setProperty('rate',160)    #we can set the speed of speaking through the number 130..
    #speak  (speaking)
    engine.say(x)
    engine.runAndWait()
#SpeechTOText(" Hello, my name is Gajraj Singh Rathore")  #this is use to speak

if __name__=='__main__':
        if "spider" in speech_text().lower():
            #Additionally added by me
            greeting = "Hello! How can I help you today?"
            SpeechTOText(greeting)
            while True:
                 #we can done our work by this below formate
                 data1=speech_text().lower()
                 
                 if "your name" in data1:
                     name = " My Name is Spider"
                     SpeechTOText(name)
                     
                 elif "old are you" in data1:
                     age = " I don't have an age in the same way that humans do. I'm a large language model, and my development is ongoing."
                     SpeechTOText(age)
                     
                 elif "time now" in data1:
                     time= datetime.datetime.now().strftime("%I%M%p")    #%I->for Hours, %M->for Min, %p->for AM/PM
                     SpeechTOText(time)
                     
                 #webbowser module
                 elif "youtube" in data1:
                     webbrowser.open("https://www.youtube.com/")
                     
                 #pyjokes module
                 elif "joke" in data1:
                     joke_1 = pyjokes.get_joke(language="en",category="all")
                     print(joke_1) 
                     SpeechTOText(joke_1)
                     
                 elif "play song" in data1:
                     add = "F:\song"
                     listsong = os.listdir(add)
                     print(listsong)
                     os.startfile(os.path.join(add,listsong[0]))
                     
                 elif "stop" in data1:
                     SpeechTOText(" OK Turning OFF ")
                     break
                 
                #  time.sleep(5)
        else:
            print("Thank You")
