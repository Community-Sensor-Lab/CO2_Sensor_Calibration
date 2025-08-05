# CO2 Sensor Calibration and Testing

---

## Overview

This repository contains Arduino code for setting up, calibrating, and continuously reading data from **Sensirion SCD30** and **SCD4x (SCD40/41)** CO2 sensors. The primary goal of this project is to provide a flexible framework for accurately calibrating these sensors using an external reference (like an LI-850 CO2 analyzer) and then monitoring their performance. The code includes functionalities for configuring various sensor parameters and performing forced recalibration.

## Project Goal

The main objective is to enable precise calibration and continuous measurement of CO2 concentration, temperature, and humidity using either the SCD30 or SCD4x series of sensors. This is achieved by allowing users to interactively set sensor parameters and perform forced recalibration against a known CO2 reference.

## Sensors Supported

* **SCD30:** A high-accuracy CO2, temperature, and humidity sensor.
* **SCD4x (SCD40/41):** A compact CO2, temperature, and humidity sensor.

## Key Functionalities & Parameters

The project provides interactive setup and continuous reading for both sensor types:

### For SCD30 Sensor:

* `void scd30Setup()`:
    * Initializes the SCD30 sensor.
    * **Measurement Interval:** Configurable rate at which measurements are taken (2-1800 seconds).
    * **Ambient Pressure Offset:** Allows setting an offset (700-1400 mBar) to compensate for ambient pressure variations.
    * **Altitude Offset:** Sets an altitude offset in meters above sea level. This overrides pressure offset.
    * **Temperature Offset:** Configurable temperature offset in hundredths of a degree Celsius.
    * **Forced Recalibration:** Prompts the user to input a reference CO2 value (400-2000 ppm) from an external source (e.g., LI-850) to force sensor recalibration. This value is stored in non-volatile memory.
    * **Automatic Self-Calibration (ASC):** Reports if ASC is enabled or disabled.
