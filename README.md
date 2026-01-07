# ASCII Art Generator (Manual BMP Parser)

This project converts a **24-bit BMP image** into **colored ASCII art** using **pure Python**, without relying on image-processing libraries like PIL or OpenCV.

The core focus of this project is understanding **binary file formats**, **low-level image parsing**, and **manual image processing logic**.

---

## Features

- Manual parsing of **24-bit BMP files** (byte-by-byte)
- Correct handling of BMP headers and row padding
- Nearest-neighbor image resizing
- Terminal-aware aspect ratio correction
- ANSI true-color (24-bit RGB) output in terminal
- Optional manual color enhancement (no libraries)

---

## Requirements

- Python 3.x
- A terminal that supports **ANSI true color**
  - Works on most modern Linux terminals, macOS Terminal, Windows Terminal

---

## How It Works (High-Level)

1. Reads the BMP file header manually to extract width, height, and pixel offset
2. Reads raw pixel data in **BGR format**
3. Fixes bottom-to-top BMP storage order
4. Resizes the image using nearest-neighbor logic
5. Enhances color saturation manually
6. Prints colored ASCII characters using ANSI escape codes

---

## Usage

1. Convert any image to **24-bit BMP**
2. Rename it to `output.bmp`
3. Place it in the same directory as the script
4. Run:

```bash
python main.py
```
Configuration

You can adjust output width by changing:
```
OUTPUT_WIDTH = 150

```
Larger values produce more detailed ASCII art but require a wider terminal.
Project Structure
```
ascii-art-bmp/
│
├── main.py        # Core implementation
├── README.md      # Project documentation
└── .gitignore     # Ignored files (BMP, cache, etc.)
```
## Limitations

- Only supports 24-bit BMP images
- ASCII density mapping is not implemented (single character output)
- Performance is not optimized for very large images

---

## Why This Project Matters

This project demonstrates:

- Binary file handling
- Understanding of image storage formats
- Manual memory and pixel manipulation
- Algorithmic thinking without external dependencies

It prioritizes **fundamentals over convenience**.

---

## Future Improvements

- Brightness-based ASCII character mapping
- Support for multiple ASCII characters
- Saving output to a text file
- Performance optimizations
- Support for additional image formats
