---
title: "Serial Pill"
date: 2020-01-13T18:56:03+02:00

---
#### pill_serial.bin
compile  [pill_serial](https://github.com/satoshinm/pill_serial)


Changed baudrate to `230400` on all three serialports in [usbuart.c](https://github.com/satoshinm/pill_serial/blob/master/src/usbuart.c#L63)  

and also `CDCACM_PACKET_SIZE` to `32` according to [Issue 1](https://github.com/satoshinm/pill_serial/issues/1)

more information from here: https://satoshinm.github.io/blog/171223_stm32serial_triple_usb-to-serial_adapter_using_stm32_blue_pill.html

enable serial bootloader on STM32F10x

    boot0 = 1
    boot1 = 0

and connect with a serial adapter    
   
    tx = A10
    rx = A9

then we need something to flash with, [stm32loader](https://github.com/florisla/stm32loader) is a good choice

`pip install pyserial stm32loader`

then we can flash our code, choose correct COM port

`stm32loader -p COM6 -e -w -v src\pill_serial.bin`

	

| Serial | TX | RX | SPEED |
| ------ | -- | -- | ----- |
| USART 3 | PB10 | PB11 | 230400
| USART 2 | PA2 | PA3 | 230400
| USART 1 | PA9 | PA10 | 230400

##### Serial driver
With my usb serial adapter based on PL2303 some new driver would not load and just gace the error "PL2303HXA PHASED OUT SINCE 2012. PLEASE CONTACT YOUR SUPPLIER." after some searching https://vk3tbs.home.blog/tag/pl2303hxa-phased-out-since-2012/ came up with a solution. After some links You can find a driver on the bottom of this page https://grylewicz.pl/kabel-usb-rs232-prolific-pl2303-i-blad-kod-10/


{{%attachments title="Backed up files" %}}