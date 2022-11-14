# ESPixelStick_Mods_for_Battery_Voltage
ESPixelStick_Battery_Voltage

Features were added to ESPixelStick v1.3 to allow monitoring of the pixel supply voltage, in the case where the pixels are powered from a 12V battery.  This is to prevent operation of the light show under insufficient battery voltage, which causes  errors and glitching in the display when the voltage becomes too low.  

The battery voltage is measured with a 100k/22k voltage divider and the use of analogRead on the A0 pin of the D1 mini.  The value is continuously averaged over 10 readings on 1 second intervals and is calibrated for 15V maximum allowable when using a 100k/22k voltage divider.  The averaged vbat value is displayed on the Home tab of the ESPixelStick menu as Battery Voltage.  

A text field is displayed on the ESPixelstick Device Settings menu tab which accepts values for a vbat_thresh float variable.  IF the averaged voltage vbat becomes less than vbat_thresh then a notification is displayed on the ESPixelStick Home menu tab and the show light output is set to black and the D5 pin is toggled for activating an external relay to disconnect the battery from the pixels, until the module is rebooted.

The battery voltage is displayed on the I2C SSD_1306 OLED Shield for the D1 Mini if attached.

Modifications include:

ESPixelStick_mod_ssd1306.ino:
==============================
Tab:  ESPixelStick_mod_ssd1306.ino:
Lines:  44-46, 113-115, 121-122, 348-363, 1021-1025, 1177, 1318 (only for testing), 1324-1370, 1442-1449.

Tab:  ESPixelStick.h:
Lines:  148.

Tab:  wshandler.h:
Lines:  42, 92, 108.
==============================

esps.css, esps.js, index.html, and config.json were also modified.




