# Getting Started

<div class="annotate" markdown>

This document is designed to help someone
boot a [Libre Computer] board
into an officially supported [GNU/Linux] distribution image of their choice
from a microSD card or eMMC module. (1)

???+ info "Advanced Boot Options"

    For more advanced boot options, see the
    [libretech-flash-tool repository].

</div>

1. This document will not cover the specifics of flashing an eMMC module.

## Requirements

<div class="annotate" markdown>

* a Libre Computer board (1)

* a secondary computer (PC) (2)

* a microSD card (3) and an appropriate adapter for the PC

    ??? tip

        The typical use case for a microSD card is not as
        the filesystem of an entire operating system.
        
        Plan accordingly.

* _optional_: an eMMC module (4)

    ??? tip
    
        Flashing an eMMC module requires
        a board that has already been booted
        into an operating system.
        Typically,
        this involves a flashed microSD card.

* _optional_: a secondary/tertiary storage drive (USB)

    ??? tip "Recommended"
    
        A secondary/tertiary drive is recommended for increased:
        
        * performance over microSD and eMMC
        
        * endurance with frequently written and overwritten files
        
* a micro USB power cable and an appropriate power supply

    ???+ info

        Libre Computer boards are specced for 5V input
        and most use 5W under full load
        ([AML-A311D-CC] is 10W).

        A +5% voltage should be within tolerance.
    
    ??? tip

        It is recommended to use at least a 5V 2.4A supply
        to avoid power stability issues,
        especially when attaching additional devices powered by the board
        (like USBs).

* an HDMI cable and monitor (5)

* a USB keyboard (6)

* _optional_: an ethernet cable or WiFi USB adapter (7)

    ??? tip

        You should complete any inital setup after first boot while offline.

        Performing the initial host setup while offline
        can avoid messy routing and IP leasing behaviors
        when you have predecided to reserve a static IP
        in your local network's DHCP server for the NIC.

</div>

1. as the hardware that will run an OS

2. for flashing an OS image to the microSD card

3. as the boot/root drives for the OS

4. as a replacement (or addition)
   to microSD as the boot/root drives,
   with higher performance and endurance

5. plus any converters necessary for the monitor to accept the HDMI source input

6. and mouse when using a GUI OS image

7. for network connectivity

## Procedure

### Download and decompress the OS image

<div class="annotate" markdown>

Using the PC,
download the official compressed image (1)
for the operating system of your choice
and decompress it.

There are many GNU/Linux distributions images
to choose from at the
[Libre Computer Products page][Libre Computer Products].
For a complete listing of your board's officially support operating systems:

1. click on your board

2. click the `Downloads` tab

Each download page should have instructions
to select a compatible image for your board.

You may verify the checksum of the download
if one has been made available.

</div>

1. typically a `*.img.xz` file

### Flash the OS image to microSD

<div class="annotate" markdown>

Using a tool like [Rufus] or [`dd`][dd],
copy the contents of the image (1) onto the microSD card.

When the process is complete,
the card should contain 2 partitions: (2)

1. a boot partition

2. a root filesystem partition

??? tip

    At this point,
    you could make modifications
    to the configuration files for
    the bootloader and OS
    on the microSD card.

</div>

1. the decompressed `*.img` file

2. images created for
   boards with a firmware bootloader
   may only have a root partition

### Boot the OS

<div class="annotate" markdown>

Insert the microSD card and attach peripherals (1)
to the board before applying suitable power via micro USB.

After some time,
you should start to see the boot sequence logs
and then be greeted with a login prompt.
Ensure that you can login using the method described
for the image.

</div>

1. HDMI monitor, USB keyboard, additional storage, etc.
