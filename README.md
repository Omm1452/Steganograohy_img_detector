
🕵️‍♂️ Steganography Detector
A simple GUI-based tool to detect hidden messages in image files using Least Significant Bit (LSB) steganography analysis. Built with Python, OpenCV, and Tkinter.

🔍 Features
. Detects potential hidden data using LSB analysis on grayscale images.

. Simple graphical user interface (GUI) to select images.

.Supports common image formats: .png, .jpg, .jpeg, .bmp.

🧠 How It Works
The tool converts the selected image to grayscale and examines the distribution of the least significant bits (LSBs) of each pixel. If the number of 0s and 1s is nearly balanced, it suggests potential hidden data.


