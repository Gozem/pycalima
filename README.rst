========
PyCalima
========
Simple python interface against the
`Pax Calima® <http://www.pax.se/sv/produkt/calima/pax-calima-flakt>`_
bathroom fan created and sold by `Pax® <http://www.pax.se>`_

This module provides a very simple interface against the various
GATT characteristics of the Calima fan, most importantly it handles the
authentication so values are actually persisted within the fan.

Uses `BluePy <https://github.com/IanHarvey/bluepy>`_


Installation
----------
I did this on Raspberry pi Zero W but it can be done on other hardware too.

You will need to install python3 which is Python v 3.4 if you install it from apt-get repos.
   $apt install python3 python3-pip libglib2.0-dev

Then install BluePy
    $sudo pip3 install bluepy

Clone this repo
Edit all py files and change the env from python3.6 or 3.7 to just python3
setup.py install


Demo usage
----------
.. code:: python

  from Calima import Calima

  fan = Calima("MA:CC:AD:DR:ES:SS", "012345")
  print(fan.getAlias())

Command line tool
-----------------
The module includes a very simple commandline tool which prints all
the characteristics of a fan and then the State every two seonds. It can
also search for available fans if you don't the MAC address.

For more on using the tool, just run `calima -h`.

Documentation
-------------
A good readup introductory readup on BLE reverse engineering can be found
`here <https://medium.com/@urish/reverse-engineering-a-bluetooth-lightbulb-56580fcb7546#.9ltnsvdsn>`_.

Some badly structured details about the protocol can be found in the
`Characteristics file <characteristics.md>`_.

There is currently no documentation on the module yet, check the
Calima.py file to see available functions.

License
-------
See LICENSE file
