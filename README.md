# FORENSIC_COMMANDS


### Tools used for solving Forensics challenges

### Image File

* Try `file` command to learn more information about the image file.
* Extract data inside Image files using:
```
> $ zsteg <FILE_NAME>
```
* Check for metadata of the Image files using:
```
> $ exiftool <FILE_NAME>
```
* Search for particular string or flag in an Image file:
```
> $ strings <FILE_NAME> | grep flag{
```
* Extract data hidden inside an image file protected with password:
```
> $ steghide extract -sf <FILE_NAME>
```
* Verify the integrity of PNG and dump all of the chunk-level information in human-readable form:
```
> $ pngcheck -cvt <FILE_NAME>.png
```
### Binwalk

* Find data inside the image or extract interesting data if binwalk reports it as a zip Archive:
```
> $ binwalk <IMAGE_NAME>
```
### File Carving

* Process used in computer forensics to extract data from a disk drive or other storage device without the assistance of the file system that originally created the file:
	+ `dd` command: Copy a file, converting and formatting according to the operands.
	+ `foremost` command: Try file carving using `foremost <filename>` command. Foremost supports all files, but it takes time to extract all files when dealing with big-sized files.
	+ `HXD` command: User-friendly hex editor that allows you to perform low-level editing and modifying of a raw disk or main memory (RAM)

### Network Analysis

* Analyze pcap or pcapng files using:
```
> $ wireshark <FILE_NAME>.pcapng
```
* NetworkMiner: Network Forensic Analysis Tool used as a passive network sniffer/packet capturing tool in order to detect operating systems, sessions, hostnames, open ports
	+ Aircrack-NG Tool: Crack 802.11 WEP and WPA-PSK keys
		- Install using `apt-get install aircrack-ng`

### USB

* USBRip: Simple CLI forensics tool for tracking USB device artifacts (history of USB events) on GNU/Linux

### Registry Viewers

* OfflineRegistry View: Simple tool for Windows that allows you to read offline Registry files from external drive and view the desired Registry key in .reg file format.
	+ Registry Viewer: Used to view Windows registries.

### Extract NTFS Filesystem

* Extract NTFS file system on Windows using 7Zip
* Extract NTFS file system on Linux:
```
> $ sudo mount -o loop <FILENAME.ntfs> mnt
```
### Recover Files from Deleted File Systems

* Recover Files from Deleted File Systems from Remote Hosts:
	+ `dcfldd` command: Recover files from deleted file systems
	+ `gunzip` command: Decompress extracted files
	+ `binwalk` command: Find interesting data inside the extracted files

### Memory Forensics

* Investigate memory dump using:
	+ Volatility: Extraction of digital artifacts from volatile memory (RAM) samples
	+ WindowsSCOPE: Enables memory forensics for Windows computers

### Audio Forensics

* Extract Data from Audio File using Audacity: checking integrity, improving speech clarity, transcribing dialogue

### Zip Password Cracking

* Extract ZIP password using:
	+ `fcrackzip` command
	+ `zip2john` command:
```bash
> $ zip2john <File-Name>.zip > <Name>.txt
> $ john <Name>.txt --wordlist=/usr/share/wordlists/rockyou.txt
```

### Rar Password Cracking

* Extract Rar password using:
	+ `rar2john` command
	+ `john` command:
```bash
> $ rar2john <File-Name>.rar > <Name>.txt
> $ john <Name>.txt --wordlist=/usr/share/wordlists/rockyou.txt
```

### Pdf Password Cracking

* Extract Pdf password using:
	+ `pdf2john` command
	+ `john` command:
```bash
> $ pdf2john <File-Name>.pdf > <Name>.txt
> $ john <Name>.txt --wordlist=/usr/share/wordlists/rockyou.txt
```

### 7z Password Cracking

* Extract 7z password using:
	+ `7z2john` command
	+ `john` command:
```bash
> $ 7z2john <File-Name>.7z > <Name>.7z
> $ john id_rsa.txt --wordlist=/usr/share/wordlists/rockyou.txt
```

### SSH Password Cracking

* Crack encrypted ssh key using `ssh2john` tool:
```bash
> $ ssh2john id_rsa > id_rsa.txt
> $ john id_rsa.txt --wordlist=/usr/share/wordlists/rockyou.txt
> $ ssh -i id_rsa <Username>@<IP-Address>
   :Enter the Password Cracked 
```


### Disk Image Analysis

* Mount disk images to examine contents:
```bash
> $ sudo mount -o loop <DISK_IMAGE> /mnt
```

* Analyze disk images using Autopsy, a graphical forensic tool:
```bash
> $ autopsy
```

* Use `sleuthkit` to analyze file systems:
```bash
> $ fls -r <DISK_IMAGE>
> $ icat <DISK_IMAGE> <INODE>
```

### Log File Analysis

* Analyze Windows event logs:
```bash
> $ log2timeline.py <OUTPUT_FILE> <SOURCE>
> $ psort.py -o l2tcsv <OUTPUT_FILE>
```

* Check Linux log files:
```bash
> $ cat /var/log/auth.log
> $ cat /var/log/syslog
```

### PDF Analysis

* Extract embedded files from a PDF:
```bash
> $ pdfdetach -saveall <PDF_FILE>
```

* Analyze PDF structure and content:
```bash
> $ pdfid.py <PDF_FILE>
> $ pdf-parser.py <PDF_FILE>
```

### Steganography

* Analyze and extract hidden data in audio files:
```bash
> $ steghide extract -sf <AUDIO_FILE>
> $ stegsnow <INPUT_FILE>
```

* Use `stegsolve` to analyze image files:
```bash
> $ java -jar stegsolve.jar
```

### File System Analysis

* Examine EXT file systems:
```bash
> $ extundelete <DISK_IMAGE> --restore-all
```

* Check for deleted files on NTFS file systems:
```bash
> $ ntfsundelete <DISK_IMAGE>
```

### Hex Editors

* Use `xxd` to create a hex dump:
```bash
> $ xxd <FILE_NAME>
```

* Edit binary files with `bless`, a GUI hex editor:
```bash
> $ bless <FILE_NAME>
```

### Memory Forensics

* Analyze Windows memory dumps:
```bash
> $ volatility -f <MEMORY_DUMP> --profile=<PROFILE> pslist
> $ volatility -f <MEMORY_DUMP> --profile=<PROFILE> memdump -D <OUTPUT_DIR>
```

### Network Traffic Analysis

* Extract files from PCAP files:
```bash
> $ tcpflow -r <PCAP_FILE>
> $ tcpextract -d <PCAP_FILE>
```

* Analyze HTTP traffic:
```bash
> $ tshark -r <PCAP_FILE> -Y 'http.request'
```

### Browser Forensics

* Analyze browser artifacts using `browser_history`:
```bash
> $ browser-history -b chrome history
```

### Email Analysis

* Analyze email files (PST, OST):
```bash
> $ readpst -r -o <OUTPUT_DIR> <EMAIL_FILE>
```

### Document Analysis

* Extract metadata from Office documents:
```bash
> $ oletools
> $ olevba <DOC_FILE>
```

### Miscellaneous

* Recover deleted files using `testdisk`:
```bash
> $ testdisk <DISK_IMAGE>
```

* Analyze SQLite databases:
```bash
> $ sqlitebrowser <DB_FILE>
```

These commands cover a broad range of tools and techniques used in forensic analysis for CTF challenges.
```

Feel free to copy this content into your README.md file for your project!
