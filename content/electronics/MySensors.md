---
title: "MySensors"
date: 2020-08-04T18:56:03+02:00

---


    git clone https://github.com/mysensors/MySensors.git --branch master
    cd MySensors


SensorBender PiGate Pins

|(pin no)<br>rPI|PiGate|
|---:|:--|
|15      |    nRF24 IRQ|
|22     |     nRF24 CE|
|24      |    nRF24 CS|
|Lora|
|13     |     RFM95 IRQ (DIO 0)|
|26     |     RFM95 CS|
|Common|
|19     |     MOSI|
|21     |     MISO|
|23     |     SCK|

Build gateway for nrf24

    ./configure --my-transport=rf24 --my-gateway=mqtt --my-controller-ip-address=10.42.0.101 --my-mqtt-publish-topic-prefix=mys-out --my-mqtt-subscribe-topic-prefix=mys-in --my-mqtt-client-id=mysgwt1 -my-rf24-ce-pin=22 -my-rf24-cs-pin=24 -my-rf24-irq-pin=15

    make
    mv bin/mysgw ../mysgw-nrf24

Build gateway for rfm95

    ./configure --my-transport=rfm95 --my-gateway=mqtt --my-controller-ip-address=10.42.0.101 --my-mqtt-publish-topic-prefix=mys-out --my-mqtt-subscribe-topic-prefix=mys-in --my-mqtt-client-id=mysgwt8 --my-rfm95-cs-pin=26 --my-rfm95-irq-pin=13 --my-rfm95-frequency=434

    make
    mv bin/mysgw ../mysgw-rfm95

