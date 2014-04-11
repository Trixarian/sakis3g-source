Compiling
---------

Required dependencies: libusb-dev, ppp

Now clone the repo branch using git:  
`git clone https://github.com/Trixarian/sakis3g-source.git -b pre-libusb-1.x`

Then change to directory when the repo has downloaded:  
`cd sakis3g-source`

Then compile Sakis3G:  
`./compile`

Use the following to create the embedded version (complete, but lacks usb_modeswitch & it's sources):  
`./compile embedded`

And the stripped version (smallest & like embedded, but strips docs, man pages & recompile tools):  
`./compile stripped`

Finally copy the compiled file to your bin folder:  
`sudo cp build/sakis3gz /usr/bin/sakis3g`


Running
-------

Once installed you can run the program simply by typing `sakis3g` from the terminal.
See `sakis3g help` and `sakis3g man` for a complete list of commands.

Use the sakis3g.conf in the files directory as a basis to automated your 3G connection. This will allow the use of the `sakis3g connect` command to connect. Just `sudo cp files/sakis3g.conf /etc` when you're done configuring it.

When using the interactive terminal gui on rootless systems (like Ubuntu), you may need to run it with `sudo sakis3g` before it will connect. Another thing to note is that modem-manager from NetworkManager may lock the interface of the device, which will make sakis3g fail to connect. Either kill modem-manager or remove and plug the device back in before trying again.

Couple of things to note:
* If the system has usb-modeswitch installed, sakis3g will prefer it over it's internal one.
* If the system has wvdial installed, sakis3g will prefer it over ppp.  

The full readme can be found in README.
