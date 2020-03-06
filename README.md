# Serial Sequence Executer

Testing is life - A small tool to execute a sequence of serial commands in a loop and capture a log

![Image of it](https://github.com/MrMuhs/SerialSequenceExecuter/blob/master/pictureofit.png)

## Getting Started

So you need an AutoIt v3 installation to compile and run the script, you can get it at: [AutoIt](http://www.autoitscript.com) 
The DLL for the serial communication just works with 32bit - so just compile the script for 32bit

## Nutshell usage

* open a serial connection
* write a command sequence in the textbox, line by line
* click execute

The serial log is capured in the file with timestamp as mentioned below.

## "Advanced" usage

For convinience, you can load/store the commands in a textfile.
There are certain "special" commands to define more complex sequences or just to utilize the log:
```
## do the magic here
```
Defines a comment in the sequence " do the magic here", which is ignored for the execution
```
#exit
```
Will just stop executing the sequence
```#sleep#~#123
```
Will sleep for 123ms until going for the next command
```
#waitfor#~#xyz
```
Will capture serial and sleep until "xyz" is found in the serial log, before going for the next command
```
#writemarker#~#Test 123
```
Will write a marker line to the logfile containing the text "Test 123"
```
#startnewlog
```
Will start writing to a new logfile with timestamp
```
#startnewlog#~#logFileForXYZ
```
Will start writing to a new logfile with timestamp AND the given text "logFileForXYZ"

## Build with

For the serial port bindings the external project is used made by "Martin Gibson" (and contributers) - thanks for sharing.
So the CommMG.au3 and commg.dll within the repo are imported from the forum thread:
https://www.autoitscript.com/forum/topic/128546-serial-port-com-port-udf/
The used version here is 2.83, which maybe outdated.
Anyway, the copyright/licence of the authors remain how ever they are - i couldnt find information about it anywhere.