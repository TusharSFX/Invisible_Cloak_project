# Invisible_Cloak_project
# 🧙‍♂️ Invisible Cloak (OpenCV)

A computer vision project that recreates the "Invisibility Cloak" effect from Harry Potter using Python and OpenCV. This script captures a background scene and replaces specific colored pixels (e.g., a red cloth) in real-time with the saved background, creating the illusion of transparency.

## 📋 Table of Contents
- [Demo](#-demo)
- [Features](#-features)
- [Prerequisites](#-prerequisites)
- [Installation](#-installation)
- [How to Run](#-how-to-run)
- [How It Works](#-how-it-works)
- [Customization](#-customization)

## 🎥 Demo
*(Optional: Add a GIF or screenshot of your project here to make your repo stand out!)*

## ✨ Features
- **Real-time processing**: Works instantly with a standard webcam.
- **Dynamic Resolution**: Automatically detects and adapts to your camera's resolution.
- **Noise Removal**: Uses morphological operations (Open/Dilate) to clean up the mask and remove jitter.
- **Video Recording**: Automatically saves the output as `output.avi`.

## ⚙️ Prerequisites
- Python 3.6+
- A webcam
- A distinct red cloth (or any solid red object)

## 📦 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/invisible-cloak.git
   cd invisible-cloak
