# FPGA-Based-RGB-LED-Mood-Lighting-System
(Digital Systems Design and Lab Project)

📌 Project Overview

This project implements an FPGA-based RGB LED mood lighting system that allows users to create various lighting effects by independently controlling the brightness of Red, Green, and Blue LEDs.

The system uses PWM (Pulse Width Modulation) to control LED brightness in discrete levels, enabling smooth and intuitive color mixing. Users can select colors and adjust brightness through hardware buttons and switches, while the current state is displayed via a 7-segment display.

<img width="1137" height="636" alt="image" src="https://github.com/user-attachments/assets/28e2e963-0d20-4393-9662-5ed3b9cd16c4" />


🎯 Key Features

Independent brightness control for R / G / B LEDs

5-level brightness control (Level 0 ~ 4)

Support for:

Single color mode (1 Color)

Dual color mixing (2 Color)

Full RGB mixing (3 Color)

Real-time brightness adjustment using push buttons

Visual feedback using 7-segment display

Fully synchronous digital design on FPGA

🛠️ System Architecture
1. Brightness Control Method

PWM (Pulse Width Modulation) is used to adjust LED brightness

Brightness is determined by the duty cycle

Higher duty cycle → brighter LED

Lower duty cycle → dimmer LED

Brightness levels are mapped using a ROM-based duty cycle table

2. User Inputs

RGB Selection Switch (sw_rgb[2:0])

sw_rgb[0] → Red

sw_rgb[1] → Green

sw_rgb[2] → Blue

Push Buttons

btn_up : Increase brightness

btn_down : Decrease brightness

Reset

Initializes all RGB brightness levels to 0

3. Output Components

RGB LED (PWM controlled)

7-Segment Display

Displays selected color and brightness level (0–4)

🧩 Module Description
Data Path

PWM_counter

counter_20ms

ROM_n

Seg7_ascii

Main_led_brightness_control_PWM

Control Path

Top_button

Selection_counter

Top_pwm_control

top_debounce / sm_debounce

Synchronizer

lev_puls_conv

🔁 Finite State Machine (FSM)
State	Description
INIT	Initialize RGB brightness to 0
COLOR_SELECT	Select R / G / B channel
BRIGHT_UP	Increase selected color brightness
BRIGHT_DOWN	Decrease selected color brightness
UPDATE_PWM	Update PWM duty cycle using ROM
👩‍💻 Contributors

Jiyoon Kim – Block Design & Testbench

Yuna Oh – Block Design & Testbench
