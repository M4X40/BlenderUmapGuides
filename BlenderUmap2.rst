This specific version of BlenderUmap is an unofficial fork, but don't let that scare you. BlenderUmap2 is much better than the original. 
This guide will go over how to install and optimal settings.

If you are using the Free Github version, you will need to build the addon yourself (we cover this).
For patrons, you can skip to `here <https://github.com/M4X40/BlenderUmapGuides/blob/main/BlenderUmap2.rst#installation-to-blender>`_ for installation.

I **HIGHLY RECCOMEND** to fully read this guide and not skip anything unless told explicitly so. This is for you, not to waste your time.

*Side Note for Github Users: The building process only documents how to do it on windows. A MacOS / Linux guide may come at a later date, but is not guarenteed.*

----

.. contents::

----

Requirements
============
Blender v3.y.z
--------------

Any version past Blender 3.0.0 will work. You can download blender `here <https://www.blender.org/download/>`_

Git
---

Git is a command-line tool used (in our case) to download Github repositories. Download it `here <https://git-scm.com/downloads>`_

Python 3
--------

Any version of Python 3 **SHOULD** work, however this is not confirmed. This will be used to build the addon for Github users.
You can download python `here <https://www.python.org/downloads/>`_. 
   **MAKE SURE** to check ``Add python to PATH`` once installation is finished.

FModel
------

FModel is an application for looking through packages of UE games, and we will use it to find what map you want.
Download FModel `here <https://fmodel.app/download>`_.

Some Technical Competence / Patience
------------------------------------

This is not a process for people not willing to learn and tinker with things. This guide wont hold your hand through everything. Errors and unexpected issues are bound to happen and thats not something I can control.
If you are experiencing issues; Don't give up or ask for help immediately. Instead, try to work out what went wrong and what you can do to fix it.

This process will also take time. If you don't have patience, then this isn't the hobby for you.

----

Now that all of that is out of the way, lets get into the build phase.

Downloading / Building the addon (for Free Github Users)
========================================================
1.  Make a new folder anywhere (I would recommend making it in your downloads) and enter it.
2.  In the address bar at the top, click the blank space in it and type ``cmd``, and press enter.
3.  Type the following command into the new Command Prompt window:

>>> git clone https://github.com/MinshuG/BlenderUmap2.git --recursive

4. Once that finishes, enter the new folder if needed to see ``make_release.py``.

5. Now run this:

>>> python make_release.py

Or if that doesn't work: 

>>> python3 make_release.py

5. Wait for this to finish. This **WILL** take a while
6. In the new ``Release`` folder, delete the ``MacOSX`` and ``Linux`` zip files, and just leave the windows one. This is the one we want.

And that is it! You have successfully built BlenderUmap2!

Installation to Blender
=======================

.. _install:

1. Open Blender
2. Go to ``Edit > Preferences > Add-Ons > Install``.
3. Select the zip file you downloaded (github users will choose the windows file we made earlier).
4. Enable with the check-box when installed.

General Use
===========

1. Click and drag this arrow to the left, opening this menu:
 .. image:: ./image_assets/arrow.png
2. Click the button the says ``Umap``.
3. Enter your games path, AES key, export path (where you want dumped files to go), and UE Version.
4. For the package, head over `here <https://github.com/M4X40/BlenderUmapGuides/blob/main/BlenderUmap2.rst#finding-your-package>`_ for how to get that.
5. At the top of Blender, ``Window > Toggle System Console``, and move this somewhere else for now.
6. Enter any settings you want and click ``Import``. This **WILL** TAKE TIME. For progress updates, check the system console we opened earlier.
  **NOTE: IF YOU WANT MATERIALS, TURN OFF** ``Generic Shader``.

Finding your Package
====================

1. Open FModel.
2. Go to ``Directory > Selector``.
3. Click the opposing arrows button at the bottom to open the Undetected Game menu,
4. Type your game's name  in its respective field.
5. For the directory, click the ellipsis (``...``), and navigate to ``[GAME PATH]\[gameName]\Content\Paks``.
6. Click the plus (``+``) to the right of the ellipsis and then ``OK``. Then click ``OK`` again on the prompt that appears.
7. Now go to ``Directory > AES`` and enter the game's AES key where prompted and click ``OK``.
8. Enter the pak file for your game. If your game has multiple files, choose the one that makes the most sense to you.
9. Look around and find the ``.umap`` file you want to port. Usually these will be in a \Maps\ folder.
10. Once you find the file, right click it and go ``Copy > Package Path``. 
  *SIDE NOTE: DO NOT CLICK* ``Package Path w/o extension``
11. Back in Blender, paste this into the ``Package`` field.


Optimal Settings for best performance / outcome
===============================================

Here is the settings I use every time I do a porting project:

::

  ☐ Use UE Custom Version
  ☑ Read Materials
  ☐ Export DDS When Possible
  ☐ Export Building Foundations (this is a fortnite thing)
  ☑ Export Hidden Actors
  ☐ Dump Assets
    Object Cache Size        0
  ☑ Reuse Maps
  ☑ Reuse Meshes
  ☑ Use Cube as Fallback Mesh (this can sometimes mess things up but I personally havent had any issues with it.)
  ☐ Use Generic Shader

No need to do anything in ``Texture Mapping`` or ``Advanced Options``. Default is good.

Troubleshooting
===============

Coming soon...
