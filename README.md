# ImageSocket_Python
[![Packagist](https://img.shields.io/packagist/l/doctrine/orm.svg?maxAge=2592000)]()
[![Packagist](https://img.shields.io/badge/Develope-1.0.0-brightgreen.svg)]()</br>   
    
The python plugin to receive the image socket
    
       
    
<p align="center">
  <img src="https://github.com/SunnerLi/ImageSocket/blob/master/Image/logo.jpeg"/>
</p> 
    
       
    
Abstract
---------------------
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This project provide a new class `ImageSocket`. As the usual, you can easily transfer the string.
But It's not easy to transfer the image with a few code. On the Android platform, Google provide 
TCP & UDP two WiFi method to pass information. One the other hand, the python platform provide 
socket pachage to receive the infomation. This project build a basic API that the developer can 
transfer the image in a easy way!    
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This project provide Internet( TCP & UDP ) and bluetooth methodology to reach the goal.    
    
    
    
     
Motivation
---------------------
It's wild to use RTP to transfer the video streaming. There's some situation that the phone would transfer the image to PC. The computation of phone is weaker than the PC. This project use this property to receive the image and reassemble.    
There are other projects that do the similar things. (For example: PC to android or Android to Android) So this project wouldn't implement these direction now.    

Example
---------------------
TCP:
```python
   sock = ImageSocket.ImageSocket()
   sock.socket(socket.AF_INET, socket.SOCK_STREAM)
   sock.setsockopt(socket.SOL_SOCKET, socket.SO_REUSEADDR, 1)
   sock.bind (("", port))
   sock.listen(1)
   sock.settimeout(20)
   opSock, address = sock.accept()
   img = opSock.recv(2000000)
```
UDP:
```python
   sock = ImageSocket.ImageSocket()
   sock.socket(socket.AF_INET,socket.SOCK_DGRAM)
   sock.setsockopt(socket.SOL_SOCKET, socket.SO_REUSEADDR, 1)
   sock.bind (("", port))
   img = sock.recvfrom(2000000)
```    
Bluetooth:
```python
   sock = ImageSocket.ImageSocket()
   sock.socket(RFCOMM)
   sock.bind(("",PORT_ANY))
   sock.listen(1)
   client_sock, client_info = sock.accept()
   img = client_sock.recv(2000000)
```    

Get Start
---------------------
The following is the environment of development. Don't garentee it would work normally if you didn't have the proper edition of other package.
* OpenCV 2.4.0+
* Numpy 1.10.4+
* Python 2.7  
* pybluez if you want to use bluetooth transfer    
    
The command to install:
```
sudo pip install "https://github.com/sunnerli/ImageSocket_Python/tarball/1.0.0"
```    
or    
```
sudo pip install ImageSocket --update
```    
The end number above is the version of this plugin.
The edition number of this project would show at the top. (green small image)

    
Usage Detail
---------------------
Check the Wiki to get the more detail.
- [Wiki](https://github.com/SunnerLi/ImageSocket_Python/wiki/Home)
    </br>    
    </br>     
    
Developed By
---------------------

* SunnerLi - <a6214123@gmail.com>
    </br>    
    </br>    
    
License
---------------------
    The MIT License (MIT)
    Copyright (c) 2016 - SunnerLi

    Permission is hereby granted, free of charge, to any person obtaining a copy of this software 
    and associated   documentation files (the "Software"), to deal in the Software without 
    restriction, including without limitation the rights to use, copy, modify, merge, publish, 
    distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom 
    the Software is furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in all copies or 
    substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING 
    BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND 
    NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, 
    DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, 
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
