# Introduction
## Devices
1. [PLC](#1): Siemens S7-1200 CPU 1211C DC/DC/DC
2. [RS232/485/422 to TCP/IP converter](#2): ZLAN 5207M
3. [Frequency Converter](#3): Danfoss FC-51
4. Motor: 380V 0.75kW three phase asynchronous motor
5. Others: CAT5 Network Cable *1, Power Supply *1

<h2> Network View </h2>
<div align=center>
    <img src="/../shots/DeviceMap.png" height="500px"/>
</div>

<h2 id="1"> PLC Configuration </h2>

- TIA Portal Version: V18
- External Library: LGF_ScaleLinear
- Add-Ins: Siemens.ExportImportV18.addin

<h2 id="2"> Converter Configuration </h2>

- Convert Protocol: Modbus TCP

<h2 id="3"> Frequency Converter Configuration </h2>

- BUS TER Switch: ON 
><a href="/../shots/FC51 Design Guide.pdf" target="_blank">FC51 Design Guide Page 54</a>

<div style="width:100%; height:350px;border:none;text-align:center">
    <iframe  width="100%" height="800px" src="https://www.google.com/#sbfbu=0&pi="/>
</div>

- Communication parameters (group 8):
    - 8-01 Control Site: 0 or 1
    - 8-04 Control Word Timeout Function: 2
    - 8-30 Protocol: 2
    - 8-31 to 8-33: depend on demand
    - 8-50 to 8-56: depend on demand

# How to use
1. Extract and copy the [Siemens.ExportImportV18.addin](https://support.industry.siemens.com/cs/document/109773999/) into the "AddIns" folder of your TIA Portal installation path. Per default, it is C:\Program Files\Siemens\Automation\Portal V18\AddIns\ .
2. Opening TIA Portal V18.
3. Add a PLC in "Device and network".
4. In "Add-Ins" panel, active the Siemens.ExportImportV18.addin.
5. Right click the program block, select "Export/Import-Import from directory" and choose the .xml-file directory.
6. Reconnect the error output of "LGF_ScaleLinear" block.
7. Refresh and reconnect the FB or FC blocks.