# hacking-vstarcam-cb71
I purchased one of the VSTARCAM IP Cameras, the CB71 and the only way to get this camera configured is via the Android App that doesn't work on my Galaxy S5 phone so I'm trying to hack into the camera so I can use it.

What I found out so far is the UART port and I think I found the SPI port too which is right next to the UART port.
I've included a picture in this repository to show you the exact pinout of both ports on the PCB with a description below the picture.
What I can tell is the UART port is 3.3 volt and the SPI port is 1.8 volt so you definitely need to have a bi-directional level shifter in between
the camera and in my case the Arduino Nano which has a 5 volt logic and I would destroy both chips on the camera immediately without the level shifter
so be careful what you connect to where if you are following along with me.

So with the camera connected to the bi-directional level shifter and from there to my Arduino Nano RX and TX pins and the code that I also provided
in this repository.
The only thing what the code does is to configure PIN0 and PIN1 to be high impedance so the Arduino chip doesn't interfere with the RX and TX pins
so you can use the USB to TTL chip independently, if you don't get any output on the Putty terminal you need to switch the RX and TX and try again.

If you're on Windows you can use Putty to see the UART output on the terminal, just select the serial connection and enter the COM port, in my case it's COM4
and enter the connection speed which is 115200 kbps.
