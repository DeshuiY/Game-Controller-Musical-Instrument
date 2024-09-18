# Game-Controller-Musical-Instrument
EP-390-002 New Musical Instrument Building
# This Instrument is based on the PS4 Game Controller
# This Instrument can be played on the Maxmsp
# For building this Instrument, I used Maxmsp Version 8.6.4
### Interaction Design

- **Planed Button Controls**:
    - The four buttons on the right side of the PS4 controller (X, O, Δ, □) are mapped to different drum sounds: 
        - X: Kick
        - O: Snare
        - Δ: Hi-hat
        - □: Tom
    - The left joystick is used to control the intensity or velocity of the sounds, allowing for dynamic sound control based on how the joystick is manipulated.

- **Motion Sensors**:
    - I initially aimed to use the PS4 controller's motion sensors (gyroscope and accelerometer) to influence sound modulation, but this feature was not fully implemented due to technical difficulties.

    - I used linear interpolation for pitch control, especially for the joystick movements. When controlling the pitch of the sine wave or the kick drum sound, the left joystick’s angle smoothly transitioned between values to create a natural modulation.

    - I experimented with exponential and logarithmic interpolation methods to control sound parameters, but I found that linear interpolation worked best for the dynamic range I wanted.

# What Went Well
The initial setup and integration of the PS4 controller into the Max environment went smoothly. I was able to map the buttons and joysticks to the respective controls without much difficulty. The kick drum sound design was successful, and the pitch control through the joystick worked as expected.

# Several persistent issues:
- **Signal Handling**: One of the biggest challenges was managing the signal from `cycle~`. Sometimes it would continuously output signals, and other times it would only respond to a bang once. This inconsistent behavior caused significant delays in development as I had to troubleshoot repeatedly. I managed to make it work for the kick drum by copying a successful portion of the patch.
- **Snare, Hi-hat, and Tom Sound Design**: I struggled to replicate the same success with the other drum sounds (snare, hi-hat, and tom). Despite repeated efforts, only the kick drum was properly functional.
- **Motion Sensors Integration**: I attempted to connect the PS4 controller's motion sensors with the `mousestate~` object, hoping to allow the user to draw a waveform by touching the screen. Unfortunately, I couldn’t get this feature to work despite reviewing Google resources and Max/MSP tutorials.
- **Waveform Selection**: I wanted to assign the left directional pad buttons on the controller to different basic waveforms (Sine, Saw, Square, Triangle) and allow pitch control via the right joystick. I was only able to successfully implement this for the sine wave.

# Learning
Despite the technical hurdles, I thoroughly enjoyed this process of learning Max/MSP and integrating it with the PS4 controller. It’s been a long time since I found myself so immersed in a project, spending hours thinking through challenges and exploring creative solutions. Although I felt limited at times due to my lack of EP-341, I was able to draw from the Max/MSP materials I studied during the holiday. When I encountered issues, researching Max’s resources often helped me find new ways to apply my knowledge, motivating me to keep learning and experimenting.



# Initialization Instructions
1. Connect my PS4 controller to my computer via USB.
2. Launch the Max patch. Setup a gamepad~
3. Ensure the controller is recognized by the patch 
4. Once recognized, I'm ready to start playing!

### How to play

- **Kick Drum**: Press the **X** button on the PS4 controller to trigger a kick drum sound. You can adjust its pitch using the **left joystick**.
- **Sine Wave Control**: Press the **left directional button** to generate a sine wave. The **right joystick** will control the pitch of the waveform.
- Further controls for other sounds (snare, hi-hat, tom) are partially functional but not fully developed.

# I believe I will do better in the upcoming courses, and having more challenges will give me even more motivation to solve them.