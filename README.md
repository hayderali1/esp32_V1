# esp32_V1
# Log-Distance Path Loss Model

The function applies the log-distance path loss model, which is a standard way to estimate distance based on signal strength. The formula used in calculateDistance(rssi) is:

<img width="200" alt="image" src="https://github.com/user-attachments/assets/38edb46d-36e5-450c-b754-db7f5b72f922">

Here’s what each variable represents:

RSSI: The received signal strength in dBm.

txPower: The signal strength in dBm at a reference distance (typically 1 meter). 
This is often determined experimentally and reflects the transmitted power when the receiver is 1 meter from the transmitter.

n: The path-loss exponent, which represents how much the signal attenuates as it travels through the environment. This varies based on surroundings:

n = 2: Free space (e.g., outdoors or unobstructed areas)

n > 2: Environments with obstacles (e.g., indoors with walls)

