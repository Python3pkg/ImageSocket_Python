# ImageSocket_Python
[![Packagist](https://img.shields.io/packagist/l/doctrine/orm.svg?maxAge=2592000)]()
[![Packagist](https://img.shields.io/badge/Develope-0.0.1-brightgreen.svg)]()</br>   
The python plugin to receive the image socket

Abstract
---------------------
This project provide a new class ImageSocket. As the usual, you can easily receive the string. But It's not easy to receive the image with a few code. On the linux platform, GNU provide TCP & UDP two WiFi method to pass information. This project build a basic API that the developer can receive the image in a easy way!    

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

Get Start
---------------------
The following is the environment of development. Don't garentee it would work normally if you didn't have the proper edition of other package.
* OpenCV 2.4.0+
* Numpy 1.10.4+
* Python 2.7  

The command to install:
```
sudo pip install "https://github.com/sunnerli/ImageSocket_Python/tarball/0.0.1"
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
