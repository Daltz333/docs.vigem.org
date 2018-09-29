# x360ce to ViGEm

VDX is a ViGEm Feeder Application designed to create a System-Wide XBox360 or DualShock 4 joystick

## Target Audience
- Users running a `modern` OS.  Windows 8.1 or Windows 10 😉

## Prequisites
- Setup [ViGEm Bus Driver](https://docs.vigem.org/#!vigem-bus-driver-installation.md) if you haven't already
- Download and Install [Microsoft Visual C++ Redistributable for Visual Studio 2017](https://visualstudio.microsoft.com/de/downloads/)
- Download and Install [Microsoft Visual C++ Redistributable for Visual Studio 2013](http://www.microsoft.com/en-us/download/details.aspx?id=40784)
- [DirectX End-User Runtime(June 2010)](http://www.microsoft.com/en-us/download/details.aspx?id=8109)

## Download VDX and x360ce

- Download the latest VDX application from [here](https://buildbot.vigem.org/builds/VDX/master/)
- Download the latest x360ce x64 from [here](https://www.x360ce.com/)

## How to use

It's not that hard. I swear! 😃

### Gather the files
- Extract x360ce to it's own folder. EX: `Downloads\x360ce`
- Put the VDX executable in the same folder as x360ce
![2018-09-29_16-41-39.png](img/2018-09-29_16-41-39.png)

### Configuring x360ce
- Open the x360ce_x64 application and create the DLL that it prompts you to. 
![x360ce_x64_2018-09-29_16-44-21.png](img/x360ce_x64_2018-09-29_16-44-21.png)

- You will be prompted to search the internet for default settings. Press next and finish through the dialog.
![x360ce_x64_2018-09-29_16-49-17.png](img/x360ce_x64_2018-09-29_16-49-17.png)
![x360ce_x64_2018-09-29_16-49-33.png](img/x360ce_x64_2018-09-29_16-49-33.png)

- Configure your joystick controls.
![x360ce_x64_2018-09-29_16-54-11.png](img/x360ce_x64_2018-09-29_16-54-11.png)

- In some cases where VDX does not detect your controller, you may need to press the `auto` button in the bottom right of the application before you modify the controls.
- Save and close out of x360ce

### Enabling VDX
- Open VDX and press connect
![VDX_2018-09-29_16-57-57.png](img/VDX_2018-09-29_16-57-57.png)

## Troubleshooting
`[Pad0] Misconfigured Device, check GUIDs`
- Delete x360ce.ini and xinput1_3.dll from the application directory and relaunch x360ce
