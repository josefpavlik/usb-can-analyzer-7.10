# usb-can-analyzer-7.10
Simple command line utility for USB-CAN Analyzer (V7.10)
![](doc/analyzer.png)

There are 2 utilities - *canmonitor* and *cansend*<br>
*Canmonitor* reads the can and prints on stdout timestamp and content of received packet.<br>
*Cansend* sends the packet on the bus

<pre>
Usage:
canmonitor &lt;serial port&gt; &lt;CAN speed&gt; [extframe=0] [filter (hex) =00000000] [mask (hex) =00000000] [mode=0] [send_once=0]
Example: canmonitor /dev/ttyUSB0 500000

example of output:
15:11:04.066: 0041: ff 7f 41 00 98 10 00 00
15:11:06.629: 00c1: 12 34 56
15:11:07.909: 00c1: 09 02 01 01 ff
15:11:08.358: 00c1: 04 09 01 15 ff
15:11:09.067: 0041: ff 7f 41 00 98 10 00 00

cansend &lt;serial port&gt; &lt;frametype&gt; &lt;addr (hex)&gt; [up to 8 hex data bytes]
frametype is one of:
  0: standard frame
  1: remote frame
  2: extended frame
  3: extended remote frame
Example: cansend /dev/ttyUSB0 0 0041 12 34 56 78
</pre>
