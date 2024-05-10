Objective: The Anti-Blinding Light System (ABLS) is aimed at enhancing road safety by preventing accidents caused by blinding high-beam headlights. Our solution automatically adjusts simulated headlights upon detecting approaching vehicles, utilizing computer vision techniques.

Components Used:

Computer Vision: We employ OpenCV to detect vehicles in video frames using a special file called "haarcascade_car.xml". This XML file contains a pre-trained model known as a Haar cascade, which is capable of recognizing car-like patterns in images.

Hardware: The system includes an 8x8 LED matrix that mimics vehicle headlights. An Arduino UNO is utilized to control this matrix based on commands from our Python script.

Communication: We establish a communication link between the Python script and the Arduino UNO using serial communication to send commands for dimming and brightening the LED matrix.

Connections:

Before starting, ensure that the "haarcascade_car.xml" file, video file, and Arduino are properly connected. Connect the Arduino UNO to your computer via a USB cable, and make sure it is recognized by the system. Connect the 8x8 LED matrix to the Arduino according to the wiring diagram provided in the project documentation. Finally, establish the serial communication between the computer and the Arduino by specifying the correct port and baud rate in the Python script.

Functionality:

The Python script retrieves frames from a video file (or a live video feed). Each frame is converted into a grayscale image to detect vehicles using the "haarcascade_car.xml" file. Upon spotting vehicles, the script instructs the Arduino to dim the LED matrix to 40% brightness to avoid glare. If no vehicles are detected, it brightens the LED matrix to full intensity for better visibility. Commands for dimming and brightening are sent via serial communication to the Arduino. Rectangles are drawn around detected cars for visualization. The process continues until the user exits by pressing 'q'.

Enhancements:

Our system aims to reduce accidents by mitigating glare from high-beam headlights, thereby making driving safer and more comfortable. Future improvements could include implementing real-time communication with vehicle headlights to dynamically adjust LED brightness based on nearby vehicles.

Note: While the current implementation of the project is designed for educational purposes and is not capable of real-time detection as it utilizes a pre-captured video, there is potential for future enhancements to enable real-time detection.
