
🕵️‍♂️ Steganography Detector
A simple GUI-based tool to detect hidden messages in image files using Least Significant Bit (LSB) steganography analysis. Built with Python, OpenCV, and Tkinter.

🔍 Features
. Detects potential hidden data using LSB analysis on grayscale images.

. Simple graphical user interface (GUI) to select images.

.Supports common image formats: .png, .jpg, .jpeg, .bmp.

🧠 How It Works
The tool converts the selected image to grayscale and examines the distribution of the least significant bits (LSBs) of each pixel. If the number of 0s and 1s is nearly balanced, it suggests potential hidden data.


🛠️ Installation
1. Clone the repository

```git clone https://github.com/Omm1452/steganography-detector.git
cd steganography-detector

2. Install the required packages

You can use ```pip:
```pip install opencv-python numpy

Tkinter comes pre-installed with most Python distributions. If not, install it via:

. Ubuntu/Debian: ```sudo apt-get install python3-tk

. Windows/Mac: ```Usually included by default

🚀 Usage
Run the script using Python:

```python steganography_detector.py

This will launch a simple window where you can select an image file. The application will then analyze the image and display whether hidden data is potentially present.

📂 File Structure
steganography_detector.py     # Main script with GUI and detection logic
Uploads               # Project documentation

📌 Dependencies
. Python 3.x

. OpenCV (opencv-python)

. NumPy

. Tkinter

🧪 Example
When analyzing an image, you may get results such as:

. Potential hidden data detected in the image!

. No hidden data detected in the image.
