# IQ_SDR
The goal of this project was to design a software defined radio (SDR) reciever that operated in the range of _______ to _______ MHz. This project was conducted with my partner Cayden Maddocks as part of Walla Walla University's Electronics II course.
## Design Goals
The following design objectives were given for this project as part of the course syllabus:
1. Minimum discernible signal less than 1uV
2. Visible image rejection through quisk
3. Low noise figure
4. Low Cost ($25 budget)
Cayden Maddocks and I set additional design obectives in order to aid in the design process:
1. Operate in a Frequency Range of ________
2. Modulation Type:
3. Size of 10 cm by 10 cm
4. Weight of less than 2 pounds
5. Power Requirement of 5V
## Overview
The Software Defined Radio (SDR) reciever has three ports: antenna, USB, and audio jack. The input from the antenna gets filtered, mixed, and then the desired signal is then amplified. The input from the USB to the Raspberry Pi Pico powers the radio and operates the oscillator. The audio jack is connected to a sound card that is attached to a computer where the software demodulates the signal into recognizable audio. Mixing is accomplished via the Raspberry Pi Pico, with ported arduino code from Dr. Rob Frohne. This code interacts with Quisk, a software that controls the reciever through the Raspberry Pi. Quisk should allow the radio to be tuned to certain frequency but this was not accomplished due to issues from porting the arduino code over to the Raspberry Pi Pico. The total cost of this project was about ____.
# SDR Block Diagram
![Circuit Block Diagram](/images/Diagrams/SDRRecieverBlockDiagram.png)
# Version 6 Design
![Version 6 Design](/images/Schematics/SDRRecieverSchematic.png)
Shown above is the design schematic for the SDR. More details will be given down below about each section of the schematic. This includes a 12MHz BandPass Filter, Tayloe Mixer, Oscillator, Voltage Smoother, LM4562MA Power Supply, and a Multiple Feedback Lowpass Filter and Amplifier.\
## Bandpass Filter
![Bandpass Filter](/images/Schematics/SDR_BandPass_Filter.png)
Shown above is a 7-12MHz, 3rd order, series first, Butterworth, bandpass filter. The above filter was designed using the LC Filter Design Tool found here: https://rf-tools.com/lc-filter/
## DC Voltage Offset
![Voltage Smoother](/images/Schematics/SDR_Voltage_Smoother.png)
In order to limit noise into our radio a 5V voltage smoother was used before entering t
## Oscillator
![Oscillator](/images/Schematics/SDR_Oscillator.png)
For the design of our radio we used a Si5351A-B-GT Oscillator.
## Tayloe Mixer and Multiple Feedback Lowpass Filter and Amplifer
![Tayloe Mixer](/images/Schematics/SDR_TayloeMixer.png)
The SDR uses a SN74CBT3253 Tayloe Mixer that leads into a Multiple Feedback Lowpass Filter and Amplifer. The amplifier employs the use of two LMH4562MA op amps, and has a cutoof frequency around 100kHz.
## Raspberry Pi Pico
![Raspberry Pi Pico](/images/Schematics/SDR_Raspberry.png)
Shown above is the Raspberry Pi Pico and the pins used to drive the SDR.
# Multiple Feedback Amplifier Simulation
![Amplifier LTSpice](/images/Schematics/MultipleFeedbackAmplifier.png)
![Amplifier LTSpice Simulation](/images/Schematics/MultipleFeedbackAmplifierSimulation.png)
Shown here is an LTSpice simulation for our Multiple Feedback Amplifier. The simulation shows the amplifier's response between 100Hz to 100MHz.
# PCB Design
![PCB Design](/images/Schematics/PCB_Design.png)
The board shown above was sourced from JLCPCB. Certain design principles were taken into consideration when coming up with the initial design of the board, such as:
# Board Build Up Plan
- NEEDS TO BE ADDED
# Quisk Setup
Quisk was downloaded from http://www.james.ahlstrom.name/quisk/ on to a laptop was able to be loaded onto the Raspberry Pi Pico. Quisk was then configured to operating on COM3, the respective port that communicated with the Raspberry Pi. Upon opening Quisk, a new SoftRock Fixed Radio was created and configured to use the appropriate sound card input. The hardware file path was also changed to quisk_conf_openradio.py to use the code that was ported from Dr. Frohne's orignial arduino code.
# Results
![Final Results](/images/Schematics/Final_Results)
Looking at the results above, image rejection can still be seen around 1 microvolt at a 10MHz frequency. This was the best image rejection that we were able to obtain. Using the antenna on top of the Kretschmar roof, we were able to obtain a clearly discernible signal from a religious radio station. Thank the Lord. 
# Credits
Huge credits go to Cayden Maddocks, my teammate who helped tremendoulsy on this project

Also thanks to Professor Rob Frohne, for without his help this project would not have been possible. 





