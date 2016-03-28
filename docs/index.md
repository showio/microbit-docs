<center>
<!-- Created using @ntoll's microbit animator: http://pycomic.github.io/microbit.html -->
!["welcome to the runtime" on a microbit](resources/welcome.gif)
</center>
#Welcome to our Documentation!

The micro:bit runtime, also known as the micro:bit DAL (Device Abstraction Layer), is
essentially a small, lightweight operating system that controls every aspect of
the BBC micro:bit.

The runtime is built on a platform called [mbed](https://www.mbed.com), provided by ARM,
which provides a common abstraction layer for many ARM based devices.

This resource supplies an abstract overview of the key elements of the runtime,
including the general concepts used by the runtime, and the best practices for
programming the micro:bit when programming at the C/C++ layer.

#Installing

If you want to write code for the micro:bit at the C/C++ layer, then you will need
to install [Yotta](https://yotta.mbed.com/). Detailed instructions on how to install
and get our basic project building with Yotta can be found [here](./installing-yotta.md).


#Layout

The remainder of the page will discuss the general layout of the documentation on
this site.

Member documentation is generated using [doxygen](http://www.stack.nl/~dimitri/doxygen/),
which is translated into markdown for use by [mkdocs](http://www.mkdocs.org/).

##uBit
uBit, a condensed name for micro:bit,  presents our common abstraction
used by Microsoft Blocks, Microsoft TouchDevelop and CodeKingdoms Javascript.

It is broken down by classes, which are instantiated and attached to the uBit object
at runtime.

Each document provides a brief overview of the class, MessageBus IDs and possible events
that could be generated by that class. It also lists the member functions that can
executed by the user to perform various actions with the micro:bit.

The uBit object looks like this:

>    uBit {<br/>
>    &emsp;&emsp;[.i2c](ubit/i2c.md),<br/>
>    &emsp;&emsp;[.serial](ubit/serial.md),<br/>
>    &emsp;&emsp;[.MessageBus](ubit/messageBus.md),<br/>
>    &emsp;&emsp;[.buttonA](ubit/button.md),<br/>
>    &emsp;&emsp;[.buttonB](ubit/button.md),<br/>
>    &emsp;&emsp;[.buttonAB](ubit/button.md),<br/>
>    &emsp;&emsp;[.display](ubit/display.md),<br/>
>    &emsp;&emsp;[.accelerometer](ubit/accelerometer.md),<br/>
>    &emsp;&emsp;[.compass](ubit/compass.md),<br/>
>    &emsp;&emsp;[.thermometer](ubit/thermometer.md),<br/>
>    &emsp;&emsp;[.io](ubit/io.md),<br/>
>    &emsp;&emsp;[.ble](ubit/ble.md),<br/>
>    &emsp;&emsp;[.BLEManager](ubit/blemanager.md),<br/>
>    &emsp;&emsp;[.radio](ubit/radio.md),<br/>
>    }

##Data Types

The 'Data Types' drop down lists the various different structures used to hold,
pass, and evaluate data used in the runtime.

> [MicroBitImage](data-types/image.md) - This data type is used in the runtime when interacting
with various components, in particular the display. It contains bit map information
and supports various manipulations of this information.<br/><br/>
> [MicroBitEvent](data-types/event.md) - Events are used throughout the runtime to pass messages
between components or between the system and the user.<br/><br/>
> [ManagedString](data-types/string.md) - Strings are used when interacting with buffers containing
text intended for any one of our interfaces that support ManagedString, namely the display.
This data type supports many operations on the buffer wrapped by this type. It also, most
importantly, manages the memory allocation for the user, and maintains a count of the references
pointing to an instance of this type.<br/><br/>

##BLE

The ability to communicate is an important aspect of an IOT device. There are a number of ways
to communicate with a micro:bit from another device, Bluetooth Low Energy (BLE) is one of them.

The documentation covered in this section outlines important elements required to communicate
with a micro:bit over BLE, including documentation around the pairing process, and the specification
of the default micro:bit profile.

##Extras

This navigation list commonly covers classes that are hidden or wrapped by other elements of the runtime
to simplify APIs for other languages that target the runtime.