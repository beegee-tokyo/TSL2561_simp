#TSL2561 Light Sensor Driver #

This library is based on [Adafruits Unified sensor driver for TSL2561](https://github.com/adafruit/Adafruit_TSL2561), but simplified so that no additional unified sensor library is needed.

~~This driver is for the Adafruit TSL2561 Breakout, and is based on Adafruit's Unified Sensor Library (Adafruit_Sensor).~~

The driver supports manual or 'auto' gain. Adjusting the gain allows you to make the sensor more or less 'sensitive' to light (depending on if you are indoors or outdoors, for example):
```
tsl.setGain(TSL2561_GAIN_1X);      /* No gain ... use in bright light to avoid sensor saturation */
tsl.setGain(TSL2561_GAIN_16X);     /* 16x gain ... use in low light to boost sensitivity */
tsl.enableAutoGain(true);          /* Auto-gain ... switches automatically between 1x and 16x */
```

The driver also supports as automatic clipping detection, and will return '65536' lux when the sensor is saturated and data is unreliable. tsl.getEvent will return 65536 in case of saturation. ~~false in case of saturation and true in case of valid light data.~~


## About the TSL2561 ##

The TSL2561 is a 16-bit digital (I2C) light sensor, with adjustable gain and 'integration time'.  

Adjusting the 'integration time' essentially increases the resolution of the device, since the analog converter inside the chip has time to take more samples.  The integration time can be set as follows:
```
tsl.setIntegrationTime(TSL2561_INTEGRATIONTIME_13MS);      /* fast but low resolution */
tsl.setIntegrationTime(TSL2561_INTEGRATIONTIME_101MS);  /* medium resolution and speed   */
tsl.setIntegrationTime(TSL2561_INTEGRATIONTIME_402MS);  /* 16-bit data but slowest conversions */
```

One of the big advantages of the TSL2561 is that it is capable of measuring both broadband (visible plus infrared) and infrared light thanks to two distinct sensing units on the device.  This is important in certain lighting environments to be able to read the light level reliably.

More information on the TSL2561 can be found in the datasheet: http://www.adafruit.com/datasheets/TSL2561.pdf


## ~~What is the Adafruit Unified Sensor Library?~~ ##
Removed because no longer valid for this library

## About this Driver ##

Adafruit invests time and resources providing this open source code.  Please support Adafruit and open-source hardware by purchasing products from Adafruit!

Written by Kevin (KTOWN) Townsend for Adafruit Industries.
Simplified by Bernd Giesecke for private use.
