#############################################################
python-escpos - Python library to manipulate ESC/POS Printers
#############################################################

.. image:: https://travis-ci.org/python-escpos/python-escpos.svg?branch=master
    :target: https://travis-ci.org/python-escpos/python-escpos
    :alt: Continous Integration

.. image:: https://codecov.io/github/python-escpos/python-escpos/coverage.svg?branch=master
    :target: https://codecov.io/github/python-escpos/python-escpos?branch=master
    :alt: Code Coverage

.. image:: https://readthedocs.org/projects/python-escpos/badge/?version=stable
    :target: http://python-escpos.readthedocs.io/en/latest/?badge=stable
    :alt: Documentation Status

<❗>NOTICE (RCLSTN)
-----------
- This repository has been modified to support TWO of the same printer, further modifications could support more.
- The third argument in printer.Usb() is the printer identifier, currently this should either be 0 or 1


Description
-----------

Python ESC/POS is a library which lets the user have access to all those printers handled
by ESC/POS commands, as defined by Epson, from a Python application.

The library tries to implement the functions provided by the ESC/POS-commandset and supports sending text, images,
barcodes and qr-codes to the printer.

Text can be aligned/justified and fonts can be changed by size, type and weight.

Also, this module handles some hardware functionalities like cutting paper, control characters, printer reset
and similar functions.

Dependencies
------------

This library makes use of:

    * pyusb for USB-printers
    * Pillow for image printing
    * qrcode for the generation of QR-codes
    * pyserial for serial printers

Documentation and Usage
-----------------------

The basic usage is:

.. code:: python

    from escpos.printer import Usb

    """ Seiko Epson Corp. Receipt Printer M129 Definitions (EPSON TM-T88IV) """
    p = Usb(0x04b8,0x0202,0)
    p.text("Hello World\n")
    p.image("logo.gif")
    p.barcode('1324354657687','EAN13',64,2,'','')
    p.cut()

The full project-documentation is available on `Read the Docs <https://python-escpos.readthedocs.io>`_.

Contributing
------------

This project is open for any contribution! Please see CONTRIBUTING.rst for more information.
