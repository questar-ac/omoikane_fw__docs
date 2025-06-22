.. _chapter-usbserial:

=========================
Setup USB-serial adapters
=========================

.. _section-usbserial-linux:

Linux
=====

| ほとんどのベンダのUSB-シリアル・アダプタ用ドライバがカーネルに組み込まれています。
| Drivers for USB-serial adapters from most vendors are built into the kernel.

| USB-シリアル・アダプタに対するデバイスファイルは ``/dev/ttyUSB*`` または ``/dev/ttyACM*`` となります.
| Device files for USB-serial adapters will be ``/dev/ttyUSB*`` or ``/dev/ttyACM*``.

| すべてのUSBデバイスの情報は ``lsusb`` コマンドを使って確認できます。USB-シリアル・アダプタの詳細情報を確認したい場合は、コマンド "``ls -l /dev/serial/by-id``" と "``ls -l /dev/serial/by-path``" を使ってください。
| To see information about all USB devices, use ``lsusb`` command. If you want to see more information about all USB-serial adpaters, use "``ls -l /dev/serial/by-id``" and "``ls -l /dev/serial/by-path``" commands.

.. code-block:: bash

    $ lsusb
    Bus 002 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub
    Bus 001 Device 003: ID 0403:6001 Future Technology Devices International, Ltd FT232 Serial (UART) IC
    Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
    $ ls -l /dev/serial/by-id
    total 0
    lrwxrwxrwx 1 root root 13 Jun 17 11:23 usb-FTDI_USB_Serial_Converter_FTE3YEM3-if00-port0 -> ../../ttyUSB0
    $ ls -l /dev/serial/by-path
    total 0
    lrwxrwxrwx 1 root root 13 Jun 17 11:23 pci-000:00:1d.0-usb-0:2.3:1.0-port0 -> ../../ttyUSB0

.. _section-usbserial-macos:

macOS
=====

| macOS Mojave以降には、以下のベンダのUSB-シリアル・アダプタ用カーネルドライバがシステムに組み込まれています。
| For macOS Mojave and later, kernel drivers for USB-serial adapters from the following vendors are built in the system.

- `FTDI <https://ftdichip.com>`_
- `WCH <https://www.wch-ic.com/>`_
- `Prolific Technology <https://www.prolific.com.tw>`_
- `Silicon Labs <https://www.silabs.com>`_
- CDC standard-compliant devices

| 本情報は以下のコマンド "``ls -l /System/Library/DriverExtensions/``" によって確認することができます。
| You can check this information by using "``ls -l /System/Library/DriverExtensions/``" command.

| ベンダ固有のUSB-シリアル・アダプタに対するデバイスファイルは ``/dev/tty.usbserial-*`` 、CDC規格準拠の場合は ``/dev/usbmodem*`` となります.
| Device files for vender specific USB-serial adapters will be ``/dev/tty.usbserial-*``. For CDC standard-compliant devices, they will be ``/dev/usbmodem*``.

.. _section-usbserial-windows:

Windows
=======

| Widowsでは、USB-シリアル・アダプタのドライバが自動的にインストールされるものとそうでないものがあり、これらはWindowsのバージョンによって異なります。
| Depending on the version of Windows, some drivers for USB-serial adapters are installed automatically and others are not.

| **Windows 11 24H2** で確認したところ、下記のような結果になりました:
| We checked for **Windows 11 24H2** and the results were as follows:

1. FTDI FT232X


.. image:: ./img/windows_devicemanager_usbserial_1.png
    :width: 800px
    :align: center


2. WCH CH34X


.. image:: ./img/windows_devicemanager_usbserial_2.png
    :width: 800px
    :align: center


3. Prolific Technology PL2303GT


.. image:: ./img/windows_devicemanager_usbserial_3.png
    :width: 800px
    :align: center


4. Prolific Technology PL2303TA



.. image:: ./img/windows_devicemanager_usbserial_4.png
    :width: 800px
    :align: center


5. Silicon Labs CP2102N


.. image:: ./img/windows_devicemanager_usbserial_5.png
    :width: 800px
    :align: center


| 4 と 5 のケースでは、ベンダ供給ドライバをインストールしないとWindowsでUSB-シリアル・アダプタを使用することはできません。
| In the case 4 and 5, it is necessary to install a vendor-supplied driver to use the USB-serial adapters on Windows.

| `Zadig <https://zadig.akeo.ie>`_ を利用すると、USB-シリアル・アダプタのベンダ供給ドライバをインストールすることができます。 
| You can use `Zadig <https://zadig.akeo.ie>`_ to install a vendor-supplied driver for the USB-serial adapters that Windows does not make available automatically.