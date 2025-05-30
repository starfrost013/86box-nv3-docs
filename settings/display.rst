.. include:: /include.rst

|display| Display
=================

The **Display** page contains settings related to the emulated machine's 2D and 3D video cards.

Video
-----

Video card to emulate. This box only lists cards supported by the machine's expansion buses. On machines equipped with an onboard video chip, the *Internal* option enables the onboard video.

The *Configure* button opens a new window with settings specific to the selected video card, such as the amount of video memory.

Video #2
--------

Optional secondary video card to emulate. Only the **MDA**, **Hercules**, **Hercules Plus** and a limited set of **PCI VGA** cards are currently supported as secondary options. The secondary card's video output is displayed on a separate window.

As with the primary card above, the *Configure* button can be used to configure the selected card.

Voodoo Graphics
---------------

Emulate a **3dfx Voodoo** add-on 3D accelerator, connected to both the PCI bus and the video card selected above.

.. note:: The **Voodoo Banshee** and **Voodoo 3** are independent video cards, which are not found here; they must be selected on the :ref:`settings/display:Video` box above, and this Voodoo Graphics option **cannot be selected** alongside them. For these cards, the *Configure* button next to the :ref:`settings/display:Video` box provides similar settings to the ones listed below.

The *Configure* button provides the following settings:

* **Voodoo type:** type of Voodoo card to emulate.

   * **Voodoo Graphics:** the original Voodoo model, with a single Texture Mapping Unit operating at 50 MHz.
   * **Obsidian SB50 + Amethyst:** a variant of the Voodoo Graphics, with two Texture Mapping Units operating at 50 MHz.
   * **Voodoo 2:** the second Voodoo model, with two Texture Mapping Units operating at 90 MHz, as well as SLI support.

* **Framebuffer memory size** / **Texture memory size**: amount of video memory for the Frame Buffer Interface and Texture Mapping Unit(s), respectively.
* **Bilinear filtering:** apply bilinear filtering to smooth out textures displayed on screen.
* **Screen Filter:** apply a filter to make the screen picture resemble the DAC (digital-to-analog converter) output of a real Voodoo card.
* **Render threads:** split the workloads of each Voodoo card into different CPU threads for faster emulation. The recommended amount of render threads depends on your host system's CPU core count, and whether or not Voodoo 2 SLI is enabled:

+----------+--------------------------+
|Host cores|Recommended render threads|
|          +-----------+--------------+
|          |Single card|Voodoo 2 SLI  |
+==========+===========+==============+
|2         |1          |1             |
+----------+-----------+--------------+
|4         |2          |1             |
+----------+-----------+--------------+
|6 or 8    |4          |2             |
+----------+-----------+--------------+
|10 or more|4          |4             |
+----------+-----------+--------------+

* **SLI:** add a second Voodoo 2 card to the system, connected to the first one through a Scan Line Interleave (SLI) interface.
* **Dynamic Recompiler:** enable the Voodoo recompiler for faster emulation.

nVIDIA RIVA 128 (NV3)
---------------------

Emulate an **nVIDIA RIVA 128** 2D/3D accelerator, connected to the PCI or AGP buses.

.. note:: Emulation of the nVIDIA RIVA 128 is still in development. Bugs are to be expected.


The *Configure* button provides the following settings:

* **Chip revision:** Chip revision to emulate ()

   * **RIVA 128 prototype (January 1997):** Prototype model from January 1997 with an integrated sound card. Only switch to this if you know what you are doing.
   * **RIVA 128 (Revision B) (October 1997):** Released model with up to 4 MB of Video RAM. The default value.

* **VRAM:** The VRAM size on the card.

   * Can be 2 MB, 4 MB or 8 MB. 8 MB is only compatible with Revision C, though.

* **Model:** The Video BIOS to use.

   .. warning:: The "STB Velocity 128 Ver.1.60" Video BIOS (dated 8 August 1997) has a bug that prevents the Windows 98 and ME CD-ROM startup menus from displaying correctly. This can be worked around by either mashing the down button or using a different VBIOS. Windows 95 is not affected.

   * Allows selection of a vendor. Provides a subsystem ID which will alter the reported card name in Windows, and may slightly change the card's splash screen in some cases.

* **Render threads:**: Number of render threads to use in 3D rendering.

   * 1, 2, 4 and 8 can be selected. 

nVIDIA RIVA 128 ZX (NV3T)
-------------------------

Emulate an **nVIDIA RIVA 128ZX** 2D/3D accelerator, connected to the PCI or AGP buses.

.. note:: Emulation of the nVIDIA RIVA 128 ZX is still in development. Bugs are to be expected. Also, the Riva 128 ZX is always revision C and always has 8 MB of Video RAM.

* **Model:** The Video BIOS to use.

   * Allows selection of a vendor. Provides a subsystem ID which will alter the reported card name in Windows, and may slightly change the card's splash screen in some cases.

* **Render threads:**: Number of render threads to use in 3D rendering.

   * 1, 2, 4 and 8 can be selected. 


IBM 8514/A / XGA Graphics
-------------------------

Emulate an **IBM 8514/A** or **XGA** add-on graphics accelerator. Both the original IBM cards for the MCA bus and generic clone cards for the ISA bus are available; the correct card is automatically selected based on the machine's supported expansion buses.

The *Configure* button next to the XGA opens a new window where the card type (**XGA-1** or **XGA-2**) and initial BIOS address can be configured.

.. note:: Pairing the 8514/A and XGA with each other or with video cards from **ATI** or **S3** may result in compatibility issues, as each card implements a set of 8514/A features.
