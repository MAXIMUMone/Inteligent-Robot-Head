# 🍰 Animatronic Head (Powered by Local LLM)

> *"It's hard to overstate my satisfaction."* An autonomous, animatronic robot head inspired by GLaDOS from Portal. Powered by a Raspberry Pi 5 and an Arduino, this robot can actively track faces, listen to voice commands, and respond audibly using a locally hosted Large Language Model (LLM) configured with a GLaDOS personality(Portal Game).

## ✨ Key Features
* **Vision & Tracking:** Actively detects and tracks human faces in its field of view.
* **Animatronics:** Smooth physical movements to follow targets, controlled via Arduino.
* **Conversational AI:** Runs a local LLM entirely on the edge (Raspberry Pi 5) for privacy and zero-latency thinking.
* **Voice Interaction:** Speech-to-Text (STT) for hearing prompts and Text-to-Speech (TTS) for replying with that classic, sarcastic robotic tone.

## 🛠️ Hardware Stack
* **Compute:** Raspberry Pi 5 8Go RAM (handles the LLM, camera processing, and audio).
* **Microcontroller:** Arduino (handles motor control and real-time hardware execution).
* **Actuation:** 3 MG996R servos for all 3D head rotations and a PCA9685 motor pilote.
* **Sensors & I/O:** Web camera, Module Respeaker Lite, and a HP8R3W speaker.
* **Structure:** 3D printed parts and some metalic ones (axle and head supports).

## 💻 Software Stack
* **AI / LLM:** Using Ollama qwen 2.5 for the LLM and speach to text + text to speach neuronal networks, all running localy.
* **Vision:** Small image analyser for faces, running localy.
* **Languages:** Python (Raspberry Pi logic & AI) and C (Arduino motor control).
* **Communication:** Serial communication over USB between the Pi and Arduino.

## ⚙️ How It Works
1. The **Camera** feeds video to the Raspberry Pi, which uses computer vision to calculate the coordinates of any faces.
2. The Pi sends target coordinates via Serial to the **Arduino**, which calculates the kinematics and moves the motors to keep eye contact.
3. Simultaneously, the **Microphone** listens for speech. When detected, it converts the audio to text and feeds it to the **Local LLM**.
4. The LLM generates a sarcastic, GLaDOS-style response, which is converted back to audio and played through the **Speaker**.

## 🚀 Future Improvements
* [ ] Finalise the look of the robot.
* [ ] Optimize the local LLM for faster token-generation speed.
* [ ] Add emotion-based movements (e.g., erratic movement when "angry").

---
*Created by MAXIMUMone 
