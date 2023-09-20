SUMMARY

Using Arduino and Raspberry Pi, this project aims to display local weather conditions in a single interface, providing numerical data for temperature, precipitation, wind speed, and pressure. The DHT22 sensor mounted on the Proto Shield allows us to measure temperature and humidity, while the BMP180 pressure sensor measures temperature and pressure in Pascal units. To facilitate communication between Arduino and Raspberry Pi, the NRF24L01 wireless module was chosen. This setup enables the use of the outdoor system (Arduino) on the balcony while comfortably accessing the Raspberry Pi interface in another room, given the NRF24L01 module's range of approximately 100 meters, making it suitable for a 3+1 bedroom house. A 12 cm case fan connected to the Arduino serves as a wind measurement device. Although the data obtained from the case fan lacks the precision of metrics used in meteorology, such as kilometers and hours, it was included in the project for its functional contribution. Plastic spoons mounted on the case fan will generate some electricity as they rotate in the wind, and this voltage change will be observed in a 10-bit resolution, corresponding to a numerical value between 0 and 1023. For example, if the value falls between 0 and 100 bits, it indicates calm weather, while a range of 100 to 250 bits suggests windy conditions.

INTRODUCTION – What, Where, How Did I Use?

We obtained the air temperature using the DHT22 sensor placed on the Arduino Proto Shield.
With the help of the BMP180 pressure sensor mounted on the Proto Shield, we displayed air pressure in Pascal units.
We attached plastic spoons to the case fan, and as they rotate, they generate a voltage change that corresponds to a numerical value in a 10-bit resolution, ranging from 0 to 1023. To mount the plastic spoons on the case fan, we used a cover and a silicone gun.
We established the connection between the sensors and the case fan with the Arduino Uno using the Arduino Proto Shield.
I loaded the libraries and necessary codes for the sensors onto the Arduino Uno R3 model. After attaching the Proto Shield to the Arduino Uno, I used a 9-volt adapter to power the device.
The NRF24L01 wireless module on the Proto Shield wirelessly transmits data received from the Arduino to the Raspberry Pi.
I also added an NRF24L01 wireless module to the Raspberry Pi, allowing it to receive data from the Arduino. The Raspberry Pi processes this data using code found on GitHub and presents it as a weather interface.

The NRF24L01 library used in Arduino can be found here:
[https://github.com/nRF24/RF24]

The BMP180 library used in Arduino can be found here:
[https://github.com/sparkfun/BMP180_Breakout]

CONCLUSION

Arduino successfully transmitted data to the Raspberry Pi. However, due to my inability to solder the BMP180 pressure sensor, I could not retrieve pressure data for now. Nonetheless, the project functioned smoothly. The Raspberry Pi interface displays temperature, precipitation, and wind speed. One challenge I encountered during the project was the presence of numerous errors in the Python code used for the Raspberry Pi. This occasionally made it challenging to process data from the Arduino. To manage project costs, I removed the optional Raspberry Pi original touchscreen and case from the materials list. Instead, I use VNC Viewer to remotely access the Raspberry Pi desktop while it is operational. This allows me to check weather station data from my computer at any time. In conclusion, the project is still in a state where it can be further developed, but it currently operates smoothly.
