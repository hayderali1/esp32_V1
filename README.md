# esp32_V1
Log-Distance Path Loss Model:

The function applies the log-distance path loss model, which is a standard way to estimate distance based on signal strength. The formula used in calculateDistance(rssi) is:

<img width="179" alt="image" src="https://github.com/user-attachments/assets/38edb46d-36e5-450c-b754-db7f5b72f922">

Here’s what each variable represents:

RSSI: The received signal strength in dBm.

txPower: The signal strength in dBm at a reference distance (typically 1 meter). This is often determined experimentally and reflects the transmitted power when the receiver is 1 meter from the transmitter.
n: The path-loss exponent, which represents how much the signal attenuates as it travels through the environment. This varies based on surroundings:
n = 2: Free space (e.g., outdoors or unobstructed areas)
n > 2: Environments with obstacles (e.g., indoors with walls)
Breaking Down the Formula
Signal Difference: 
(
txPower
−
RSSI
)
(txPower−RSSI)

This calculates the difference between the known signal strength at 1 meter (txPower) and the actual received RSSI. A larger difference suggests a greater distance from the transmitter.
Division by Environmental Factor: 
txPower
−
RSSI
10
×
𝑛
10×n
txPower−RSSI
​
 

Dividing by 
10
×
𝑛
10×n scales the difference in signal strength to reflect environmental attenuation.
Exponential Conversion: 
1
0
result
10 
result
 

Applying 
1
0
result
10 
result
  transforms the log-scaled result back to a linear distance measure in meters. The result gives an estimated distance between the transmitter and receiver.
