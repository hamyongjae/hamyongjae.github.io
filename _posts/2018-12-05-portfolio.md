---
layout: post
title:  "블루투스와 Wifi무선통신을 이용한 Smart button"
date:   2018-12-07
excerpt: "Bluetooth / Wifi / IOT / Arduino"
project: true
tag:
- Bluetooth
- Wifi
- IOT
- Arduino
comments: true
---

![img_portfolio3_logo](https://user-images.githubusercontent.com/19748922/49659841-7168f400-fa88-11e8-93b0-000946d2f4ba.jpg)

<br />

 본 프로젝트에서는 일상생활에서 불편함을 느낄 법한 여러가지 상황을 떠올려 봤을 때 불편함을 가장 많이 해소할 수 있고, 실현 가능성 있는 기능을 제어할 수 있도록 구현하였다. 버튼을 누르면 블루투스 무선통신을 통해 휴대폰 조명이 ON/OFF 되거나, 비상전화가 걸리거나, 음악이 ON/OFF 되는 기능을 구현하였고, 뿐만 아니라, 스마트 플러그를 별도로 제작하여 안드로이드 휴대폰을 통해 콘센트에서 사용되는 전기의 원격제어가 가능하다. Arduino를 활용해 회로도를 구성하여 버튼을 제작하였고, 플러그는 실제 가정용 플러그(220V)를 구매해 재조립하여 제작하였다.




### Used Technology
* Bluetooth
* Wifi
* Arduino
* ESP8266
* HC-06


### 작품 구상도

![img_portfolio3_1](https://user-images.githubusercontent.com/19748922/49659824-6e6e0380-fa88-11e8-8b57-206e91a22e40.jpg)


ESP8266 모듈과 TCP/IP 소켓 통신을 이용하여 소형경량 데이터 전송장치를 설계하였다. 본 장치는 Wifi연결 기능을 지원하는 ESP8266모듈을 사용하여 서버와 클라이언트를 구성하고, TCP/IP의 소켓 통신을 사용하여 양방향 데이터 전송을 지원하도록 구성하였다. 네트워크는 홈 네트워크와 같이 공유기를 중심으로 사설 IP를 부여하여 ESP8266이 각각 독립적인 IP를 가지게 설계하였다. 본 장치는 양방향으로 데이터를 전송 할 수 있고, 서버 측에서 각각의 클라이언트 데이터들을 저장할 수 있다. 


![img_portfolio3_2](https://user-images.githubusercontent.com/19748922/49659825-6f069a00-fa88-11e8-8af0-4b7bc61b230e.jpg)

ESP8266은 내부는 Tensilica의 L106 Diamond 시리즈 32-bit 프로세스와 SRAM을 탑재하여 보다 저전력에서 고성능 동작이 가능하다. 센서와 같은 외부적인 데이터 를 GPIO(General Purpose Input/Output)를 통해 제공 받 고, 아날로그 데이터도 1 채널 받을 수 있다. 또한 내부 Flash memory에 특정 펌웨어를 업로드 하여 보다 쉬운 MCU(Micro Controller Unit) 컨트롤이 가능하다. ESP 8266 모듈을 선택한 이유는 Wifi soft ap동작, Wifi direct 연결 TCP/IP로 데이터 전송 지원을 하기 위해서다. Serial로 아두이노와 연결한 다음 아두이노에서 AT command를 전송해서 모듈을 제어 가능하다. Wifi 모듈의 baudrate(전송속도)가 115200으로 설정되어 있는데 SoftwareSerial라이브러리가 지원하는 최대 baudrate는 19200 이기 때문에 SoftwareSerial 로 제어할 경우 문제가 생겼다. 따라서 아두이노 0번 1번 핀을 이용해 Hardware serial로 제어해야 한다. 일반적인 아두이노
보드에는 Hardware serial 을 하나만 제공하기 때문에 0, 1번 핀을 사용하는 경우 PC로 Debug 데이터를 출력할 수가 없기 때문에 별도의 회로를 구성하였다.


{% capture images %}
https://user-images.githubusercontent.com/19748922/49659830-6f9f3080-fa88-11e8-9660-44a1f28750dc.jpg
https://user-images.githubusercontent.com/19748922/49659832-6f9f3080-fa88-11e8-819f-192f2e7167c1.jpg
https://user-images.githubusercontent.com/19748922/49659833-7037c700-fa88-11e8-8f63-4373937a64ed.jpg
{% endcapture %}
{% include gallery images=images caption="Screenshots of HC-06" cols=3 %}

위 사진은 HC-06 블루투스 모듈의 핀이다. 총 4개의 핀이 있으며 위에서부터 신호를 받기위한 핀인 RX 핀, 신호를 전송하기 위한 TX핀, GND(Ground), VCC 핀이 있다. 모듈의
전원은 3.6V ~ 6V 사이에서 동작하므로 VCC핀은 아두이노의 5V 단자에 연결하면 된다. 모듈에 따라 3.3V에서 동작하는 모듈도 있으므로 규격을 꼭 확인하여 전원을 연결해야 한다. 본 프로젝트에서는 5V로 사용할 수 있는 HC-06 시리얼 모듈을 사용하였다. HC-06 의 옵션 값들은 시리얼로 연결하여 문자열로 직접 값들을 날리는 방법으로 설정하였다. 그리고, 시리얼 포트는 하나밖에 없기 때문에 아두이노 IDE 시리얼 모니터의 커맨드 창으로 명령어를 주기 위하여 디지털 I/O 핀을 이용한 소프트웨어 시리얼을 사용했다.


![img_portfolio3_12](https://user-images.githubusercontent.com/19748922/49659838-70d05d80-fa88-11e8-9a5f-f0c333b96287.jpg)

아두이노의 작은 전압(5V)으로 큰 전압(110~220V)을 제어 할 수 있는 릴레이가 필요했다. [그림9]와 같이 아두이노의 Output Signal을 AC 릴레이의 Input Signal 부분에 연결해주고 일반 가정용 멀티탭을 개조해 AC릴레이와 연결해주면 아두이노의 5V의 전압이 INPUT에 작용할 때마다 접점이 이동하여 LOAD의 스위치를 이동시켜 220V의 전압을 제어할 수 있도록 해준다.

### Preview

{% capture images %}
https://user-images.githubusercontent.com/19748922/49659828-6f9f3080-fa88-11e8-96b1-87b7e4ad407f.jpg
https://user-images.githubusercontent.com/19748922/49659837-70d05d80-fa88-11e8-9e14-868e05889114.jpg
https://user-images.githubusercontent.com/19748922/49659840-70d05d80-fa88-11e8-8a69-4e2181f92658.jpg
{% endcapture %}
{% include gallery images=images caption="Screenshots of Project" cols=3 %}

