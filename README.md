What this is
This project sends text wirelessly using light. One Arduino blinks an LED in a controlled way. Another Arduino watches that light using an LDR, reconstructs the bits, turns them back into characters, and shows them on an LCD.
No radio. No Wi-Fi. Just visible light and timing.
Call it basic Li-Fi / optical wireless communication. It’s a learning project, not a commercial system.

Why this exists
The goal isn’t speed or range. The goal is to understand how data becomes bits .How bits become a physical signal.How timing and noise can break everything. Why synchronization matters
If you get this working, UART, SPI, RF, and real Li-Fi concepts suddenly make more sense.

How it works 

A. Transmitter
1. Text is entered via the Serial Monitor.
2. Each character is converted to its 8-bit ASCII form.
3. The LED turns ON and OFF for each bit using a fixed delay.
4. A stop condition keeps the receiver in sync.
5. A # character marks the end of a message.

B. Receiver
1. The LDR senses light intensity.
2. Analog values are compared to a threshold.
3. Bits are sampled at the same timing interval.
4. Characters are reconstructed from the bits.

Output is shown on:
Serial Monitor
16×2 I2C LCD
When # is received, the LCD clears.

Hardware Used
1. 2× Arduino boards 
2. LED (high brightness preferred)
3. LDR
4. Resistors (LDR divider)
5. 16×2 I2C LCD
6. Breadboard + jumper wires

Key Parameters
Sampling time: 5 ms
Communication type: 8-bit serial 
Medium: Visible light
Line-of-sight: Required\

Limitations 
LDRs are slow  so  low data rate
Ambient light affects reliability
Timing is fixed (no clock recovery)
Short range cant be used for longer range.

What you actually learn
Optical modulation basics
Bit-level communication
Timing sensitivity

Obvious upgrades
Replace LDR with a photodiode
Add a comparator (LM358 / LM393)
Use hardware timers instead of delay()
Add checksum or parity
Increase speed safely
