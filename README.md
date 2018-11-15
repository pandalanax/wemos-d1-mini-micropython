# wemos-d1-mini-micropython

# Introduction
A quick tutorial on how to work with micropython as i found it puzzling in the beginning.<br>

# Useful things to know
  * Unix version comes with a builtin package manager called upip, e.g.: <br>
  `$ ./micropython -m upip install micropython-pystone`<br>
  find it [here](https://github.com/micropython/micropython/ "Micropython Github")
  
  * Put or get files to the board via ampy, e.g.: <br>
  `ampy --port /dev/ttyUSB0 get file.py`<br>
  `ampy --port /dev/ttyUSB0 put file.py`<br>
  Note that this will overwrite any files with the same name without warning.
  
  * There is a VScode extension [here](https://github.com/dphans/micropython-ide-vscode "Micropython VSCode") <br>
  However, i have an alias in my .bashrc: <br>
  `alias putboot="ampy --port /dev/ttyUSB0 put boot.py;picocom /dev/ttyUSB0 -b115200"`<br>
   `alias putmain="ampy --port /dev/ttyUSB0 put main.py;picocom /dev/ttyUSB0 -b115200"` <br>
   I send over the file via putboot or putmain and then it opens a repl so i can see the output.
  
# How to:
* boot.py <br>
 Code written in boot.py is executed once, its the equivalent to the setup() method in Arduino IDE.
* main.py <br>
 Once boot.py completes the ESP8266 executes the main.py, make sure to put a `while True:` loop to get the equivalent to the loop() method in Arduino IDE.
 * Other files: <br>
 If you developed a python package on your own and your main.py needs it you simply use ampy (see above) to put it on the board.

# Examples:
Coming soon

