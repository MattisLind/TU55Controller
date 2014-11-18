TU55Controller
==============

This project aims at a simple AtMega chip based controller for the DEC TU55 / TU56 drives.

TU55 interface
--------------

The interface consists physically of two cards inserted into the TU55 backplane. The digital interface part is a single DEC module with 
18 connectors to control the selection of a particular drive and to control the motion of the drive.

The analog part consists of a dual DEC module which carries the analog signals to/and from the five R/W heads (ten really but they are
redundant).

Analog interfacing
------------------

The TC01 and TC02 controller make use of the G882 Mancherster read/write module, while the younger TC11, TD8E makes use of the G888 
module.

G882
![G882 schematic](http://i.imgur.com/u9puMxY.png "G882")

G888
![G888 schematic](http://i.imgur.com/0eFZaAe.png "G888")

As far as I can see the purpose is to amplify and limit the signal. Then there is also a circuit at the end to polong the pulse length
by a feedback loop consisting of a capacitor and resistor.

I think that this circuit should be possible to mimic using more modern TLC072 amplifiers and some simple 74HC08 buffers.

So could these circuits be replaced with 



