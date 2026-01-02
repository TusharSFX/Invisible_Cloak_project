================================================================================
                                INVISIBLE CLOAK
================================================================================

PROJECT OVERVIEW
----------------
This project recreates the "Invisibility Cloak" effect using Python and OpenCV. 
It works by capturing a static background frame and then replacing any red pixels
in the live video feed with pixels from that background, creating the illusion 
of transparency.

================================================================================
                            INSTALL DEPENDENCIES
================================================================================

To run this project, you need Python installed on your machine along with specific
libraries.

1. Open your terminal or command prompt.
2. Navigate to the project directory.
3. Run the following command to install the required libraries:

   pip install opencv-python numpy

   (Alternatively, if you have a requirements.txt file, run: pip install -r requirements.txt)

Required Libraries:
- opencv-python: For video capture and image processing.
- numpy: For matrix operations and array handling.
- time: Standard Python library (pre-installed) for handling delays.

================================================================================
                                 HOW TO RUN
================================================================================

1. PREPARATION:
   - Place your laptop/webcam on a stable surface. It must not move.
   - Have a red cloth ready (or the color you configured).
   - Ensure the lighting is good and consistent.

2. EXECUTION:
   - Run the script using Python:
     python main.py

3. INITIALIZATION (IMPORTANT):
   - When the script starts, it will print "Camera warming up...".
   - IMMEDIATELY move out of the camera frame.
   - The camera will take a few seconds to warm up and capture the background.
   - Wait until you see "Background captured" in the console.

4. USAGE:
   - Once the background is captured, enter the frame with your red cloth.
   - Hold the cloth in front of you. The red parts will disappear, revealing
     the background behind you.
   - Press 'q' on your keyboard to stop the program and save the video.

5. OUTPUT:
   - The video will be saved as 'output.avi' in the same folder.

================================================================================
                                HOW IT WORKS
================================================================================

The logic relies on Color Segmentation and Masking:

1. Background Capture: 
   The program stores a static image of the background (without you) at startup.

2. Color Detection (HSV): 
   Each frame is converted from BGR (Blue-Green-Red) to HSV (Hue-Saturation-Value).
   HSV is preferred because it separates color (Hue) from brightness (Value),
   making detection more robust against shadows.

3. Masking:
   - Mask 1: Identifies all pixels falling within the "Red" color range.
   - Mask 2: Inverts Mask 1 to identify everything that is NOT red.

4. Segmentation & Merging:
   - The "Red" area is filled with pixels from the saved Background image.
   - The "Non-Red" area is filled with pixels from the current live frame.
   - These two are combined to create the final "invisible" effect.

================================================================================
                                CUSTOMIZATION
================================================================================

Adjusting for Different Colors:
If you don't have a red cloth, you can use blue or green. You must change the
HSV range values in the code.

Example for BLUE cloth:
Replace the 'lower_red' and 'upper_red' arrays with:
   lower_blue = np.array([100, 150, 0])
   upper_blue = np.array([140, 255, 255])

Adjusting Sensitivity:
If parts of the cloth aren't disappearing, try lowering the Saturation (middle value)
in the lower_red array (e.g., change 120 to 100).

================================================================================
                                   LICENSE
================================================================================

MIT License

Copyright (c) 2026

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
