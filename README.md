# CreatePad V1
CreatePad (formerly named "Hackpad-Japanese-Matrix" and "Macropad Proto V1") is a multipurpose productivity macro pad with a 3x3 switch layout, two rotary encoders, an OLED screen and uses QMK firmware. Under the hood is a Japanese Duplex Matrix that made the large amount of inputs (15 in total, including both of the encoders' buttons!) possible. More info on that below.

<H2>
Features: 
</H2>

  * 11 total switches (3x3 MX + 2 knobs)
  
  * A 0.91 inch OLED display
    
  * 10 customizable profiles with VIA support
  
  * Slanted case design for better (my personal) comfort :)

<H2>
CAD Model, Made in Fusion360 (the free version):
</H2>

<H3>This is the overall CAD design of CreatePad:</H3> 


<img width="935" height="688" alt="image" src="https://github.com/user-attachments/assets/7928361e-c42e-447f-93c5-bf75ce24b0f0" />
<img width="528" height="710" alt="image" src="https://github.com/user-attachments/assets/aff0aef2-380d-4957-a879-2ad8f4e817ed" />


<H3>This is the separated (top case, PCB, bottom case) bodies:</H3> 


<img width="1094" height="563" alt="image" src="https://github.com/user-attachments/assets/c9ba929d-4d93-4e2e-b380-28ceaf18d0fd" />

<H2>Schematic & PCB (Made in KiCAD):</H2>

<H3>Schematic:</H3>

<img width="1503" height="876" alt="image" src="https://github.com/user-attachments/assets/a1d29457-f735-443d-acdb-bd7be2624da3" />

<H4>"Behold, The Japanese Duplex Matrix"</H4>

<H3>PCB:</H3>

<img width="664" height="846" alt="image" src="https://github.com/user-attachments/assets/112c4f57-12a4-4f8b-af41-233ef3e239e6" />

*<H4> I had such a dilemma making sure everything is aligned and symmetrical (some still probably aren't) </H4>*

<H2>Firmware Overview:</H2>

CreatePad uses custom QMK firmware (because the matrix used is different from a traditional matrix) and is highly customizable, even the OLED can be configured using it! The attatched firmware (as of now) can store up to 10 unique, fully customizable configurations (even the knobs' functions!) through VIA.

<H2>The Japanese-Duplex Matrix</H2>

Since the XIAO RP2040 only has 14 pins and only 5 of them are left for button inputs, I had to pick between two choices: 1. Reduce the amount of total physical inputs or 2. Find out if there's another type of matrix that limits the amount of pins even further than that of a traditional matrix. Turns out there is such a thing! It's called a Japanese Duplex Matrix. Everything about it can be read on this webpage: https://kbd.news/The-Japanese-duplex-matrix-1391.html#jpduplex .

In a nutshell, according to the webpage, unlike a traditional keyboard matrix, the custom QMK firmware scans the matrix in both directions! First COL2ROW, then ROW2COL, in succession. "The trick lies in the direction of diodes: two columns are connected to the same COL pin, but one column has diodes pointing in one direction, while switches in the second column have diodes pointing to the opposite direction. This way the matrix can be scanned in both ways, checking half of the switches on the COL2ROW and another half on the ROW2COL iteration." Compared to a traditional matrix, the amount of pins needed have been significant reduced, making it exactly needing only 5 pins! No extra rows or columns needed.

<H2>BOM:</H2>

* 1x Seeed XIAO RP2040 MCU

* 9x MX-Style Switches

* 2x EC11 Rotary Encoders

* 11x Through-hole 1N4148 Diodes

* 1x 0.91 Inch OLED Display

* 9x white DSA keycaps

* 4x M3x16mm screws



that's about it for now :). I've learned so much during the process of designing this project, I can't wait to assemble it in the future!
