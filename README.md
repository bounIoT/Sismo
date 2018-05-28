# Sismo

An Earthquake Alarm Prototype with Arduino Nano and ENC28J60 Ethernet Module, made for CMPE 490 IoT Course in Boğaziçi University.

## Getting Started

There are two different servers, one for handling earthquake signals, the other one to send the gyroscope data. The gyroscope data is used to predict the richter scala level the apartment can endure with little damage. The earthquake signal is predicted by Boğaziçi University Kandilli Observatory. In this prototype, our server assumes that in case of earthquake, it recieves an http request with the format 


```
get http://www.serverdomain.com/earthquake
```
The response will be 1 for alarm, 0 for no earthquake.


The request to send gyroscope data is of the format:


```
GET http://hello-node-noisy-mongoose.eu-gb.mybluemix.net/check HTTP/1.1" "\r\n"
                        "Host: <host>" "\r\n"
                        "Content-Length: <length>" "\r\n"
                        "\r\n"
                        {x: <x>, y:<y>, z:<z>}
```

### Prerequisites

ENC28J60 Ethernet Module, 
Arduino Nano, 
gy-50 l3g4200d Gyroscope, 
2 LEDs, 
8 Ohm 1 W Speaker.

Arduino IDE with Ethercard.h installed.


### Wiring

The wiring should be as follows:

Ethernet Module:

|ENC28J60 Ethernet Module | Arduino Nano |
| --- | --- |
|SO| 	D12|
|SCK|	D13|
|RST|	RST|
|GND|	GND|
|VCC|	3.3V|
|CS|	D10|
|SI|	D11|

Gyro:

| gy-50 l3g4200d Gyroscope | Arduino Nano |
| --- | --- |
|GND|	GND|
|SD0|	3.3V|
|VCC|	3.3V|
|SCL|	A5|
|SDA|	A4|


|Power Led	|Arduino Nano|
| --- | --- |
|+|	D8|
|-|	GND|


|Ethernet Led |Arduino Nano|
| --- | --- |
|+|	D9|
|-|	GND|


|Speaker |Arduino Nano|
| --- | --- |
|+|	D3|
|-|	GND|


## Flow Of Data

![alt text](https://github.com/bounIoT/Sismo/blob/master/iot%20final.png)


## Special thanks to 
[IBM Node Hello World Tutorial](https://github.com/IBM-Cloud/node-helloworld)

