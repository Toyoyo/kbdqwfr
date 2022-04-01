QWERTY-FR for Windows 3.0/3.1
CP1252-Compatible variant.

This is a Windows 3.x port of:
http://marin.jb.free.fr/qwerty-fr/

There's a few differences, as some characters from the keytable aren't available in CP1252.

Parts of this repository are from Win3.1 DDK and included to simplify the building process.
Namely:
DATE.INC: Copyright (C) 1989-1990 by Microsoft Corporation.
KEYBOARD.INC: Copyright (C) 1983,1984,1985,1986,1987,1988,1989,1990 by Microsoft Corp.
NAMESUS.INC: Copyright 1989, 1990 by Microsoft Corporation.
TRANS.INC: Copyright (C) 1988,1989,1990 by Microsoft Corporation.
VKOEM.INC: Copyright (C) 1989,1990 by Microsoft Corp.
VKWIN.INC: Copyright (C) 1989,1990 by Microsoft Corp.
GETKBD.ASM: Copyright (C) 1989-1990 by Microsoft Corporation.
NAMES.ASM: Copyright (C) 1989-1990 by Microsoft Corporation.

KBDQWFR.ASM is based on 'KBDUS.ASM', Copyright (C) 1989-1990 Microsoft Corporation.

Changed keybinds:
altgr-7 is acute-y instead instead of circumflex
altgr-= is equivalent to altgr-shift-=, 'NOT EQUAL TO' isn't in CP1252
altgr-/ is equivalent to altgr-shift-/, 'ARABIC QUESTION MARK' isn't in CP1252
shift-altgr-, is '...', 'OGONEK isn't in CP1252 and this one might useful
shift-altgr-. is 'MIDDLE DOT', might be useful (non-shifted variant already maps to 0xB0)

Removed keybinds:
altgr-t: 'pi' symbol isn't in CP1252.
altgr-f: Epsilon/Delta aren't in CP1252
altgr-g: Alpha/Beta aren't in CP1252
altgr-v: Omega isn't in CP1252
altgr->, altgr-<: 'GREATER-THAN OR EQUAL TO' & 'LESS-THAN OR EQUAL TO' aren't in CP1252

* How to build
You should have Win3.1 DDK installed:
https://winworldpc.com/download/3d0639c3-9e18-c39a-11c3-a4e284a2c3a5

Set PATH accordingly, eg:
set PATH=%PATH%;C:\MSVC\BIN
set LIB=C:\DEV\DDK\286\LIB
set INCLUDE=C:\DEV\DDK\286\INC

Then run 'nmake'.

* How to install
- Copy KBDQWFR.DLL to %windir%\SYSTEM\
- Edit %windir%\SYSTEM.INI:

In 'keyboard' section, add or replace the keyboard.dll line like this:
keyboard.dll=kbdqwfr.dll

A complete section should be like:
[keyboard]
keyboard.dll=kbdqwfr.dll
subtype=
type=4
oemansi.bin=xlat850.bin
