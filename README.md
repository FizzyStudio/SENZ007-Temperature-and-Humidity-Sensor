# SENZ007 Temperature and Humidity Sensor

###### Translation

> For `English`, please click [`here.`](https://github.com/FizzyStudio/SENZ007-Temperature-and-Humidity-Sensor/blob/master/README.md)

> For `Chinese`, please click [`here.`](https://github.com/FizzyStudio/SENZ007-Temperature-and-Humidity-Sensor/blob/master/README_CN.md)

![](https://github.com/FizzyStudio/SENZ007-Temperature-and-Humidity-Sensor/blob/master/pic/SENZ007.jpg "SENZ007")


### Introduction

>  SENZ007 features a calibrated digital signal output with the temperature and humidity sensor complex. Its technology ensures the high reliability and excellent long-term stability. A high-performance 8-bit microcontroller is connected. This sensor includes a resistive element and a sense of wet NTC temperature measuring devices. It has excellent quality, fast response, anti-interference ability and high cost performance advantages.

>Each DHT11 sensors features extremely accurate calibration of humidity calibration chamber. The calibration coefficients stored in the OTP program memory, internal sensors detect signals in the process, we should call these calibration coefficients. The single-wire serial interface system is integrated to become quick and easy. Small size, low power, signal transmission distance up to 20 meters, making it a variety of applications and even the most demanding applications. The product is 4-pin single row pin package. Convenient connection, special packages can be provided according to users need.

### Specification

* Supply Voltage: 3.3V ~ 5 V
- Temperature range :0 - 50 °C, error of ± 2 °C
- Humidity :20 - 90% RH, error of ± 5% RH
- Interface: Digital

### Tutorial

#### Pin Definition

|Sensor Pin|Ardunio Pin|Function Description|
|-|:-:|-|
|VCC|3.3V~5V|Power|
|GND|GND||
|DO|Digital pin|Digital Output|

![](https://github.com/FizzyStudio/SENZ007-Temperature-and-Humidity-Sensor/blob/master/pic/SENZ007_pin.jpg "Pin Definition") 

#### Connecting Diagram

![](https://github.com/FizzyStudio/SENZ007-Temperature-and-Humidity-Sensor/blob/master/pic/SENZ007_connect.png "Connecting Diagram") 

#### Sample Code


	#include <dht11.h>
	dht11 DHT;
	#define DHT11_PIN 4

	void setup(){
	  Serial.begin(9600);
	  Serial.println("DHT TEST PROGRAM ");
	  Serial.print("LIBRARY VERSION: ");
	  Serial.println(DHT11LIB_VERSION);
	  Serial.println();
	  Serial.println("Type,\tstatus,\tHumidity (%),\tTemperature (C)");
	}

	void loop(){
	  int chk;
	  Serial.print("DHT11, \t");
	  chk = DHT.read(DHT11_PIN);    // READ DATA
	  switch (chk){
	    case DHTLIB_OK:  
	                Serial.print("OK,\t"); 
	                break;
	    case DHTLIB_ERROR_CHECKSUM: 
	                Serial.print("Checksum error,\t"); 
	                break;
	    case DHTLIB_ERROR_TIMEOUT: 
	                Serial.print("Time out error,\t"); 
	                break;
	    default: 
	                Serial.print("Unknown error,\t"); 
	                break;
		 }
	 // DISPLAT DATA
	  Serial.print(DHT.humidity,1);
	  Serial.print(",\t");
	  Serial.println(DHT.temperature,1);

	  delay(2000);
	}


### Purchasing [*SENZ007 Temperature and Humidity Sensor*](https://www.ebay.com/).
