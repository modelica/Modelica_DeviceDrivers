# Modelica_DeviceDrivers
Free library for interfacing hardware drivers to Modelica models.
There is support for joysticks, keyboards, UDP, shared memory, AD/DA converters and other devices.

## Library description
The `Modelica_DeviceDrivers` library is an open source Modelica package under [Modelica License 2](https://modelica.org/licenses/ModelicaLicense2) that interfaces hardware drivers to Modelica models.
It unifies previous developments concerning device driver support in Modelica, see [Interactive Simulations and advanced Visualization with Modelica](https://modelica.org/libraries/events/modelica2009/Proceedings/memorystick/pages/papers/0056/0056.pdf) and [Modelica for Embedded Systems](https://modelica.org/libraries/events/modelica2009/Proceedings/memorystick/pages/papers/0096/0096.pdf) (Modelica'2009 conference). The functionality covered by this library has been used internally at DLR for several years, such as for Driver-in-the-Loop simulation and for the [DLR Robot Motion Simulator](http://www.dlr.de/media/en/desktopdefault.aspx/tabid-4995/8426_read-17606/).
The previously fragmented functionality was streamlined, improved, and extended to a coherent cross-platform library.

Main features:
  * Cross-platform (Windows and Linux).
  * (Soft) real-time synchronization of a simulation.
  * Support for Keyboard, Joystick/Gamepad, and 3Dconnexion Spacemouse.
  * Support for a universal packaging concept to pack Modelica variables in a graphical and convenient way into a bit vector and transport such a bit vector via UDP or Shared Memory (CAN support is prototypical available).
  * Support of the Linux control and measurement device interface for digital and analog IO (Comedi interface).

All device drivers are made available via external Modelica functions. Furthermore, high level interfaces on these functions are provided via Modelica blocks. The first interface uses Modelica 3.2 functionality only (when-clauses and sample-operator).
The second interface uses the synchronous language elements introduced in Modelica 3.3 and is based on clocks (works together with the new `Modelica_Synchronous` library).

![BlockOverview](screenshot.png)

### Self-certification
 - [X] Internationalized
 - [ ] Unit tests
 - [X] End-user documentation
 - [X] Internal documentation (documentation, interfaces, etc.)
 - [X] Existed and maintained for at least 6 months

## Current release

Download [Modelica_DeviceDrivers v1.1 (2013-04-24)](../../archive/v1.1.zip)

Please note that currently (2013-05-10) the only Modelica tool that is known to work well with the library is Dymola (preferable Dymola 2013 FD0 and later). If you tested the library successfully with another Modelica tool, please contact me (Bernhard), so that I can include that information.

#### Release notes
*  [Version v1.1 (2013-04-23)](../../archive/v1.1.zip)
  * Improved Modelica 3.3 standard conformance (hopefully completely standard conform by now)
  * Included support for the Linux Controller Area Network Protocol Family (aka Socket CAN). This is considered an alpha feature. Therefore the API is not stable and testing has been very limited
  * The cmake based build system for the external C sources of this library has been improved to be more robust and better documented.
  * Bugs in the SerialPackager's AddString and GetString blocks have been resolved and new blocks AddFloat and GetFloat are now available.
  * Some smaller additional bugfixes and improvements.
*  [Version v1.0 (2012-10-17)](../../archive/v1.0.zip)
  * Initial release `v1.0_build5` with improved documentation

## License

This Modelica package is free software and the use is completely at your own risk;
it can be redistributed and/or modified under the terms of the [Modelica License 2](https://modelica.org/licenses/ModelicaLicense2).

## Development and contribution
Main developers:
* [Bernhard Thiele](mailto:bernhard.thiele@dlr.de), release management and the Linux specific code
* [Tobias Bellmann](mailto:tobias.bellmann@dlr.de), most of the MS Windows specific code

You may report any issues with using the [Issues](../../issues) button.

Contributions in shape of [Pull Requests](../../pulls) are always welcome.