 .. note:: We are currently moving the documentation to a new platform. Please visit `Trezor Wiki <https://wiki.trezor.io/Developers_guide:Low_level_API>`_ for the latest version of this page.

Low level API
=============

TREZOR communicates using a simple request-response model.
Messages are exchanged always in a purely synchronous fashion over `USB HID <https://en.wikipedia.org/wiki/USB_HID>`_.
These messages are serialized into binary format using `Protocol Buffers <https://en.wikipedia.org/wiki/Protocol_Buffers>`_.

USB HID
-------

The SatoshiLabs Vendor ID is ``0x534c`` and TREZOR's Device ID ``0x0001``.

If you've never worked with HID devices before, it may be helpful to take a look at `Python implementation <https://github.com/trezor/python-trezor/blob/master/trezorlib/transport/hid.py>`_ or `Java implementation <https://github.com/trezor/trezor-android/blob/master/trezor-lib/src/main/java/com/satoshilabs/trezor/lib/TrezorManager.java>`_ which establish a connection to TREZOR and reads and write to the device.

Protobuf definitions
--------------------

Protobuf message definitions are stored in the `trezor-common <https://github.com/trezor/trezor-common/tree/master/protob>`_ repository.  The following files are of interest:

- `messages.proto <https://github.com/trezor/trezor-common/blob/master/protob/messages.proto>`_ -- describes messages
- `types.proto <https://github.com/trezor/trezor-common/blob/master/protob/types.proto>`_ -- describes data structures sent within the messages

API workflows
-------------

Message ordering in the TREZOR protobuf protocol is significant.  You will find a list of standard workflows bellow:

.. toctree::
   :maxdepth: 2

   api-workflows
