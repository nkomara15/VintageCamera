# Vintage Point-and-Shoot Camera

A retro-style digital point-and-shoot camera built on an ESP32-WROVER running MicroPython. Captures images via an OV2640 camera module, streams a live feed to a browser over WiFi, and stores photos to a MicroSD card — all in a portable, battery-powered enclosure inspired by vintage point-and-shoot cameras.

---

## Project Goals

- Build a fully functional digital camera using embedded hardware
- Create a retro-inspired point-and-shoot experience with a physical enclosure
- Practice embedded systems engineering with real hardware constraints
- Document the full engineering process from prototype to finished product

---

## Current Features

- ESP32-WROVER camera initialization
- Browser-based live camera stream via WiFi
- Modular MicroPython project structure

---

## Planned Features

- TFT live preview screen
- Physical shutter button with debounce logic
- SD card photo storage
- Photo counter
- Battery indicator
- Portable battery-powered operation
- Retro camera enclosure

---

## Hardware

| Component | Purpose |
|---|---|
| ESP32-WROVER | Main microcontroller |
| OV3660 Camera | Image capture |
| TFT Display | Live preview |
| Push Button | Shutter control |
| MicroSD Card | Photo storage |
| Breadboard + Jumper Wires | Prototyping |

---

## Software & Technologies

- MicroPython
- picoweb
- ESP32 Camera Firmware
- Thonny IDE
- GitHub

---

## Current Progress

### Stage 1 — Camera Foundation ✓
- Installed MicroPython firmware on ESP32-WROVER
- Connected and initialized OV2640 camera module
- Uploaded required camera libraries
- Configured and launched camera web server
- Verified live browser video stream over WiFi

### Stage 2 — Input & Storage *(in progress)*
- Add physical shutter button with debounce logic
- Save captured photos to MicroSD card

### Stage 3 — Display & UX
- Integrate TFT display for live preview
- Add photo counter and battery indicator

### Stage 4 — Enclosure & Portability
- Design and build retro camera enclosure
- Implement portable battery-powered operation

---

## Implementation Notes

- WiFi streaming uses picoweb to serve a lightweight MJPEG feed directly from the ESP32
- MicroPython's memory constraints required a modular file structure to avoid heap allocation issues during import
- Camera initialization is sensitive to firmware version — pinned to a stable build after resolving module detection issues during setup
- GPIO pin mapping required careful verification against the ESP32-WROVER datasheet to resolve early camera detection failures

---

## Challenges & How They Were Solved

| Challenge | Resolution |
|---|---|
| Camera module not detected | Resolved by reflashing firmware and verifying GPIO pin mapping against datasheet |
| Firmware installation errors | Identified correct firmware build compatible with OV3660 on WROVER variant |
| ESP32 storage limitations | Worked around with modular code structure, importing only required libraries per module |
| Library upload debugging | Established reliable upload workflow using Thonny IDE with filesystem verification |

---

## Credits

Initial ESP32 camera setup referenced the Freenove ESP32-WROVER tutorial and firmware resources.
