---?image=assets/images/gitpitch-audience.jpg
@title[EDK II UDK Debugger]
<br><br><br><br><br>
## <span class="gold"   >UEFI & EDK II Training</span>

#### EDK II UDK Debugger
<span style="font-size:0.75em" >Please be aware that this tool has been EOL<br>
The replacement is the <a href="https://software.intel.com/en-us/system-studio/choose-download">Intel System Studio Debugger</a>
</span>

<br>
<span style="font-size:0.75em" ><a href='http://www.tianocore.org'>tianocore.org</a></span>
Note:
  PITCHME.md for UEFI / EDK II Training  EDK II UDK Debugger Pres

  Copyright (c) 2018, Intel Corporation. All rights reserved.<BR>

  Redistribution and use in source (original document form) and 'compiled'
  forms (converted to PDF, epub, HTML and other formats) with or without
  modification, are permitted provided that the following conditions are met:

  1) Redistributions of source code (original document form) must retain the
     above copyright notice, this list of conditions and the following
     disclaimer as the first lines of this file unmodified.

  2) Redistributions in compiled form (transformed to other DTDs, converted to
     PDF, epub, HTML and other formats) must reproduce the above copyright
     notice, this list of conditions and the following disclaimer in the
     documentation and/or other materials provided with the distribution.

  THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR
  IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
  MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
  EVENT SHALL TIANOCORE PROJECT  BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
  SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
  PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS;
  OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
  WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR
  OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF
  ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.



---  
@title[Lesson Objective]
<BR>
### <p align="center"<span class="gold"   >Lesson Objective </span></p><br>

<!---  Add bullets using https://fontawesome.com/cheatsheet certificate
-->
<ul style="list-style-type:none">
 <li>@fa[certificate gp-bullet-green]<span style="font-size:0.9em">&nbsp;&nbsp;Identify the Intel® UEFI Development Kit Debugger<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; host and target basic configuration and components</span> </li>
 <li>@fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Access the debugger tools</span></li>
 <li>@fa[certificate gp-bullet-gold]<span style="font-size:0.9em">&nbsp;&nbsp;Make changes to the target firmware</span> </li>
 <li>@fa[certificate gp-bullet-ltgreen]<span style="font-size:0.9em">&nbsp;&nbsp;Launch the debug application</span></li>
 <li>@fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Use debug commands</span> </li>
 <li>@fa[certificate gp-bullet-magenta]<span style="font-size:0.9em">&nbsp;&nbsp;Debugging PI’s phases</span> </li>
</ul>

---?image=assets/images/binary-strings-black2.jpg
@title[UDK Debugger Overview Section]
<br><br><br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UDK Debugger Overview </span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Intel® UEFI Development Kit Debugger Tool</span>

Note:

---  
@title[UDK Debugger Overview]
<br>
<p align="center"<span class="gold"   ><b>Intel® UEFI Development Kit Debugger Tool </b></span></p>
<br>
@ul[no-bullet]
 - @fa[star gp-bullet-magenta]<span style="font-size:0.9em">&nbsp;&nbsp;Source level debug of UEFI firmware, drivers &<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; OpROM</span> 
 - @fa[star gp-bullet-gold]<span style="font-size:0.9em">&nbsp;&nbsp;Low-cost alternative to ITP/JTAG debug</span> 
 - @fa[star gp-bullet-green]<span style="font-size:0.9em">&nbsp;&nbsp;Host-to-target connect via COM port or USB debug<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; port</span> 
 - @fa[star gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Open source based on existing software debuggers <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;for Windows & Linux</span>
 - @fa[star gp-bullet-ltgreen]<span style="font-size:0.9em">&nbsp;&nbsp;User Manual PDF</span>
@ulend


Note:


---?image=/assets/images/slides2/Slide5.JPG
@title[UDK Debugger tool block diagram]

<p align="center"><span class="gold" ><b>Intel® UEFI Development Kit Debugger Tool</b></span></p>

@snap[south span-95  fragment]
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:60%"><span style="font-size:0.9em">Source Level Debugger for UEFI<br>&nbsp;</span></p>)
@snapend

Note:

- This slide represents a block diagram of the Host machine connected to the Target using the Host Debugger tools
  - Linux GDB
  - Windows WinDBG
- The build of the target machine needs to be on the host including all the debug and symbol file information
- the UDK Debugger works like a layer inbetween the host machines debugger to intercept the information coming to /from the target debug output
- The target machine needs to also be built with the SourceDebugPkg  libraries.

### Source Level Debugger for UEFI - EDK II


---?image=/assets/images/slides2/Slide6.JPG
@title[Host & Target Debug Setup]
<p align="right"><span class="gold" ><b>Host & Target Debug Setup</b></span></p>
@snap[north span-35  ]
<br>
<br>
<p style="line-height:80%" align="center"><span style="font-size:0.9em">
Null Modem Cable or<br> USB 2.0 Debug or USB 3.0 Cable
</span></p>
@snapend

Note:




---
@title[Distribution ]
<p align="center"><span class="gold" ><b>Distribution </b></span></p>
<span style="font-size:0.8em" > Tool EOL replaced by Replaced by <a href="https://software.intel.com/en-us/system-studio/choose-download">Intel System Studio</a> 
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<span style="font-size:0.6em" >Target source: `SourceLevelDebugPkg` at @fa[github gp-bullet-gold]<span style="font-size:0.8em">&nbsp;&nbsp;<a href="https://github.com/tianocore/tianocore.github.io/wiki/SourceLevelDebugPkg">Tianocore.org </a>

Note:

- Binary application for host on Windows or Linux from http://firmware.intel.com
- Source code for Target from tianocore.org via github



---?image=/assets/images/slides2/Slide8.JPG
@title[Host Configuration Requirements - Windows ]
<p align="right"><span class="gold" ><b>Host Configuration Requirements </b></span></p>
<br>
@fa[windows gp-bullet-cyan]<span style="font-size:01.1em" >&nbsp;&nbsp;Microsoft Windows </span>
<br>
<br>
<ul>
  <li><span style="font-size:0.9em" >XP with Service Pack 3 and Windows 7 and Windows 10</span></li>
  <li><span style="font-size:0.9em" >Debug Tool (WINDBG) x86, version 6.11.0001.404</span></li>
  <li><span style="font-size:0.9em" >Intel UDK Debugger Tool </span></li>
  <li><span style="font-size:0.9em" >WinDBG Extensions in edk2.dll <a href="http://msdl.microsoft.com/download/symbols/debuggers/dbg_x86_6.11.1.404.msi">http://msdl.microsoft.com/ ... /dbg_x86_6.11.1.404.msi </a></span></li><br>
  <li><span style="font-size:0.5em" >Details on WinDBG - <a href="https://gitpitch.com/Laurie0131/EDK_II_UDK_Debugger_pres/master#/44"> Debugging using WinDBG</a> </span></li>
  
</ul>

Note:
- May need to search for the version of WinDBG


---?image=/assets/images/slides2/Slide9.JPG
@title[Host Configuration Requirements - Linux ]
<p align="right"><span class="gold" ><b>Host Configuration Requirements </b></span></p>
<br>
@fa[linux gp-bullet-white]<span style="font-size:01.1em" >&nbsp;&nbsp;Linux</span>
<br>
<br>
<br>
<ul>
  <li><span style="font-size:0.9em" >Ubuntu 16.04 LTS client (x64 build)</span><span style="font-size:0.6em" >- validated and examples shown</span></li><br>
  <li><span style="font-size:0.9em" >GNU Debugger (GDB) - </span><span style="font-size:0.7em" >with Expat library</span></li><br>
  <li><span style="font-size:0.9em" >Intel UDK Debugger Tool 1.5.1 </span></li>
</ul>

Note:


---?image=/assets/images/slides/Slide12.JPG
@title[Host Configuration Requirements - Linux GDB ]
<p align="right"><span class="gold" ><b>Host Configuration Requirements -GDB </b></span></p>
<span style="font-size:0.9em" >Check for the configuration of GDB that is installed  </span>
```bash
bash$ gdb --configuration
```

<div class="left">
<span style="font-size:0.7em" > Install `gdb` if not installed</span>
<pre class='bash'>
```
bash$ sudo apt-get update
bash$ sudo apt-get install gdb
```
</pre>
<p style="line-height:60%"><span style="font-size:0.6em" > Download `gdb` source and compile with Expat library if there is <font color="yellow"><b>no</b></font> "`--with-expat`" as on the screen shot here</span></p>
<pre class='bash'>
```
bash$ ./configure --target=x86_64-w64-mingw32 --with-expat
bash$ make
```
</pre> 
</div>
<div class="right">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>

Note:

- If need to compile with expat
<pre>
 // 1. Download and extract
 bash$ wget "http://ftp.gnu.org/gnu/gdb/gdb-7.11.tar.gz" 
 bash$ tar -xvzf gdb-7.11.tar.gz 
 // 2. Configure and compile
 bash$ apt-get install libexpat1-dev
 bash$ apt-get install expat
 bash$ cd gdb-7.11
 bash$ ./configure --target=x86_64-w64-mingw32 --with-expat
 bash$ make 
 // 3. install
 bash$ make install

</pre>

---?image=/assets/images/slides/Slide13.JPG
@title[Install UDK Debugger - Linux ]
<p align="right"><span class="gold" ><b>Install UDK Debugger - Linux</b></span></p>
<span style="font-size:0.75em" >Please be aware that this tool has been EOL<br>
The replacement is the <a href="https://software.intel.com/en-us/system-studio/choose-download">Intel System Studio Debugger</a>
</span>
<br>
<div class="left1">
<span style="font-size:0.7em" > Extract the .zip file to a temp directory</span>
<pre class='bash'>
```
bash$ cd <temp-directory>
bash$ sudo chmod +x UDK_Debugger_Tool_v1_5_1.bin
  // run the installer
bash$ sudo ./UDK_Debugger_Tool_v1_5_1.bin
```
</pre>
<p style="line-height:70%"><span style="font-size:0.7em" >The tool will be installed to `/opt/intel/udkdebugger` by default</span></p>
<p style="line-height:70%"><span style="font-size:0.7em" >Configuration file:  `/etc/udkdebugger.conf` </span></p>
</div>
<div class="right1">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>


Note:

+++?image=/assets/images/slides/Slide14.JPG
@title[Install UDK Debugger - Linux 02]
<p align="right"><span class="gold" ><b>Install UDK Debugger - Linux</b></span></p>
<span style="font-size:0.9em" >Menu to configure the tool for the port</span>
<br>
<div class="left1">
<span style="font-size:0.7em" > Configure Debug Port Menu</span>
<pre class='bash'>
```
 // Debug Port Channel
   Serial or USB
 // Port:  using FTDI USB Serial use `bash$ dmesg` to check 
   /dev/ttyUSB0
 // Baudrate:
   115200
 // Flow control  
   none
```
</pre>
<p style="line-height:70%"><span style="font-size:0.7em" >Configuration file:  `/etc/udkdebugger.conf` </span></p>
</div>
<div class="right1">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>


Note:


---?image=/assets/images/slides2/Slide13.JPG
@title[Debug Cable Options]
<p align="right"><span class="gold" ><b>Debug Cable Options</b></span></p>

@snap[north-west span-30  ]
<br>
<br>

<p style="line-height:60%" align="left"><span style="font-size:0.7em"><br>
@size[1.2em](<font color="#A8ff60"><b>Serial Null Modem</b></font>)<br>
<br><br><br><br><br><br><br>
&bull;&nbsp;&nbsp;@size[.85em](Target must support standard RS-232 COM port)<br>
&bull;&nbsp;&nbsp;@size[.85em](Host can support standard RS-232 or USB COM port)<br>
&bull;&nbsp;&nbsp;@size[.85em](Supported by Windows & Linux)<br>
</span></p>
@snapend

@snap[north span-30  fragment]
<br>
<br>

<p style="line-height:60%" align="left"><span style="font-size:0.7em"><br>
@size[1.2em](<font color="#A8ff60"><b>&nbsp;&nbsp;USB 2.0 Debug</b></font>)<br>
<br><br><br><br><br><br><br>
&bull;&nbsp;&nbsp;@size[.85em](EHCI debug descriptor &lpar;using NET20DC adapter or AMI Debug Rx device&rpar;)<br>
&bull;&nbsp;&nbsp;@size[.85em](Target must support USB 2.0 EHCI debug port)<br>
</span></p>
@snapend

@snap[north-east span-30 fragment]
<br>
<br>

<p style="line-height:60%" align="left"><span style="font-size:0.7em"><br>
@size[1.2em](<font color="#A8ff60"><b>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;USB 3.0</b></font>)<br>
<br><br><br><br><br><br><br>
&nbsp;&nbsp;&bull;&nbsp;&nbsp;@size[.85em](Added Release 1.5)<br>
</span></p>
@snapend

Note:

- Serial Null Modem
- USB 2.0 Debug
- USB 3.0

---?image=assets/images/binary-strings-black2.jpg
@title[Changes to target Section]
<br><br><br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Changes to target</span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Required changes needed to be built with the target <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;platform</span>

Note:

---?image=/assets/images/slides/Slide20.JPG
@title[Changes to Target Firmware]
<p align="center"><span class="gold" ><b>Changes to Target Firmware</b></span></p>
<span style="font-size:0.9em" ><font color="#A8ff60"> Goal: Minimize changes to target firmware</font>  </span>
<br>
<br>
<br>
<div class="left">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>
<div class="right">
<span style="font-size:0.8em" >Add call to the library class (`DebugAgentLib`) In `SEC`, `DXE` Main, and `SMM CPU` Modules</span>
<br>
<br>
<span style="font-size:0.8em" >Or if you don’t want to add one A `NULL` implementation of `DebugAgentLib` is checked into open source </span>
</div>

Note:
- Goal: Minimize changes to target firmware

- Add call to new library class (DebugAgentLib) One in SEC, one in DXE Main, one in SMM CPU Module
- Or if you don’t want to add one A NULL implementation of DebugAgentLib will be checked into open source so all modules can build with debug feature disabled


---
@title[Updates to DSC]
<p align="right"><span class="gold" ><b>Updates to DSC</b></span></p>

@snap[north-west span-100 ]
<p style="line-height:70%" align="center"><span style="font-size:0.8em"><br><br><br>&nbsp;</span></p>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%" align="left"><span style="font-size:0.8em"><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend


@snap[north-west span-50 ]
<p style="line-height:70%" align="center"><span style="font-size:0.8em"><font color="#A8ff60"><br><br>
<b>Libraries</b><br>
&nbsp;</font></span></p>
<p style="line-height:60%" align="left"><span style="font-size:0.460em; font-family:Consolas; " >
&nbsp;&nbsp;[LibraryClasess]  <font face="Arial"><b>General</b></font><br>&nbsp;&nbsp;&nbsp;&nbsp;
PeCoffExtraActionLib<br>&nbsp;&nbsp;&nbsp;&nbsp;
DebugCommunicationLib<br>
<br> 
<br>
&nbsp;&nbsp;[LibraryClasses.IA32] <font face="Arial"><b>SEC / PEI</b></font><br>&nbsp;&nbsp;&nbsp;&nbsp;
DebugAgentLib<br>
<br>
&nbsp;&nbsp;[LibraryClasses.X64] <font face="Arial"><b>DXE</b></font><br>&nbsp;&nbsp;&nbsp;&nbsp;
DebugAgentLib<br>
<br>
&nbsp;&nbsp;[LibraryClasses.X64.DXE_SMM_DRIVER] <font face="Arial"><b>SMM</b></font><br>&nbsp;&nbsp;&nbsp;&nbsp;
DebugAgentLib<br>
<br>
</span></p>
@snapend



@snap[north-east span-55 ]
<p style="line-height:70%" align="center"><span style="font-size:0.8em"><font color="#A8ff60"><br><br>
<b>`SourceLevelDebugPkg`<br>Lib Instance</b>
&nbsp;
</font></span></p>
<p style="line-height:60%" align="left"><span style="font-size:0.460em; font-family:Consolas; " ><br>
<font color="#FFC000">@size[1.5em](&#10147;)</font>&nbsp;&nbsp;PeCoffExtraActionLibDebug.inf<br>
<font color="#FFC000">@size[1.5em](&#10147;)</font>&nbsp;&nbsp;DebugCommunicationLibSerialPort.inf <br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <font face="Arial">or</font><br>
<font color="#FFC000">@size[1.5em](&#10147;)</font>&nbsp;&nbsp;DebugCommunicationLibUsb.inf<br>
<br>
<font color="#FFC000">@size[1.5em](&#10147;)</font>&nbsp;&nbsp;SecPeiDebugAgentLib.inf<br>
<br>
<br>
<font color="#FFC000">@size[1.5em](&#10147;)</font>&nbsp;&nbsp;DxeDebugAgentLib.inf<br>
<br>
<br>
<font color="#FFC000">@size[1.5em](&#10147;)</font>&nbsp;&nbsp;SmmDebugAgentLib.inf
</span></p>
@snapend


@snap[north-east span-60  fragment]
<p style="line-height:70%" align="center"><span style="font-size:0.8em"><br><br>
<br>
&nbsp;
</span></p>
<p style="line-height:30%" align="left"><span style="font-size:0.5em"><br><br><br><br><br><br>
<br>
<br>
&nbsp;&nbsp;&nbsp;&nbsp;<font color="#FF00FF">@size[4.5em](&lbrace;)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
@size[4.5em](&rbrace;)
</font><br>
<br>
<br>
</span></p>
@snapend


@snap[north-east span-65  fragment]
<p style="line-height:70%" align="center"><span style="font-size:0.8em"><br><br>
<br>
&nbsp;
</span></p>
<p style="line-height:60%" align="left"><span style="font-size:0.5em"><br>
<br><font color="yellow">
&nbsp;&nbsp;&nbsp;&nbsp;COM1&nbsp;&nbsp;</font><br>
&nbsp;&nbsp;&nbsp;&nbsp;OR<br><font color="yellow">
&nbsp;&nbsp;&nbsp;&nbsp;USB&nbsp;&nbsp;<br>
</font></span></p>
@snapend

Note:

 

#### Library class sections
<pre class='bash'>
 [LibraryClasess]  General
  PeCoffExtraActionLib PeCoffExtraActionLibDebug.inf

 DebugCommunicationLib
   DebugCommunicationLibSerialPort.inf
     or
   DebugCommunicationLibUsb.inf

 [LibraryClasses.IA32] SEC/PEI
  DebugAgentLib SecPeiDebugAgentLib.inf

 [LibraryClasses.X64] DXE
  DebugAgentLib DxeDebugAgentLib.inf

 [LibraryClasses.X64.DXE_SMM_DRIVER] SMM
  DebugAgentLib SmmDebugAgentLib.inf
</pre>



---
@title[Updates to DSC USB 3.0]
<p align="right"><span class="gold" ><b>Updates to DSC for USB 3.0</b></span></p>

@snap[north-west span-100 ]
<p style="line-height:70%" align="center"><span style="font-size:0.8em"><br><br><br>&nbsp;</span></p>
@box[bg-grey-15 text-white rounded my-box-pad2  ](<p style="line-height:60%" align="left"><span style="font-size:0.8em"><br><br><br><br><br><br><br><br><br><br><br><br><br><br>&nbsp;</span></p>)
@snapend

@snap[north-west span-50 ]
<p style="line-height:70%" align="center"><span style="font-size:0.8em"><font color="#A8ff60"><br><br>
<b>Libraries</b><br>
&nbsp;</font></span></p>
<p style="line-height:60%" align="left"><span style="font-size:0.460em; font-family:Consolas; " >
&nbsp;&nbsp;[LibraryClasess]  <font face="Arial"><b>General</b></font><br>&nbsp;&nbsp;&nbsp;&nbsp;
PeCoffExtraActionLib<br>&nbsp;&nbsp;&nbsp;&nbsp;
<br>
&nbsp;&nbsp;[LibraryClasses.IA32] <font face="Arial"><b>SEC / PEI</b></font><br>&nbsp;&nbsp;&nbsp;&nbsp;
DebugCommunicationLib<br>&nbsp;&nbsp;&nbsp;&nbsp;
DebugAgentLib<br>
<br>
&nbsp;&nbsp;[LibraryClasses.X64] <font face="Arial"><b>DXE</b></font><br>&nbsp;&nbsp;&nbsp;&nbsp;
DebugCommunicationLib<br>&nbsp;&nbsp;&nbsp;&nbsp;
DebugAgentLib<br>
<br>
&nbsp;&nbsp;[LibraryClasses.X64.DXE_SMM_DRIVER] <font face="Arial"><b>SMM</b></font><br>&nbsp;&nbsp;&nbsp;&nbsp;
DebugCommunicationLib<br>&nbsp;&nbsp;&nbsp;&nbsp;
DebugAgentLib<br>
<br>
</span></p>
@snapend



@snap[north-east span-55 ]
<p style="line-height:70%" align="center"><span style="font-size:0.8em"><font color="#A8ff60"><br><br>
<b>`SourceLevelDebugPkg`<br>Lib Instance</b>
&nbsp;
</font></span></p>
<p style="line-height:60%" align="left"><span style="font-size:0.460em; font-family:Consolas; " ><br>
<font color="#FFC000">@size[1.5em](&#10147;)</font>&nbsp;&nbsp;PeCoffExtraActionLibDebug.inf<br>
<br>
<br>
<font color="#FFC000">@size[1.5em](&#10147;)</font>&nbsp;&nbsp;DebugCommunicationLibUsb3Pei.inf<br>
<font color="#FFC000">@size[1.5em](&#10147;)</font>&nbsp;&nbsp;SecPeiDebugAgentLib.inf<br>
<br>
<br>
<font color="#FFC000">@size[1.5em](&#10147;)</font>&nbsp;&nbsp;DebugCommunicationLibUsb3Dxe.inf<br>
<font color="#FFC000">@size[1.5em](&#10147;)</font>&nbsp;&nbsp;DxeDebugAgentLib.inf<br>
<br>
<br>
<font color="#FFC000">@size[1.5em](&#10147;)</font>&nbsp;&nbsp;DebugCommunicationLibUsb3Dxe.inf<br>
<font color="#FFC000">@size[1.5em](&#10147;)</font>&nbsp;&nbsp;SmmDebugAgentLib.inf
</span></p>
@snapend





Note:

#### Library class sections for USB 3.0
<pre class='bash'>
 [LibraryClasess]  General
  PeCoffExtraActionLib PeCoffExtraActionLibDebug.inf

 [LibraryClasses.IA32] SEC/PEI
  DebugAgentLib SecPeiDebugAgentLib.inf
  DebugCommunicationLib DebugCommunicationLibUsb3Pei.inf

 [LibraryClasses.X64] DXE
  DebugAgentLib DxeDebugAgentLib.inf
  DebugCommunicationLib DebugCommunicationLibUsb3Dxe.inf

 [LibraryClasses.X64.DXE_SMM_DRIVER] SMM
  DebugAgentLib SmmDebugAgentLib.inf
  DebugCommunicationLib DebugCommunicationLibUsb3Dxe.inf
</pre>




---
@title[Updates to FDF]
<p align="right"><span class="gold" ><b>Updates to FDF</b></span></p>
<br>
<p style="line-height:80%"><span style="font-size:0.9em" >Update for the Firmware Volume `FVMAIN`</span><span style="font-size:0.7em" ><br> - this is so there is no conflict with the terminal console driver</span></p>
```php
[FV.FVMAIN]
. . .
#  DXE Phase modules
. . .
# Comment out module for Terminal driver
# INF  IntelFrameworkModulePkg/Bus/Isa/IsaSerialDxe/IsaSerialDxe.inf
```
<span style="font-size:0.9em" >Updates to INF </span><span style="font-size:0.5em" > - Default with "Debug" builds</span>
```php
 //. . .
[BuildOptions]
  MSFT:*_*_*_CC_FLAGS = /Od /Oy-
```

Note:


---
@title[Configure COM Port (PCD) (Target)]
<p align="right"><span class="gold" ><b>Configure COM Port (PCD) (Target)</b></span></p>
<br>
<ul style="list-style-type:none">
 <li>@fa[bullseye gp-bullet-green]<span style="font-size:0.9em">&nbsp;&nbsp;Configure target to use COM port via PCD</span> </li>
 <li>@fa[bullseye gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Ensure COM port not used by other project<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; modules/features</span> </li>
 <li>@fa[bullseye gp-bullet-magenta]<span style="font-size:0.9em">&nbsp;&nbsp;COM 1 is the default on target</span> </li>
 <li>@fa[bullseye gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Simple “ASCII Print” though COM port is allowed</span> </li>
 <li>@fa[bullseye gp-bullet-ltgreen]<span style="font-size:0.9em">&nbsp;&nbsp;Non-NULL DebugAgent library instance must be used</span> </li>
</ul>


---?image=/assets/images/slides/Slide14.JPG
@title[Configure Host - Linux ]
<p align="right"><span class="gold" ><b>Configure the Host - Linux</b></span></p>
<span style="font-size:0.9em" >Menu to configure the tool for the port on installation</span>
<br>
<div class="left1">
<span style="font-size:0.7em" > Configure Debug Port Menu</span>
<pre class='bash'>
```
 // Debug Port Channel
   Serial or USB
 // Port:  using FTDI USB Serial use `bash$ dmesg` to check 
   /dev/ttyUSB0
 // Baudrate:
   115200
 // Flow control  
   none
```
</pre>
<p style="line-height:70%"><span style="font-size:0.7em" ><font color="yellow">OR</font> update the Configuration file:  `/etc/udkdebugger.conf` </span></p>
</div>
<div class="right1">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>


Note:



---?image=assets/images/binary-strings-black2.jpg
@title[Debugging using GDB Section]
<br><br><br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Debugging using GDB</span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>

Note:

---
@title[Source Level Debug Features]
<p align="right"><span class="gold" ><b>Source Level Debug Features</b></span></p>
<br>
@ul[no-bullet]
- <span style="font-size:01.0em" >&nbsp;<span style="background-color: #7030a0"><b>&nbsp;&nbsp;View call stack</b> &nbsp;&nbsp;</b></span><span style="background-color: #92d050"><b>&nbsp;Go&nbsp;</b></span></p>
- <span style="font-size:01.0em" >&nbsp;<span style="background-color: #BF5122">&nbsp;&nbsp;<b>Insert `CpuBreakpoint()`</b>&nbsp;&nbsp;</span></span><br><br>
- <span style="font-size:01.0em" >&nbsp;<span style="background-color: #00b0f0">&nbsp;&nbsp;<b>View and edit local/global variables</b>&nbsp;&nbsp;</span></span><br><br>
- <span style="font-size:01.0em" >&nbsp;<span style="background-color: #202020"><b>&nbsp;&nbsp;Set breakpoint</b> &nbsp;&nbsp;</b></span><span style="background-color: #7030a0"><b>&nbsp;Step into/over routines&nbsp;</b></span></p>
- <span style="font-size:01.0em" >&nbsp;<span style="background-color: #e49436"><b>&nbsp;&nbsp;Go till</b> &nbsp;&nbsp;</b></span><span style="background-color: #92d050"><b>&nbsp;View disassembled code&nbsp;</b></span></p>
- <span style="font-size:01.0em" >&nbsp;<span style="background-color: #BF5122">&nbsp;&nbsp;<b>View/edit general purpose register values&nbsp;</b>&nbsp;&nbsp;</span></span><br>
@ulend

Note:

- use gdb help to see how to 



---?image=/assets/images/slides/Slide35.JPG
@title[Launching UDK Debugger- Linux udk ]
<p align="right"><span class="gold" ><b>Launching UDK Debugger- Linux </b></span></p>
<span style="font-size:0.9em" >Example showing Ubuntu 16.04 LTS with GDB </span>
<br>
<br>
<div class="left">
<span style="font-size:0.7em" > Need to open 3 Terminal prompt windows<br>First Terminal(1) is the UDK debugger server </span>

<pre class='bash'>
```
 bash$ cd opt/intel/udkdebugger
 bash$ ./bin/udk-gdb-server
```
</pre>
<span style="font-size:0.7em" > Power on the Target and wait 2-3 seconds</span><br>
</div>
<div class="right">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>

Note:


---?image=/assets/images/slides/Slide36.JPG
@title[Launching UDK Debugger- Linux gdb]
<p align="right"><span class="gold" ><b>Launching UDK Debugger- Linux </b></span></p>
<span style="font-size:0.9em" >Example showing Ubuntu 16.04 LTS with GDB </span>
<br>
<br>
<div class="left">
<span style="font-size:0.7em" > Open a second  Terminal(2) for GDB </span>
<pre class='bash'>
```
 bash$ cd opt/intel/udkdebugger
 bash$ gdb
```
</pre>
<span style="font-size:0.7em" > Attach to the UDK debugger</span>
<pre class='bash'>
```
 (gdb) target remote <HOST>:1234
```
</pre>
<span style="font-size:0.7em" > Terminal(1) will show "Connection from localhost" message</span>
</div>
<div class="right">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>

Note:



---?image=/assets/images/slides/Slide37.JPG
@title[Launching UDK Debugger- Linux -scripts]
<p align="right"><span class="gold" ><b>Launching UDK Debugger- Linux </b></span></p>
<span style="font-size:0.9em" >Example showing Ubuntu 16.04 LTS with GDB </span>
<br>
<br>
<div class="left">
<span style="font-size:0.7em" > Open the udk scripts in  GDB - Terminal(2) </span>
<pre class='bash'>
```
 (gdb) source ./script/udk_gdb_script
```
</pre>
<p style="line-height:70%"><span style="font-size:0.7em" > Symbols will show for PeiCore, also notice the prompt changes from "(gdb)" to "(udb)"</span></p>
</div>
<div class="right">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>

Note:



---?image=/assets/images/slides/Slide38.JPG
@title[Launching UDK Debugger- terminal]
<p align="right"><span class="gold" ><b>Launching UDK Debugger- Linux </b></span></p>
<br>
<p style="line-height:90%"><span style="font-size:0.9em" >Optional - open a 3rd Terminal(3) with a terminal program</span><span style="font-size:0.7em" ><br> - &nbsp; Example showing "screen" terminal program</span></p>
<br>

Note:

- most debugging will be from Teriminal(2) 
- terminal (3) is just to see where it is.



---?image=/assets/images/slides/Slide42.JPG
@title[UDK Debugger - setting break points]
<p align="right"><span class="gold" ><b>UDK Debugger - Setting break points</b></span></p>
<br>
<br>
<div class="left">
<span style="font-size:0.7em" >Terminal(2) Breakpoint at PeiDispatcher </span>
<pre class='bash'>
```
 (udb) b PeiDispatcher
```
</pre>
<span style="font-size:0.7em" > Break at Port 0x80</span>
<pre class='bash'>
```
 (udb)iowatch/b 0x80
```
</pre>
<span style="font-size:0.7em" > Break at absolute address</span>
<pre class='bash'>
```
 (udb)b *0xfff94a68
```
</pre>
</div>
<div class="right">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>

Note:


---?image=assets/images/binary-strings-black2.jpg
@title[Debugging through Boot phases Section]
<br><br><br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Debugging Thru boot flow</span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>

Note:




---?image=/assets/images/slides/Slide43.JPG
<!-- .slide: data-transition="none" -->
@title[Debugging the Boot Phases]
<p align="center"><span class="gold" ><b>Debugging the Boot Phases</b></span></p>


Note:


+++?image=/assets/images/slides/Slide44.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Debugging the Boot Phases 02]
<p align="center"><span class="gold" ><b>Debugging the Boot Phases</b></span></p>


Note:


+++?image=/assets/images/slides/Slide45.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Debugging the Boot Phases 03]
<p align="center"><span class="gold" ><b>Debugging the Boot Phases</b></span></p>


Note:


+++?image=/assets/images/slides/Slide46.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Debugging the Boot Phases 04]
<p align="center"><span class="gold" ><b>Debugging the Boot Phases</b></span></p>


Note:


---?image=/assets/images/slides/Slide48.JPG
@title[Debugging the Boot Phases SEC]
<p align="center"><span class="gold" ><b>Debugging the Boot Phases - SEC</b></span></p>

<div class="left-2">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>
<div class="right-2">
<span style="font-size:0.8em" >Debugging Sec phase</span>
<br>
<br>
<span style="font-size:0.8em" ></span>
</div>

@snap[south-west span-100 fragment ]
<p style="line-height:70%" align="left"><span style="font-size:0.90em;  " >
@size[8em](@color[red](X))&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;@color[yellow](<b>SORRY</b>) - Requires a hardware debugger
</span></p>
<br>
<br>
@snapend

Note:


SEC Must use hardware debugger, not Intel® UEFI Development Kit Debugger

---?image=/assets/images/slides/Slide50.JPG
@title[Debugging the Boot Phases PEI]
<p align="center"><span class="gold" ><b>Debugging the Boot Phases - PEI</b></span></p>
<br>
<br>
<div class="left-1">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>
<div class="right-1">
<ul style="list-style-type:disc">
 <li><span style="font-size:0.8em" >Use debugger prior to PEI Main</span></li>
 <li><span style="font-size:0.8em" >Check proper execution of PEI drivers </span></li>
 <li><span style="font-size:0.8em" >Execute basic chipset & Memory init. </span></li>
 <li><span style="font-size:0.8em" >Check memory availability</span></li>
 <li><span style="font-size:0.8em" >Complete flash accessibility</span></li>
 <li><span style="font-size:0.8em" >Execute recovery driver </span></li>
 <li><span style="font-size:0.8em" >Detect DXE IPL</span></li>
 </ul>
</div>


Note:

- SEC Must use hardware debugger, not Intel® UEFI Development Kit Debugger
- Begin using debugger prior to PEI Main
- Check proper execution of all PEI drivers 
- Execute basic chipset initialization 
- Execute memory initialization instructions
- Check availability of memory
- Complete flash accessibility
- Execute recovery driver if the recovery jumper is selected, and execution of recovery path if recovery is detected 
- Detection of DXE IPL PEIM which in turn detects and launches the DXE core

---
@title[PEI Phase: Trace Each PEIM]
<p align="center"><span class="gold" ><b>PEI Phase: Trace Each PEIM</b></span></p>
<br>
<span style="font-size:0.8em" >There is a loop function in : </span><br>
@fa[github gp-bullet-gold]<span style="font-size:0.8em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Core/Pei/Dispatcher">MdeModulePkg/Core/Pei/Dispatcher/Dispatcher.c </a></span><br>
<span style="font-size:0.8em" >Add `CpuBreakpoint();` before launching each PEIM</span>

```c
VOID
PeiDispatcher (
  IN CONST EFI_SEC_PEI_HAND_OFF  *SecCoreData,
  IN PEI_CORE_INSTANCE           *Private
  )
{// ...
        // Call the PEIM entry point
        //
        PeimEntryPoint = (EFI_PEIM_ENTRY_POINT2)(UINTN)EntryPoint;
        PERF_START (PeimFileHandle, "PEIM", NULL, 0);
// Add a call to CpuBreakpoint();  approx. line 1004
        CpuBreakpoint();
        PeimEntryPoint(PeimFileHandle, (const EFI_PEI_SERVICES **) &Private->Ps);
```

Note:


- For Loop in Function: PeiDispatcher()
	- MdeModulePkg/Core/Pei/Dispatcher/Dispatcher.c

- Trace all PEIMs dispatched in PEIMAIN module 
- PeiDispatcher() function - set a break point at the main dispatch loop before each PEIM Entry
	- // Call the PEIM entry point
- 	CpuBreakpoint() ;
	- PeimEntryPoint(PeimFileHandle, (const EFI_PEI_SERVICES **) &Private->Ps);
- On breakpoint, step into function to trace PEIMs

---
@title[Check for transition from PEI to DXE]
<p align="center"><span class="gold" ><b>Check for transition from PEI to DXE</b></span></p>
<br>
<span style="font-size:0.8em" >Critical point before calling DXE in: </span><br>
@fa[github gp-bullet-gold]<span style="font-size:0.8em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Core/Pei/PeiMain">MdeModulePkg/Core/Pei/PeiMain.c </a></span><br>
<span style="font-size:0.8em" >Add `CpuBreakpoint();` before entering DxeIpl</span>

```c
VOID
EFIAPI
PeiCore (
  IN CONST EFI_SEC_PEI_HAND_OFF        *SecCoreDataPtr,
  IN CONST EFI_PEI_PPI_DESCRIPTOR      *PpiList,
  IN VOID                              *Data
  )
{ // ...
  // Enter DxeIpl to load Dxe core.
  //
  DEBUG ((EFI_D_INFO, "DXE IPL Entry\n"));
// Add a call to CpuBreakpoint();  approx. line 468
  CpuBreakpoint();
  Status = TempPtr.DxeIpl->Entry (
                             TempPtr.DxeIpl,
                             &PrivateData.Ps,
                             PrivateData.HobList
 
```

Note:

There may also be issues with transition from 32 to 64 bit so this makes a good place to add a breakpoint


---
@title[Check for transition from DxeIpl to DXE]
<p align="center"><span class="gold" ><b>Check for transition from DxeIpl to DXE</b></span></p>
<span style="font-size:0.8em" >Critical point before calling DXE Core in: </span><br>
@fa[github gp-bullet-gold]<span style="font-size:0.8em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Core/DxeIplPeim">MdeModulePkg/Core/DxeIplPeim/DxeLoad.c </a></span><br>
<span style="font-size:0.7em" >Before entering Dxe Core</span><span style="font-size:0.5em" >&nbsp;&nbsp;(&nbsp;Notice also this is a standalone module - DxeIpl.efi)</span>

```c
EFI_STATUS
EFIAPI
DxeLoadCore (
  IN CONST EFI_DXE_IPL_PPI *This,
  IN EFI_PEI_SERVICES      **PeiServices,
  IN EFI_PEI_HOB_POINTERS  HobList
  )
{ // ...
  // Transfer control to the DXE Core
  // The hand off state is simply a pointer to the HOB list
  //
// Add a call to CpuBreakpoint();  approx. line 790
  CpuBreakpoint();
  HandOffToDxeCore (DxeCoreEntryPoint, HobList);
  //
  // If we get here, then the DXE Core returned.  This is an error
```

Note:
- Check for transition from IPL to DXE

- MdeModulePkg/Core/DxeIplPeim/DxeLoad.c

- Verify address of DXE Core Entry point after IPL from PEI – DxeLoadCore function in DxeIpl->Entry()
- HandOffToDxeCore call (DxeCoreEntryPoint)
<pre>
 // Transfer control to the DXE Core
 // The hand off state is simply a pointer to the HOB list
 //
   CpuBreakpoint() ;
    HandOffToDxeCore (DxeCoreEntryPoint, HobList);
 //
 // If we get here, then the DXE Core returned.  This is an error
</pre>



---?image=/assets/images/slides/Slide55.JPG
@title[Debugging the Boot Phases DXE]
<p align="center"><span class="gold" ><b>Debugging the Boot Phases - DXE</b></span></p>
<br>
<br>
<div class="left-1">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>
<div class="right-1">
<ul style="list-style-type:disc">
 <li><span style="font-size:0.8em" >Search for cyclic dependency check </span></li>
 <li><span style="font-size:0.8em" >Trace ASSERTs caused during DXE execution </span></li>
 <li><span style="font-size:0.8em" >Debug individual DXE drivers </span></li>
 <li><span style="font-size:0.8em" >Check for architectural protocol failure</span></li>
 <li><span style="font-size:0.8em" >Ensure BDS entry call</span></li>
</ul>
</div>


Note:

---
@title[DXE: Trace Each Driver Load]
<p align="center"><span class="gold" ><b>DXE: Trace Each Driver Load</b></span></p>
<br>
<span style="font-size:0.8em" >DXE Dispatcher calls to each driver's entry point in: </span><br>
@fa[github gp-bullet-gold]<span style="font-size:0.8em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Core/Dxe/Image">MdeModulePkg/Core/Dxe/Image/Image.c </a></span><br>
<span style="font-size:0.8em" >Break every time a DXE driver is loaded. </span>

```c
EFI_STATUS
EFIAPI
CoreStartImage (
  IN EFI_HANDLE  ImageHandle,
  OUT UINTN      *ExitDataSize,
  OUT CHAR16     **ExitData  OPTIONAL
  )
{ // ...
    //
    // Call the image's entry point
    //
    Image->Started = TRUE;
// Add a call to CpuBreakpoint();  approx. line 1673
    CpuBreakpoint();
    Image->Status = Image->EntryPoint (ImageHandle, Image->Info.SystemTable);
```

Note:

- MdeModulePkg/Core/Dxe/Image/Image.c
- Image->EntryPoint() call in CoreStartImage
- remember to step "INTO" when it gets to desired module to debug
- Check if control transfers to image entry points
- System breaks here every time a new DXE driver is loaded. Step into this function to trace the driver.

- Image->Started = TRUE;
- CpuBreakpoint() ;
- Image->Status=Image->EntryPoint (ImageHandle, Image->Info.SystemTable);


---?image=/assets/images/slides/Slide58.JPG
@title[Debugging the Boot Phases BDS]
<p align="center"><span class="gold" ><b>Debugging the Boot Phases - BDS</b></span></p>
<br>
<br>
<div class="left-2">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>
<div class="right-2">
<ul style="list-style-type:disc">
 <li><span style="font-size:0.8em" >Detect console devices (input and output) </span></li>
 <li><span style="font-size:0.8em" >Check enumeration of all devices’ preset </span></li>
 <li><span style="font-size:0.8em" >Detect boot policy</span></li>
 <li><span style="font-size:0.8em" >Ensure BIOS BDS “front page” is loaded</span></li>
</ul>
</div>


Note:

---
@title[BDS Phase – Entry Point]
<p align="center"><span class="gold" ><b>BDS Phase – Entry Point</b></span></p>
<br>
<span style="font-size:0.8em" >DXE call to BDS entry point in:</span><br>
@fa[github gp-bullet-gold]<span style="font-size:0.8em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Core/Dxe/DxeMain">MdeModulePkg/Core/Dxe/DxeMain/DxeMain.c </a></span><br>
<span style="font-size:0.8em" >Add `CpuBreakpoint();` to break before BDS. </span>

```c
VOID
EFIAPI
DxeMain (
  IN  VOID *HobStart
  )
{ // ...
  // Transfer control to the BDS Architectural Protocol
  //
// Add a call to CpuBreakpoint();  approx. line 554
  CpuBreakpoint();
  gBds->Entry (gBds);

  //
  // BDS should never return
  //
  ASSERT (FALSE);
  CpuDeadLoop ();
```

Note:
- MdeModulePkg/Core/Dxe/DxeMain/DxeMain.c
- gBds->Entry (gBds); call in DxeMain
- Verify BDS Phase Entry
<pre>
	CpuBreakpoint();
	gBds->Entry (gBds);
	// BDS should never return
	ASSERT (FALSE);
	CpuDeadLoop ();
</pre>


---?image=/assets/images/slides/Slide61.JPG
@title[Debugging the Boot Phases Pre-Boot]
<p align="center"><span class="gold" ><b>Debugging the Boot Phases - Pre-Boot</b></span></p>
<br>
<br>
<div class="left">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>
<div class="right">
<ul style="list-style-type:disc">
 <li><span style="font-size:0.8em" >“C” source debugging</span></li>
 <li><span style="font-size:0.8em" >UEFI Drivers  </span></li>
 <ul style="list-style-type:disc">
   <li><span style="font-size:0.6em" >Init - entry point</span></li>
   <li><span style="font-size:0.6em" >Supported</span></li>
   <li><span style="font-size:0.6em" >Start</span></li>
 </ul>
 <li><span style="font-size:0.8em" >UEFI Shell Applications</span></li>
 <ul style="list-style-type:disc">
   <li><span style="font-size:0.6em" >Entry point</span></li>
   <li><span style="font-size:0.6em" >Local variables</span></li>
 </ul>
 <li><span style="font-size:0.8em" >`CpuBreakpoint();`</span></li>
 </ul>
</div>


Note:



---?image=/assets/images/slides/Slide63.JPG
@title[Debug in Pre-Boot – UEFI Shell]
<p align="right"><span class="gold" ><b>Debug in Pre-Boot – UEFI Shell Application</b></span></p>
<span style="font-size:0.8em" >Add `CpuBreakpoint()` to SampleApp.c near the entry point</span>
<br>
<br>
<div class="left">
<span style="font-size:0.7em" >Add SampleApp.inf to the platform .dsc file</span>
<pre class='bash'>
```
bash$ cd <edk2 workspace directory>
bash$ . edksetup.sh
bash$ build -m SampleApp/SampleApp.inf
```
</pre>
<span style="font-size:0.7em" >Copy the binary SampleApp.efi to USB drive</span><br>
</div>
<div class="right">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>


Note:



---?image=/assets/images/slides/Slide64.JPG
@title[Debug in Pre-Boot – UEFI Shell GDB]
<p align="right"><span class="gold" ><b>Debug in Pre-Boot – UEFI Shell Application</b></span></p>
<span style="font-size:0.8em" >Use UDK Debugger and GDB to debug SampleApp</span>
<br>
<br>
<div class="left">
<span style="font-size:0.7em" >At the shell prompt on the target invoke SampleApp</span>
<pre class='bash'>
```
Shell> Fs0:
FS0:/> SampleApp
```
</pre>

<span style="font-size:0.7em" >GDB will break at the CpuBreakpoint</span><br>
<span style="font-size:0.7em" >Begin debugging SampleApp </span><br>
<pre class='bash'>
```
(udb) layout src
(udb) info locals
(udb) next
```
</pre>
</div>
<div class="right">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>


Note:




---  
@title[Summary]
<BR>
### <p align="center"><span class="gold"   >Summary </span></p><br>
<ul style="list-style-type:none">
 <li>@fa[certificate gp-bullet-green]<span style="font-size:0.9em">&nbsp;&nbsp;Identify the Intel® UEFI Development Kit Debugger<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; host and target basic configuration and components</span> </li>
 <li>@fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Access the debugger tools</span></li>
 <li>@fa[certificate gp-bullet-gold]<span style="font-size:0.9em">&nbsp;&nbsp;Make changes to the target firmware</span> </li>
 <li>@fa[certificate gp-bullet-ltgreen]<span style="font-size:0.9em">&nbsp;&nbsp;Launch the debug application</span></li>
 <li>@fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Use debug commands</span> </li>
 <li>@fa[certificate gp-bullet-magenta]<span style="font-size:0.9em">&nbsp;&nbsp;Debugging PI’s phases</span> </li>
</ul>

---?image=assets/images/gitpitch-audience.jpg
@title[Questions]
<br>
![Questions](/assets/images/questions.JPG) 


---?image=assets/images/gitpitch-audience.jpg
@title[Logo Slide]
<br><br><br>
![Logo Slide](/assets/images/TianocoreLogo.png =10x)


---
@title[Acknowledgements]
#### <p align="center"><span class="gold"   >Acknowledgements</span></p>

```c++
/**
Redistribution and use in source (original document form) and 'compiled' forms (converted
to PDF, epub, HTML and other formats) with or without modification, are permitted provided
that the following conditions are met:

Redistributions of source code (original document form) must retain the above copyright 
notice, this list of conditions and the following disclaimer as the first lines of this 
file unmodified.

Redistributions in compiled form (transformed to other DTDs, converted to PDF, epub, HTML
and other formats) must reproduce the above copyright notice, this list of conditions and 
the following disclaimer in the documentation and/or other materials provided with the 
distribution.

THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR IMPLIED 
WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND 
FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL TIANOCORE PROJECT BE 
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES 
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, 
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, 
WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) 
ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF ADVISED OF THE POSSIBILITY 
OF SUCH DAMAGE.

Copyright (c) 2018, Intel Corporation. All rights reserved.
**/

```


---?image=assets/images/binary-strings-black2.jpg
@title[Using WinDBG Section]
<br><br><br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Debugging using WinDBG</span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>

Note:


---?image=/assets/images/slides/Slide70.JPG
@title[Configure SoftDebugger.ini (Host)]
<p align="center"><span class="gold" ><b>Configure SoftDebugger.ini (Host)</b></span></p>
```php
[Debug Port]
; Channel = Usb
Channel = Serial

;The following settings only apply when Channel=Serial
Port = COM1
FlowControl = 1
BaudRate = 115200

[Target System]

[Debugger]

[Features]
LoadModuleSymbol = 1
TerminalRedirectionPort = 20715

[Maintenance]
Debug=1
```

Note:


---?image=/assets/images/slides/Slide72.JPG
@title[Launch the UDK Debugger Tool]
<br>
<p align="center"><span class="gold" ><b>Launch the UDK Debugger Tool Application</b></span></p>
<br>


Note:
- Start WinDbg with Intel UDK Debugger Tool
- Start up the target system using the UDK based firmware image with the debug feature enabled (within 30 seconds after starting WinDbg)

- Wait two or three seconds, until WinDbg is connected and is ready to accept commands




---?image=/assets/images/slides/Slide74.JPG
@title[Initial Breakpoint for Debugger]
<br>
<p align="center"><span class="gold" ><b>Initial Breakpoint for Debugger</b></span></p>
<br>


Note:

- WinDBG will stop the TARGET in late SEC phase, and load the symbols for SecCore.



---?image=/assets/images/slides/Slide76.JPG
@title[Initial Breakpoint for Debugger]
<br>
<p align="center"><span class="gold" ><b>Initial Breakpoint for Debugger</b></span></p>
<span style="font-size:0.9em"> Code can be viewed after a “Control Break”</span>


Note:



---?image=/assets/images/slides/Slide78.JPG
<!-- .slide: data-transition="none" -->
@title[View Source from Call Stack]
<p align="center"><span class="gold" ><b>View Source from Call Stack</b></span></p>
<br>

<div class="left">
<ul>
 <li><span style="font-size:0.7em" ><u>Alt</u> +6 - to View Call Stack</span> </li>
 <li><span style="font-size:0.7em" >Double click on desired source code</span></li>
 
</ul>
</div>
<div class="right">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>

Note:

+++?image=/assets/images/slides/Slide79.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[View Source from Call Stack]
<p align="center"><span class="gold" ><b>View Source from Call Stack</b></span></p>
<br>

<div class="left">
<ul>
 <li><span style="font-size:0.7em" ><u>Alt</u> +6 - to View Call Stack</span> </li>
 <li><span style="font-size:0.7em" >Double click on desired source code</span></li><br>
 <li><span style="font-size:0.7em" >Double click to open source code for PeiDispatcher</span></li>
</ul>
</div>
<div class="right">
<span style="font-size:0.8em" >&nbsp;  </span>
</div>

Note:


+++?image=/assets/images/slides/Slide81.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[PeiDispatcher.c Opened from Call Stack]
<br>
<p align="center"><span class="gold" ><b>PeiDispatcher.c Opened from Call Stack</b></span></p>
<br>

Note:

- can only set a breakpoint if current IP is within that module check by stepping...


---?image=/assets/images/slides2/Slide57.JPG
<!-- .slide: data-transition="none" -->
@title[Set a Break Point from the Call Stack]
<br>
<p align="center"><span class="gold" ><b>Set a Break Point from the Call Stack</b></span></p>

@snap[north-west span-35]
<br>
<br>
<br>
<br>

<p style="line-height:60%" align="left"><span style="font-size:0.60em; " >
&bull;&nbsp;Click on desired location in the <br>&nbsp;&nbsp;Call Stack<br>
&bull;&nbsp;Select w/ Cntl-C (copy)<br>
&bull;&nbsp;Alt+F9 - Breakpoints menu<br>
&bull;&nbsp;Add "bp" command <br>
&bull;&nbsp;And Cntl-v to (paste) from Call <br>&nbsp;&nbsp;Stack reference <br>
&bull;&nbsp;Click "OK"<br>
</span></p>
@snapend

@snap[north-west span-30 fragment]
<br>
<br>
<br>
<br>
<p style="line-height:60%" align="left"><span style="font-size:0.60em; " >
&nbsp;<br>
&nbsp;<br>
&nbsp;<br>
&nbsp;<br>
&nbsp;<br>
&nbsp;<br><br><br>
&bull;&nbsp;Press "F5" to GO
</span></p>
@snapend

@snap[north-east span-55 fragment]
<br>
<br>
<br>
<br>
<br>
<p style="line-height:30%" align="left"><span style="font-size:0.60em; " >
&nbsp;<br>
&nbsp;<br>
&nbsp;<br>
&nbsp;<br><br><br><br><br><br>
<font color="black">@size[.55em](<b>`0 e fffd2459 [l:\lr\mdemodulekg\core\pei\dispatcher\dispatch `</b>)</font><br>
<br>
</span></p>
@snapend

Note:

1. Click on desired location in the Call Stack
2. Select w/ Cntl-C (copy)
3. Alt+F9 – Breakpoints menu
4. Add “bp” command  and Cntl-v to (paste) from Call Stack reference 
6. Click “OK” 	
7. Press “F5” to Go




---?image=/assets/images/slides/Slide86.JPG
@title[Next “Go” will break in Pei Dispatcher.c]
<br>
<p align="center"><span class="gold" ><b>Next “Go” will break in Pei Dispatcher.c</b></span></p>
<br>


---?image=assets/images/binary-strings-black2.jpg
@title[End Using WinDBG Section]
<br><br><br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;End of WinDBG</span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>

Note:


---?image=assets/images/gitpitch-audience.jpg
@title[Logo Slide]
<br><br><br>
![Logo Slide](/assets/images/TianocoreLogo.png =10x)
