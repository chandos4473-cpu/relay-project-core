Welcome to the repository for my Relay Project. A hardware engineering and computer architecture project developed for the Hack Club Stardance Challenge.
This project centers around a fully functional, custom-designed 8-bit relay adder. Rather than being built around a locked, standalone device, this circuit was engineered from the ground up as a modular processor component featuring a 30 pin I/O system bus.
The core objective during this challenge is to utilize this 30 pin bus to design custom logic interfaces, level shifters and firmware that will bridge this retro mechanical architecture with modern microcontrollers.


# 1. The 8-bit relay core
   The computational core uses physical electromechanical relays to execute full 8-bit binary addition. This layout imitates the fundamental concepts of an Arithmetic Logic Unit found in almost all modern computers. This provides a tactile demonstration of low level digital logic gates

# 2. The custom 30 pin I/O bus
   To allow communication with external hardware, and other relay boards utilising the same bus, the adder breaks out all essential data, power, and control lines into a 30 pin bus interface. This layout includes pathways for:
   
   2 8-bit inputs - these are the 2 binary numbers that the relays will sum together. Labelled A0-7, and B0-7 with bit 0 being the least significant (2^0 - 1) and bit 7 being the most significant on this board (2^7 - 128).
   
   1 8-bit output and Carry - this is the final output which outputs the sum of the 2 8 bit inputs. If the final number is greater than 128, the final carry out pin will be set as high.
   
   1 Control - This pin, labelled as 'Compute' allows all relays to be turned on simultaneousely, starting the ripple adder. The adder will only perform the calculaton when BOTH Compute and VCC (5v) are high.
   
   Power rails - one VCC line and 2 GND lines are connected to a 5V power source with a current between 1.0 and 2.0 A.
   
   1 empty pin - pin 27 on the bus is not connected to anything on the addition board. This pin could be used for extra inputs if the current number does not satisfy needs in the future.

# 3. The Heirarchical Schematic

   The complex routing and page-to-page organisaton of the relay networks were designed completely within the KiCad schematic editor using heirarchical sheets

# To access this, open the schematic PDF in the repository


# Mission Roadmap and Milestone Tracking

[ ] Phase 1: Architecture Design - Complete the multi-page heirarchical schematics in KiCad

[x] Phase 2: Repository Launch - Establish open-source codebase tracking and link the repository to the Stardance Dashboard

[ ] Phase 3: Breadboard Prototyping - Interface the 30 pin I/O bus to a breadboard workspace. Ensure all relay logic works and the prototype can add 2 8-bit numbers and give a 9-bit sum

[ ] Phase 4: PCB Designing - Use KiCad to design an appropriate PCB for the relays and 30 pin bus

[ ] Phase 5: Microprocessor Integration - Connect an ESP32 or Raspberry Pi to the bus. Use the microprocessor for simple looping, storing values and more complex calculations

[ ] Phase 6: Relay ALU - Move away from microprocessors and create a full ALU from relays


The BOM .csv file for the mainboard is in this repository.
