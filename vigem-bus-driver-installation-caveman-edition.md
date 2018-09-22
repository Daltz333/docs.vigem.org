# ViGEm Bus Driver Installation – caveman edition

If the path of the PowerShell failed you; don’t worry, we’ve got your back! 😉

## Preparations

👉 First of all grab the driver files: [ViGEmBus_signed_Win7-10_x86_x64_latest.zip](https://downloads.vigem.org/.stable/latest/windows/x86_64/ViGEmBus_signed_Win7-10_x86_x64_latest.zip)

Attention: This link will change in the near future, come back here if you get the 404 😉

Extract the archive:

![2018-08-15_13-31-18.png](img/2018-08-15_13-31-18.png)

Which will leave you with this folder structure:

![vmware_2018-08-15_12-54-36.png](img/vmware_2018-08-15_12-54-36.png)

Keep that path noted, we'll require it later on.

## The way of the GUI (Windows Device Manager)

The Windows Device Manager is a management tool that's been built into Windows for ages. You can pretty much accomplish almost all device and driver management tasks with it. Depending on your version of Windows [there are multiple ways to open it](https://www.computerhope.com/issues/ch000833.htm); on Windows 10 you can simply right-click on the Windows logo in the taskbar or press the keyboard combination `Win + X`. A menu will po-up where you can fire up Device Manager:

![2018-08-15_13-01-55.png](img/2018-08-15_13-01-55.png)

The task we're seeking after is hidden under the `Action` menu and (a tad the misleading) named `Add legacy hardware`:

![2018-08-15_13-02-13.png](img/2018-08-15_13-02-13.png)

A wizard pops up greeting you with a page you can skip 😊

![vmware_2018-08-15_13-02-39.png](img/vmware_2018-08-15_13-02-39.png)

Choose the radio button `Install the hardware that I manually select from a list (Advanced)`.

Don't worry, it won't get that "advanced", I promise 😜

![2018-08-15_13-03-25.png](img/2018-08-15_13-03-25.png)

Now scroll down and select `System devices`:

![2018-08-15_13-03-38.png](img/2018-08-15_13-03-38.png)

Ignore the Manufacturer and Model entries, hit `Have Disk...` instead:

![2018-08-15_13-03-56.png](img/2018-08-15_13-03-56.png)

Now insert the driver floppy disk. Wait, no 🤨 We don't use floppies anymore, what a shame! Remember where you extracted the driver files previously? Yeah, hit `Browse...`:

![2018-08-15_13-04-11.png](img/2018-08-15_13-04-11.png)

Now instead of digging up your dusty floppy drive navigate to the driver path until you get the `ViGEmBus` entry, select it and hit `Open`:

![2018-08-15_13-04-42.png](img/2018-08-15_13-04-42.png)

Confirm once more with `OK`:

![2018-08-15_13-04-55.png](img/2018-08-15_13-04-55.png)

Now the dialog has changed like presented. You can go to the next screen:

![2018-08-15_13-05-12.png](img/2018-08-15_13-05-12.png)

One last confirmation page and the fun begins, click next:

![vmware_2018-08-15_12-59-16.png](img/vmware_2018-08-15_12-59-16.png)

It's doing something! Exciting! 😃

![vmware_2018-08-15_12-59-41.png](img/vmware_2018-08-15_12-59-41.png)

👮 If you've never installed the driver before, Windows would like you to confirm that you trust the publisher (me). 

You do trust me, right? Right?! 😰

![2018-08-15_13-05-31.png](img/2018-08-15_13-05-31.png)

Oh my! Looks like we did it! 🎉

![vmware_2018-08-15_12-59-54.png](img/vmware_2018-08-15_12-59-54.png)

You should now find a new device named `Virtual Gamepad Emulation Bus` under the `System devices` node:

![2018-08-15_13-06-04.png](img/2018-08-15_13-06-04.png)

That's it! You've done it! Congratulations on your effort to finish this journey 😄 Go have fun playing your 🕹️ now!

## The path of command-line (devcon)

The `devcon` utility is a small console program for common driver tasks created by Microsoft. The tool is unfortunately only "officially" redistributed by the rather huge Windows SDK. I'm hosting a copy you're invited to use so you don't need to install gigabytes of stuff you won't need 😁

👉 [Download devcon](https://downloads.vigem.org/other/microsoft/devcon.zip)

Extract the archive to a location of your choice (e.g. `C:\devcon`) so you'll end up wit the tool here:

![explorer_2018-09-20_17-02-34.png](img/explorer_2018-09-20_17-02-34.png)

[Fire up PowerShell as Administrator](https://www.top-password.com/blog/5-ways-to-run-powershell-as-administrator-in-windows-10/) and execute the following command:

```text
C:\devcon\x64\devcon.exe install "D:\Downloads\ViGEmBus\x64\ViGEmBus.inf" Root\ViGEmBus
```

Make sure the paths used in the example match your system. Execution will then looks similar to this:

![powershell_2018-09-22_15-23-42.png](img/powershell_2018-09-22_15-23-42.png)

And you're done! 🎉

## How do I get rid of this

Bus-Chan is sad to see you go 😿 but here's how to do it.

In Device Manager, expand the `System devices` node and scroll to the `Virtual Gamepad Emulation Bus` entry.

Right-click on it and select `Uninstall device`:

![2018-08-15_14-25-07.png](img/2018-08-15_14-25-07.png)

Make sure to tick the box to also remove the driver files:

![2018-08-15_14-25-39.png](img/2018-08-15_14-25-39.png)

That's it! A reboot might be required for the removal to complete.
