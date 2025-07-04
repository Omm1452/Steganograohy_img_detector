# 🕵️‍♂️STEGANOGRAPHY_IMG-DETECTOR

A simple GUI-based tool to detect hidden messages in image files using Least Significant Bit (LSB) steganography analysis. Built with Python, OpenCV, and Tkinter.


---

## 🔍 Features
- Detects potential hidden data using LSB analysis on grayscale images.

- Simple graphical user interface (GUI) to select images.

- Supports common image formats: .png, .jpg, .jpeg, .bmp.

  
  ---


## 🧠 How It Works
The tool converts the selected image to grayscale and examines the distribution of the least significant bits (LSBs) of each pixel. If the number of 0s and 1s is nearly balanced, it suggests potential hidden data.


---

## 🛠️ Installation
1.Install the required packages

You can use pip:

```pip install opencv-python numpy```

Tkinter comes pre-installed with most Python distributions. If not, install it via:

- Ubuntu/Debian: sudo apt-get install python3-tk

- Windows/Mac: Usually included by default

## 🚀 Usage
Run the script using Python:

```python steganography_detector.py

This will launch a simple window where you can select an image file. The application will then analyze the image and display whether hidden data is potentially present.

---

## 📌 Dependencies

- Python 3.x

- OpenCV (opencv-python)

- NumPy

- Tkinter




## 🧪 Sample Code ('main.py')

```python
import tkinter as tk
from tkinter import filedialog, messagebox
import cv2
import numpy as np

def detect_steganography(image_path):
    """
    Detect hidden data in an image using LSB steganography detection.
    This function analyzes the least significant bits of grayscale pixel values.

    Args:
        image_path (str): Path to the image file.

    Returns:
        str: A message indicating whether hidden data is detected or not.
    """
    try:
        # Load the image
        image = cv2.imread(image_path, cv2.IMREAD_COLOR)
        if image is None:
            return "Invalid image file!"

        # Convert to grayscale
        gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

        # Extract the least significant bit (LSB) of each pixel
        lsb_image = np.mod(gray_image, 2)

        # Check for distribution of 0s and 1s in LSB
        unique, counts = np.unique(lsb_image, return_counts=True)

        if len(counts) > 1 and abs(counts[0] - counts[1]) < 0.1 * np.sum(counts):
            return "Potential hidden data detected in the image!"
        else:
            return "No hidden data detected in the image."
    except Exception as e:
        return f"Error during detection: {str(e)}"

def browse_file():
    """
    Open a file dialog to select an image file and run the steganography detector.
    """
    file_path = filedialog.askopenfilename(
        title="Select Image File",
        filetypes=[("Image Files", "*.png;*.jpg;*.jpeg;*.bmp")]
    )
    if file_path:
        result = detect_steganography(file_path)
        messagebox.showinfo("Detection Result", result)

def create_gui():
    """
    Create the GUI window for the steganography detector.
    """
    root = tk.Tk()
    root.title("Steganography Detector")
    root.geometry("300x150")

    label = tk.Label(root, text="Steganography Detector", font=("Arial", 16))
    label.pack(pady=10)

    button = tk.Button(root, text="Select Image", command=browse_file, width=20)
    button.pack(pady=20)

    root.mainloop()

if __name__ == "__main__":
    create_gui()
```

---


## 🧪 Example
When analyzing an image, you may get results such as:

- Potential hidden data detected in the image!

- No hidden data detected in the image.

  
---
