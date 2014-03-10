py-fritz-monitor
================

Python class to read the provided data by fritzbox call monitor on port 1012

How I use it
================
I created the class to detect incoming and outgoing calls for my home automation system. If any audio playback is running, it is automatically paused, if there are incoming or outgoing calls. After ending a call the music continues. You can find a lot of articles about it on my blog http://www.blog.smartnoob.de/ (german only).

Troubleshooting
================
If you run py-fritz-monitor the first time, you might have to enable the call monitor on your fritzbox first. To enable it, use any (DECT) phone connected with your fritzbox and type:
♯96*5*
Complete with the green call button

Dont't worry, you can it disable the call monitor at any time you want. Just type:
♯96*4*
Complete again with the green call button

If your fritzbox's hostname is different from fritz.box you can define it when you initialize a new instance of callmonitor class. Normally you use
call = callmonitor()
the class also accepts the two optional parameters hostname and port:
call = callmonitor(hostname[str], port[int])

Examples
================
In the example.py file, there are some examples at the end. You might use them to make a dry try with your own application if you don't want to call yourself again and again. By adding some sleep() commands you could simulate a real call. Anyway, you should remove or uncomment these lines in productive use.
The examples still work when you are connected to your fritzbox so it is required to remove these lines!

Callbacks
================
The class also provides a callback function. Please note that only one callback can be enabled at the same time. It is not possible to call multiple functions using the integrated callback handler. By default the callback handler is disabled. You can enable it with:
call.register_callback ("my_cb")
Replace my_cb with your function name. To disable the callback, you use
call.register_callback (-1)

Currently it is not possible to call functions of class instances. If you found some modifications which work with both, please inform me via GitHub

Example code
================
The file call-monitor.py contains the required class. The file example.py contains an example for the usage. Please try it first, before you make your own modifications.

The last things ...
================
Congratulation! You read nearly the complete readme file. Thank you ;)

If you find bugs (some bad home animals), please inform me via GitHub. You can find my repo here: https://github.com/HcDevel/py-fritz-monitor
