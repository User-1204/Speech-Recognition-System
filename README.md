# Speech-Recognition-System

*COMPANY*: CODTECH IT SOLUTUIONS

*NAME*: MAKWANA SAKSHI M

*INTERN ID*: C0DF93

*DOMAIN*: ARTIFICIAL INTELLIGENCE MARKUP LANGUAGE

*DURATION*: 4 WEEKS

*MENTOR*: NEELA SANTHOSH


## 📌 Introduction
Speech recognition enables computers to convert spoken language into text, facilitating applications such as **virtual assistants, automated transcription, accessibility tools, and hands-free control systems**.  

This project leverages Python’s `speech_recognition` library to process audio input and transcribe speech efficiently. It supports both **live microphone input** and **pre-recorded audio files**, making it a versatile tool for various real-world applications.

## 🔧 System Overview  

### **Workflow:**  
1. **Audio Input** – Accepts either real-time microphone input or a `.wav` file.  
2. **Noise Adjustment** – Dynamically reduces background interference using `adjust_for_ambient_noise()`.  
3. **Speech Processing** – Utilizes Google’s Speech Recognition API to transcribe speech accurately.  
4. **Text Formatting** – Implements `regex` to enhance readability and structure output effectively.  
5. **Error Handling** – Detects file-related issues, speech recognition failures, and API errors, providing informative user feedback.  

### **Implementation Example:**  
```python
import speech_recognition as sr  
import re  

recognizer = sr.Recognizer()  

with sr.AudioFile("your_audio_file.wav") as source:  
    recognizer.adjust_for_ambient_noise(source)  
    audio = recognizer.record(source)  

    try:  
        text = recognizer.recognize_google(audio)  
        formatted_text = re.sub(r'(?<=\.) ', '\n', text)  
        print("Transcribed Text:\n", formatted_text)  
    except sr.UnknownValueError:  
        print("Speech Recognition could not understand the audio.")  
    except sr.RequestError:  
        print("Error requesting results from Google API.")  
```  

## 🚀 Key Features:  
- **Accurate Speech-to-Text Conversion** – Processes spoken language efficiently.  
- **Multi-Input Support** – Works with live speech and pre-recorded audio files.  
- **Automatic Noise Reduction** – Improves transcription accuracy in varied environments.  
- **Robust Error Handling** – Provides detailed messages for debugging and troubleshooting.  
- **Lightweight & Efficient** – Optimized for performance with minimal dependencies.  

## 🛠️ Installation & Setup: 

### **Prerequisites:**  
Ensure the following are installed:  
- Python **3.7 or later**  
- **Jupyter Notebook** (optional but recommended)  

### **Install Dependencies:**  
To set up the required libraries, run:  
```bash
pip install SpeechRecognition pyaudio
```

> **Troubleshooting:** If `pyaudio` fails to install, download the precompiled `.whl` file from [this source](https://www.lfd.uci.edu/~gohlke/pythonlibs/#pyaudio) and install manually:  
```bash
pip install path-to-downloaded-file.whl
```

## 📚 Troubleshooting & Common Issues: 

### **Issue:** Speech is not recognized or produces incorrect results  
-Ensure a **clear audio input**, as excessive background noise can impact accuracy.  
-Adjust ambient noise using:  
```python
recognizer.adjust_for_ambient_noise(source)
```

### **Issue:** Google API returns `RequestError`  
-Verify internet connectivity.  
=Consider **offline speech recognition models** like `pocketsphinx` if necessary.  

### **Issue:** `pyaudio` installation fails  
-Try using administrator privileges (`pip install pyaudio --user`).  
-Manually install precompiled `.whl` files if needed.  

## 📜 License:  
This project is available under the **MIT License**, granting permission for free use, modification, and distribution.  


## 📤 Output:
![Image](https://github.com/user-attachments/assets/50db4714-dcb1-4170-ae29-0bf8385184df)
