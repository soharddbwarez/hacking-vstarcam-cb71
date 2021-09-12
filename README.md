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

If you want to see what the output is like, open up the textfile that I've added to this repository above named "Cam_UART_Dump.txt"

There's more...
I downloaded the Android app "Eye4.apk" to my computer and then decompiled it to have a look inside so I get a better understanding how it works.
Because it's a large file of about 98MB and about 326MB when it's decompiled it's too big to upload and save it here on GitHub so I've uploaded it to my Google Drive to make it publicly available to you.
I don't know if that's useful but I wanted to have everything accessable and available from one place here on GitHub so that's what we have to deal with so if you're interested and want to take at the code you can go to my Google Drive directory called "VSTARCAM", linked here: https://drive.google.com/drive/folders/1YqskHwKtslQNzrmdpGdovLcgfkWcBXjV?usp=sharing

With all the info I've gathered I'm going to try to get access to the camera so I can start using it with my own or third-party software and app, however I'm kind of stuck at this point and I can use some help to go forward so feel free to share and add the information that I don't know or have at the moment.

  - That could be an Arduino sketch to be able to dump the SPI flash memory into a file so it can be extracted, changed or whatever necessary to make it work.

  - If you know of any software that I can use to extract the .bin file in Windows, then work on it and repack it into a .bin file to be uploaded to the camera that would be very     helpful if you can share that with me.

Any input would be appreciated right now to be honest so that's it for now.
