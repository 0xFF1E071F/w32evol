# w32evol -- x86 obfuscation engine
- - -

* Original Author: 	Unknown
* Author: 					[Martin Velez](http://www.martinvelez.com)
* Copyright: 				Copyright (C) 2011 [Martin Velez](http://www.martinvelez.com)
* License: 					[GPL](http://www.gnu.org/copyleft/gpl.html)

## Description 

This repository contains a command line interface to the obfuscation engine 
used by the W32.Evol virus.

The Win32.Evol virus appeared around July 2000 and was able to infect any major
Win32 platform.  It used a metamorphic engine to rewrite its code during
replication.  Here is a more detailed description of the virus: 
[Symantec](http://www.symantec.com/security_response/writeup.jsp?docid=2000-122010-0045-99).

## Dependencies

### General

* [MAMS32](http://www.masm32.com/)
    * ml.exe: assembler 
    * link.exe: linker

### Linux (Tested on Ubuntu 11.10)

* [wine](http://www.winehq.org/download/) (>= 1.3 or greater, may work with 1.2)

## Installation

Files to build w32evol.exe are included.  
You can build under Linux and Windows.

### Linux (Tested on Ubuntu 11.10)

	$ make

### Windows
 
	> make.bat

## Usage

	w32evol.exe <infile.bin> <outfile.bin>

infile.bin: existing file, contains raw binary code which represents x86 
instructions

outfile.bin: nonexisting file, will contain obfuscated code if no error occurs 
during obfuscation

## Development
### Source 
Disassembled source code obtained from orriscariot@gmail.com.  Some of his
functions contained errors which cause the program to fail.  We obtained
executabled code from http://vx.netlux.org/vl.php?dir=Virus.Win32.Evol, 
and disassembled it using IDA Pro.  We found the mistakes in the 
disassembled source code and corrected them.

## Acknowledgements
* Orr
  * an OpenRCE.org[www.openrce.org/articles/full_view/27] user
  * wrote an article in which described how he disassembled the metamorphic 
    engine used in the W32.Evol virus
  * He  was kind enough to email his disassembled code.  
* {VX Heavens}[http://vx.netlux.org/vl.php?dir=Virus.Win32.Evol]


We wrote evol.asm which drives the W32/Evol obfuscation engine and provides
an appropriate command line interface.
