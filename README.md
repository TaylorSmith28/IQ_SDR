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
# Version 5 Design
![Version 5 Design](/images/Schematics/SDRRecieverSchematic.png)
Shown above is the design schematic for the SDR. More details will be given down below about each section of the schematic. This includes a 12MHz BandPass Filter, Tayloe Mixer, Oscillator, Voltage Smoother, LM4562MA Power Supply, and a Multiple Feedback Lowpass Filter and Amplifier.\
## 12MHz Bandpass Filter
![Bandpass Filter](/images/Schematics/SDR BandPass Filter.png)






