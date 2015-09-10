Below are instructions to format an SD card for DragonBOard 410c. This tool is for experimental purpose only:

1) ptool.py -x partition.xml -g 1
    After this command, you will have rawprogram0.xml, patch0.xml, gpt_both0.bin ...etc.
	partition.xml will have the entries for all files used for Android distribution, gpt_both0.bin is the file that needs to be flashed to emmc.	
	For Android gpt_both.bin could be flashed to emmc via fastboot:
	fastboot flash partition gpt_both0.bin

2) msp.py
\\.\PHYSICALDRIVE0   149.05 GB  sectors:312576705 <--- Not likely an SD card, careful!
\\.\PHYSICALDRIVE1   14.83 GB   sectors:31101840 This is probably your SD card device
*At this phase, you should find external SD card.

5-4. msp.py -r rawprogram0.xml -p patch0.xml -d \\.\PHYSICALDRIVE1
* Be careful about the device name. If you type PC drive as device name, Hard disk of PC will be damaged           

