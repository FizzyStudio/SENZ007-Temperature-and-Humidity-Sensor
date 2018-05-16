# SENZ007 数字温湿度传感器

###### 翻译

> `英文`请参考 [`这里`](https://github.com/njustcjj/SENZ007-Temperature-and-Humidity-Sensor/blob/master/README.md).

> `中文`请参考 [`这里`](https://github.com/njustcjj/SENZ007-Temperature-and-Humidity-Sensor/blob/master/README_CN.md).

![](https://github.com/njustcjj/SENZ007-Temperature-and-Humidity-Sensor/blob/master/pic/SENZ007.jpg "SENZ007")
 

### 产品介绍

> SENZ007采用DHT11传感器，是一款含有已校准数字信号输出的温湿度复合传感器。它应用专用的数字模块采集技术和温湿度传感技术，确保产品具有极高的可靠性与卓越的长期稳定性。
> 传感器包括一个电阻式感湿元件和一个NTC测温元件，并与一个高性能8位单片机相连接。因此该产品具有品质卓越、超快响应、抗干扰能力强、性价比极高等优点。

> 
> 用途：测量温度、湿度

### 产品参数

* 工作电压 : 3.3V ~ 5V （ DC ）
* 接口类型：数字
* 温度范围 : 0 ~ 50℃，误差 : ±2℃
* 温度范围： 20 ~ 90%RH，误差 : ±5%RH
* 尺寸 : 3.2cm x 1.4cm

### 使用教程

#### 引脚定义

|Sensor Pin|Ardunio Pin|Function Description|
|-|:-:|-|
|VCC|3.3V~5V|Power|
|GND|GND||
|DO|Digital pin|Digital Output|



![](https://github.com/njustcjj/SENZ007-Temperature-and-Humidity-Sensor/blob/master/pic/SENZ007_pin.jpg "引脚定义") 


#### 连线图

![](https://github.com/njustcjj/SENZ007-Temperature-and-Humidity-Sensor/blob/master/pic/SENZ007_connect.png "连线图") 


### 示例代码

	/*
	  # 描述：
	  # 以下这段代码可检测当下环境的湿度及温度
	*/

	// 
	//   FILE:  dht11_test1.pde
	// PURPOSE: DHT11 library test sketch for Arduino
	//
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



### 购买[*SENZ007 数字温湿度传感器*](https://www.ebay.com/).