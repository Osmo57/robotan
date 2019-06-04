<H2>Assembly Instructions</H2>
Die deutsche Version findet man  <A HREF="Assembly Instructions_de.md">hier</A>.  
<BR><BR>
To assemble the Robotan board, you'll need the <A HREF="schematics">plain board</A> itself plus:  
<BR>
<UL>
<LI>1 x Wemos D1 Mini
<LI>1 x MAX 3232 CPE DIP 16 RS232/TTL converter
<LI>1 x 9 pin male serial connector
<LI>5 x 0.1µF capacitators
<LI>1 x 470µF capacitator
<LI>2 x 8 pin header
<LI>2 x 8 pin socket
<LI>optionally: 1 x HC-05 Bluetooth module (HC-06 also works)
<LI>optionally: 1 x u-blox NEO-6 GPS module (or compatible)
<LI>optionally: 1 x ADXL335 acceleration sensor (analogue, with X/Y/Z output pins)
<LI>optionally: 1 x KY-003 hall effect sensor (digital, active low)
<LI>optionally: 1 x Piezo buzzer CPM 121 (for alarm beeps when robot is outside GPS boundaries)
  </UL>
Except for the Wemos D1 Mini and the extension modules/sensors, you can find a list of items at <A HREF="https://www.reichelt.de/my/1409494">Reichelt</A>.  
<BR>
Some boards from a collective order are still available. Contact robotan (ät) code-it.de if you are interested (German or English).
<BR><BR>
To assemble the board, proceed as follows:
<BR>

1. Solder the MAX 3232 CPE on the board.

2. Solder the five 0.1µF capacitators on the board at the designated spots

3. Solder the 470µF capacitator  between 5V and G(ND) on the board - watch the polarity! Afterwards, bend the capacitator down, as shown in the photo below.

4. Solder the two 8 pin sockets to the Wemos D1 mini and the two 8 pin headers on the Robotan board.

5. Solder the serial connector to the board. You might have to bend the two adjacent capacitators a bit.

6. Plug the Robotan board on top of the Wemos D1 Mini. The serial connector of the Robotan board must be on the same side as the Micro USB 
connector of the Wemos D1 Mini.

7. If you need to flash the firmware via USB, you have to unplug the board and the Wemos first. This usually only applies to the first flashing process, because afterwards you can use the web-based flashing feature which is not affected by this.

8. If you want to add the u-blox GPS  module, you can solder the pins one 
to one like this:  
VCC <-> 3V3  
GND <-> G  
TX <-> D7  
Do not connect the RX line of the module as it is not used and might interfere with the Wemos D1 Mini board.  
If you connect the piezo buzzer to D2 (+) and GND (-), an SOS beep will turn on once the robot has left the permissible GPS coordinates.

9. If you want to add the  <A HFREF="https://amzn.to/2MoVvjT">ADXL335</A> acceleration sensor in older robots for detecting whether the robot is stuck, connect the VCC and GND pins to 3V3 and GND on the Wemos D1 Mini respectively. Connect one of the X/Y/Z axis pins to the A0 pin on the Wemos. Use that axis pin on the ADXL335 that best matches the horizontal movement axis of the robot. This depends on where and in which direction you have attached the sensor inside the robot.  
To reduce or at best eliminate false alarms on older robots when the robot is back in its base, you can use a <A HREF="https://amzn.to/3184fOL">Hall Effect Sensor KY-003</A> in combination with a <A HFRE="https://amzn.to/2MqvkJP">strong magnet</A>. Connect VCC with 5V, GND with G and the signal pin of the KY-003 with pin D1 of the Wemos.  
Magnet and sensor should be placed in a way that there is only a very small distance between them when the robot is in its base (2-3 cm).

10. If you want to add the HC-05 Bluetooth module, you can solder the pins one 
to one like this (see also image below):  
5V <-> 5V  
GND <-> G  
TX <-> D4  
RX <-> D3  
For modules with six pins, make sure you only connect the four center ones 
(5V, GND, RX and TX)!  
To configure the HC-05, see the manual or try the `RobotanBT.ino` which should
be able to configure the Bluetooth module correctly. You have to put the module
into programming mode first by connecting the 5V and EN pins on the module 
while powering up. Better modules have a microswitch which you just need to
press alternatively.  
<H3>Done :-)!</H3>
Position of the capacitator:<BR>
<IMG SRC="img/Robotan-Board-Final.jpg">
<BR><BR>
Position of the Bluetooth module:<BR>
<IMG SRC="img/8 - Adding Bluetooth module.jpg">
