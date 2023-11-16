# icanhaspii-CTF CheatSheet
## These are my CTF Hacks!  I hope you enjoy!
<details markdown>
  <br>
  <summary>[Linux Analysis Commands - file]</summary>
Run this to determine what type of file you are dealing with:<br><br>
<img src="images/File_Screenshot 2023-10-03 203208.png"><br><br>
</details>

<details markdown>
  <br>
  <summary>[Linux Analysis Commands - binwalk]</summary>
Run this to view a summary of the file contents:<br><br>
<img src="images/BinWalk_Screenshot 2023-10-03 203227.png"><br><br>
</details>

<details markdown>
  <br>
  <summary>[Linux Analysis Commands - strings]</summary>
Run this to get the list of printable characters from files.  You can even run strings on a Pcap!  Or, say for example, that you have something you think contains a flag and you know that flag is in the typical CTF format of flag{some_bonus}, you can run the following to cut down on the amount of data you have to parse through. The following will only yield lines of 8 characters or more:<br><br>
<img src="images/Strings_Screenshot 2023-05-12 172558.jpg"><br><br>
You can also combine strings and grep:<br><br>
<img src="images/Strings_Screenshot 2023-05-12 174704.jpg">
</details>

<details markdown>
  <br>
  <summary>[Linux Analysis Commands - java -jar]</summary>
The java -jar command will open a .jar file:<br><br>
<img src="images\Java_JarStegSolveHowTo.png"><br><br>
</details>

<details markdown>
  <br>
  <summary>[Linux Analysis Commands - java]</summary>
The java command will open a .java file:<br><br>
<img src="images/Java_Screenshot 2022-06-15 085349_Edited.png"><br><br>
</details>

<details markdown>
  <br>
  <summary>[Linux Analysis Commands - base64]</summary>
The base64 decode command will decode a b64 string.  There’s more than one way to invoke the base64 decode command, here are few:<br><br>
1. Grab a base64 encoded string such as: Umlja19SMGxsM2Q=<br><br>
2. Type the following into your Linux command prompt to echo/print to screen:<br><br>
echo 'Umlja19SMGxsM2Q=' | base64 -d<br><br>
3. Hit ENTER<br><br>
<img src="images/Base64_Screenshot 2023-11-08 172521.png"><br><br>
4. If you’re feeling really fancy, and you are playing a CTF, you can run the following to echo/print your decoded b64 in standard flag format to your screen:<br><br>
echo "flag{$(echo 'Umlja19SMGxsM2Q=' | base64 -d)}"<br><br>
<img src="images/Base64_Screenshot 2023-11-08 180945.png"><br><br>
-Here’s another way:<br><br>
1. Grab a base64 encoded string such as: Umlja19SMGxsM2Q=<br><br>
2. Type the following into your Linux command prompt:<br><br>
Base64 –d<br><br>
3. Hit ENTER<br><br>
<img src="images/Base64_Screenshot 2023-11-08 173111.png"><br><br>
4. At the prompt, paste in your base64 encoded string:<br><br>
<img src="images/Base64_Screenshot 2023-11-08 173249.png"><br><br>
5. Hit ENTER again:<br><br>
<img src="images/Base64_Screenshot 2023-11-08 173640.png"><br><br>
6. Finally, hit Control-D on your keyboard:<br><br>
<img src="images/Base64_Screenshot 2023-11-08 172847.png"><br><br>
-And yet another method:<br><br>
1. Save your base64 encoded string into a text editor:<br><br>
<img src="images/Base64_Screenshot 2023-11-08 174625.png"><br><br>
2. Type the following into your Linux command prompt to echo/print to screen:<br><br>
base64 -d dns.txt >decoded.txt<br><br>
<img src="images/Base64_Screenshot 2023-11-08 174546.png"><br><br>
3. Open your new file, “decoded.txt”:<br><br>
<img src="images/Base64_Screenshot 2023-11-08 174720.png"><br><br>
If you run across encoding similar to below:<br><br>
IO.Compression.DeflateStream([IO.MemoryStream][Convert]::FromBase64String<br><br>
[IO.Compression.CompressionMode]::Decompress<br><br>
You can try the following “Recipe” in CyberChef to decode:<br><br>
(a)From_Base64('A-Za-z0-9%2B/%3D',true,false)<br><br>
(b) Raw_Inflate(0,0,%5B'Adaptive','Block'%5D,false,false)<br><br>
</details>

<details markdown>
  <br>
  <summary>[Linux Analysis Commands - ifconfig]</summary>
To find your ip address and network configuration, you can use the old ifconfig command (considered depreciated), or the newer ip address command.  It works with any of the following, and of course more in depth combined with switches:<br><br>
<img src="images/ip_Screenshot 2023-11-09 105007.png"><br><br>
<img src="images/ip_Screenshot 2023-11-09 104951.png"><br><br>
<img src="images/ip_Screenshot 2023-11-09 104928.png"><br><br>
</details>

<details markdown>
  <br>
  <summary>[Linux Analysis Commands - realpath]</summary>
realpath converts each filename argument to an absolute pathname, which has no components that are symbolic links or the special . or .. directory entries. Each path component in the filename must exist, otherwise realpath will fail and non-zero exit status will be returned.<br><br>
href="https://www.google.com/url?q=https://linux.die.net/man/1/realpath&amp;sa=D&amp;source=editors&amp;ust=1699590511374365&amp;usg=AOvVaw1FkT0L7tNSOCrQIqhPv2FA">https://linux.die.net/man/1/realpath</a><br><br>
</details>

<details markdown>
  <br>
  <summary>[Linux Analysis Commands - SSH]</summary>
To find your ip address and network configuration, you can use the old ifconfig command (considered depreciated), or the newer ip address command.  It works with any of the following, and of course more in depth combined with switches:<br><br>
https://www.lrz.de/services/compute/courses/x_lecturenotes/191007_OpenSSH_Tutorial_2019.pdf<br><br>
https://opensource.com/article/20/9/ssh<br><br>
<img src="images/image181.jpg"><br><br>
</details>

<details markdown>
  <br>
  <summary>[Linux Analysis Commands - chmod]</summary>
chmod +x<br><br>
Note: chmod +x (plus x) stands for execute.<br><br>
Question:<br><br>
I want to write the Ubuntu analogue of a "batch file" (a shell script). But I don't know how to use chmod +x filename command to make it so that the script can be run. Nor do I know where to use it.<br><br>
Answer:<br><br>
chmod +x on a file (your script) only means, that you'll make it executable. Right click on your script and chose Properties -> Permissions -> Allow executing file as program, leaves you with the exact same result as the command in terminal.<br><br>
If a file you want to change permissions on is located within the systems directory you may need to be root, like so: (be careful, while using sudo command)<br><br>
sudo chmod +x /usr/share/testfolder/aFile<br><br>
https://askubuntu.com/questions/443789/what-does-chmod-x-filename-do-and-how-do-i-use-it<br><br>
Question:<br><br>
What is the difference between chmod u+x and just chmod +x? I have seen a ton of tutorials that say to use u+x to make scripts executable. However, omitting the u doesn't seem to have any effect.<br><br>
Answer:<br><br>
The man page of chmod covers that.<br><br>
u stands for user.<br><br>
g stands for group.<br><br>
o stands for others.<br><br>
a stands for all.<br><br>
That means that chmod u+x somefile will grant only the owner of that file execution permissions whereas chmod +x somefile is the same as chmod a+x somefile.<br>
<a href="https://askubuntu.com/questions/29589/chmod-ux-versus-chmod-x" target="_blank">https://askubuntu.com/questions/29589/chmod-ux-versus-chmod-x</a><br><br>
</details>

<details markdown>
  <br>
  <summary>[Linux Analysis Commands - chown]</summary>
To give a file permissions so that a regular user can move it or edit it, you can run the following:<br><br>
# chown kali NTUSER.DAT.dat<br><br>
</details>

<details markdown>
  <br>
  <summary>[Linux Analysis Commands - Bash]</summary>
Bash (Bourne-Again SHell) is one of the most commonly used Unix/Linux shells and is the default shell in many Linux distributions.<br><br>
<a href="https://www.freecodecamp.org/news/bash-scripting-tutorial-linux-shell-script-and-command-line-for-beginners" target="_blank">https://www.freecodecamp.org/news/bash-scripting-tutorial-linux-shell-script-and-command-line-for-beginners</a><br><br>
Some of the main delimiters (terminators or redirectors) for Bash commands are as follows:<br>
whoami; whoami<br>
whoami|<br>
> (output to)<br>
|| (double pipe)<br>
</details>

<details markdown>
  <br>
  <summary>[Linux Analysis Commands - grep]</summary>
Some common grep options:<br><br>
<img src="images/image165.png"><br><br>
<img src="images/Screenshot 2023-11-15 203316.png"><br><br>
grep example: cat cowrie.log.wwhf2020_lab2 | grep CMD<br><br>
<img src="images/image163.jpg"><br><br>
<img src="images/image155.jpg"><br><br>
Count w/ grep:<br><br>
<img src="images/image154.png"><br><br>
<img src="images/image158.png"><br><br>
</details>

<details markdown>
  <br>
  <summary>[Linux Analysis Commands - curl]</summary>
Curl is useful in transferring data without user interaction.<br><br>
curl http://nidus-setup:8080<br><br>
curl -X POST http://nidus-setup:8080/api/cooler -H "Content-Type: application/json" --data-binary '{"temperature":1000}'<br><br>
<img src="images/image157.png"><br><br>
</details>


<details markdown>
  <br>
  <summary>[Pcap Analysis - strings]</summary>
You can run strings on a Pcap! Below are a couple examples (I like to pipe my results to a .txt file for easier review):<br><br>
<img src="images/StringsPcap_Screenshot 2023-11-09 184958.png"><br><br>
</details>

<details markdown>
  <br>
  <summary>[Pcap Analysis - TShark]</summary>
<a href="https://osqa-ask.wireshark.org/questions/38071/how-to-extract-ip-addresses-from-cap-file-to-text-file" target="_blank">You can extract ip addresses from a Pcap using Tshark</a><br><br>
To extract just the destination ip, type the following command:<br><br>
<img src="images/TShark_Screenshot 2023-03-16 211016.jpg"><br><br>
To extract both the destination ip and the source ip, type the following command:<br><br>
<img src="images/TShark_Screenshot 2023-03-16 211435.jpg"><br><br>
</details>

<details markdown>
  <br>
  <summary>[Pcap Analysis - Zeek]</summary>
Zeek installs itself here:<br><br>
<img src="images/Zeek_Screenshot 2023-03-24 201006_Edited.jpg"><br><br>
To export logs from a Pcap into Zeek format, type the following syntax (r is for read):<br><br>
<img src="images/Zeek_Screenshot 2023-03-24 201006.jpg"><br><br>
</details>

<details markdown>
  <br>
  <summary>[Pcap Analysis - RITA]</summary>
RITA (Real Intelligence Threat Analytics):<br><br>
<a href="https://www.activecountermeasures.com/free-tools/rita" target="_blank">RITA is named in honor of John Strand’s mother who is no longer with us but will always be remembered in this loving way</a><br><br>
<a href="https://www.youtube.com/watch?v=QcQmG5KTLpo&ab_channel=ActiveCountermeasures" target="_blank">Chris Brenton has a fantastic install video</a><br><br>
To import logs from Zeek format into RITA, navigate via command line to the folder where your exported Pcap logs are:<br><br>
<img src="images/image62.jpg"><br><br>
Next, type the following syntax (LogsOily was the name of my pcap, so I called the output folder for RITA the same name):<br><br>
<img src="images/image64.png"><br><br>
RITA will tell you when it’s done:<br><br>
<img src="images/image66.jpg"><br><br>
</details>

<details markdown>
  <br>
  <summary>[Pcap Analysis - TCPflow]</summary>
TCPflow is a command-line tool for processing streams.<br>
<a href="https://linux.die.net/man/1/tcpflow" target="_blank">https://linux.die.net/man/1/tcpflow</a><br>
<a href="https://www.geeksforgeeks.org/tcp-flow-analyze-and-debug-network-traffic-in-linux/#" target="_blank">https://www.geeksforgeeks.org/tcp-flow-analyze-and-debug-network-traffic-in-linux/#</a><br>
<a href="https://simson.net/ref/2013/2013-12-05_tcpflow-and-BE-update.pdf" target="_blank">https://simson.net/ref/2013/2013-12-05_tcpflow-and-BE-update.pdf</a><br><br>
<img src="images/image183.png"><br><br>
<img src="images/image209.png"><br><br>
</details>

<details markdown>
  <br>
  <summary>[Audio - Decoders/Analyzers]</summary>
Note from Dcode regarding T9 vs Multitap Confusion:<br>
Multitap ABC should not be confused with T9 predictive text. For example,'DCODE' is written '3222666333' in Multitap and '32633' in T9.<br>
<a href="https://twitter.com/_johnhammond/status/1244277165316857857?lang=en" target="_blank">https://twitter.com/_johnhammond/status/1244277165316857857?lang=en</a><br><br>
<img src="images/image207.png"><br><br>
<a href="https://www.audacityteam.org/download" target="_blank">https://www.audacityteam.org/download</a><br>
<a href="https://www.sonicvisualiser.org/download.html" target="_blank">https://www.sonicvisualiser.org/download.html</a><br>
<a href="http://dialabc.com/sound/detect/index.html" target="_blank">http://dialabc.com/sound/detect/index.html</a><br>
<a href="http://www.polar-electric.com/DTMF/Index.html" target="_blank">http://www.polar-electric.com/DTMF/Index.html"</a><br>
<a href="https://forums.radioreference.com/threads/twotonedetect-beta.120010" target="_blank">https://forums.radioreference.com/threads/twotonedetect-beta.120010</a><br>
<a href="https://onlinetonegenerator.com/dtmf.html" target="_blank">https://onlinetonegenerator.com/dtmf.html</a><br>
<a href="https://www.venea.net/web/dtmf_generator" target="_blank">https://www.venea.net/web/dtmf_generator</a><br>
<a href="https://github.com/ribt/dtmf-decoder" target="_blank">https://github.com/ribt/dtmf-decoder</a><br>
<a href="https://www.dcode.fr/multitap-abc-cipher" target="_blank">https://www.dcode.fr/multitap-abc-cipher</a><br>
<a href="https://www.dcode.fr/t9-cipheraudi" target="_blank">https://www.dcode.fr/t9-cipheraudi</a><br>
<a href="https://www.windows7download.com/win7-dtmf-tone-decoder/mgbuqfct.html" target="_blank">https://www.windows7download.com/win7-dtmf-tone-decoder/mgbuqfct.html</a><br> 
<a href="http://www.windows7download.com/win7-dtmf-tone-decoder/download-mgbuqfct.html" target="_blank">http://www.windows7download.com/win7-dtmf-tone-decoder/download-mgbuqfct.html</a><br> 
<a href="https://www.windows7download.com/win7-dtmf-tone-decoder/download-mgbuqfct.html" target="_blank">https://www.windows7download.com/win7-dtmf-tone-decoder/download-mgbuqfct.html</a><br> 
<a href="https://dtmf.netlify.app" target="_blank">https://dtmf.netlify.app</a><br>
<a href="https://jpinsoft.net/deepsound/download.aspx" target="_blank">https://jpinsoft.net/deepsound/download.aspx</a><br>
<a href="https://www.youtube.com/watch?v=VZbZa99ocPU&ab_channel=mdthib" target="_blank">https://www.youtube.com/watch?v=VZbZa99ocPU&ab_channel=mdthib</a><br>
<a href="https://www.youtube.com/watch?v=rAGkm4pv44s" target="_blank">https://www.youtube.com/watch?v=rAGkm4pv44s</a><br>
<a href="https://www.aperisolve.com" target="_blank">https://www.aperisolve.com</a><br>
<a href="https://www.aperisolve.com/cheatsheet" target="_blank">https://www.aperisolve.com/cheatsheet</a><br>
<a href="https://www.dcode.fr/spectral-analysis" target="_blank">https://www.dcode.fr/spectral-analysis</a><br>
<a href="https://gqrx.dk" target="_blank">https://gqrx.dk</a><br><br>
</details>

<details markdown>
  <summary>[Audio - Extract Morse Code from an audio file]</summary>
<a href="https://morsecode.world/international/decoder/audio-decoder-adaptive.html" target="_blank">https://morsecode.world/international/decoder/audio-decoder-adaptive.html</a><br>
<a href="https://databorder.com/transfer/morse-sound-receiver" target="_blank">https://databorder.com/transfer/morse-sound-receiver</a><br><br>
</details>

<details markdown>
  <summary>[Large Number/Big Integer/Big Number converter]</summary>
<a href="http://www.onedollardata.com/encoder.php" target="_blank">http://www.onedollardata.com/encoder.php</a><br><br>
</details>

<details markdown>
  <summary>[Stego - Some Resources]</summary>
<a href="https://fareedfauzi.gitbook.io/ctf-checklist-for-beginner/steganography" target="_blank"></a>https://fareedfauzi.gitbook.io/ctf-checklist-for-beginner/steganography<br>
<a href="https://www.kali.org/tools/steghide" target="_blank">https://www.kali.org/tools/steghide</a><br>
<a href="https://steghide.sourceforge.net" target="_blank">https://steghide.sourceforge.net</a><br>
<a href="https://www.geeksforgeeks.org/how-to-install-steghide-tool-in-linux" target="_blank">https://www.geeksforgeeks.org/how-to-install-steghide-tool-in-linux</a><br>
<a href="https://stegonline.georgeom.net/upload" target="_blank">https://stegonline.georgeom.net/upload</a><br>
<a href="http://magiceye.ecksdee.co.uk" target="_blank">http://magiceye.ecksdee.co.uk</a><br>
<a href="https://manytools.org/hacker-tools/steganography-encode-text-into-image" target="_blank">https://manytools.org/hacker-tools/steganography-encode-text-into-image</a><br>
<a href="https://www.mobilefish.com/services/steganography/steganography.php" target="_blank">https://www.mobilefish.com/services/steganography/steganography.php</a><br>
<a href="http://stylesuxx.github.io/steganography" target="_blank">http://stylesuxx.github.io/steganography</a><br>
<a href="https://futureboy.us/stegano" target="_blank">https://futureboy.us/stegano</a><br>
<a href="https://neatnik.net/steganographr" target="_blank">https://neatnik.net/steganographr</a><br>
<a href="https://wiki.bi0s.in/steganography/zsteg" target="_blank">https://wiki.bi0s.in/steganography/zsteg</a><br>
<a href="https://github.com/zed-0xff/zsteg" target="_blank">https://github.com/zed-0xff/zsteg</a><br>
<a href="https://github.com/ragibson/Steganography#WavSteg" target="_blank">https://github.com/ragibson/Steganography#WavSteg</a><br>
<a href="https://github.com/ragibson/Steganography#lsbsteg" target="_blank">https://github.com/ragibson/Steganography#lsbsteg</a><br>
<a href="https://github.com/ragibson/Steganography#stegdetect" target="_blank">https://github.com/ragibson/Steganography#stegdetect</a><br>
<a href="https://github.com/pavanchhatpar/wav-steg-py" target="_blank">https://github.com/pavanchhatpar/wav-steg-py</a><br>
<a href="https://0xrick.github.io/lists/stego" target="_blank">https://0xrick.github.io/lists/stego</a><br>
<a href="https://www.linuxlinks.com/wavsteg-uses-least-significant-bit-steganography" target="_blank">https://www.linuxlinks.com/wavsteg-uses-least-significant-bit-steganography</a><br>
<a href="https://www.abc.se/~re/Coagula/Coagula.html" target="_blank">https://www.abc.se/~re/Coagula/Coagula.html</a><br>
<a href="https://www.stenge.info/post/steganography" target="_blank">https://www.stenge.info/post/steganography</a><br>
<a href="https://cheatography.com/aleksandrm/cheat-sheets/coagula-cheat-sheet" target="_blank">https://cheatography.com/aleksandrm/cheat-sheets/coagula-cheat-sheet</a><br>
<a href="https://github.com/zardus/ctf-tools/blob/master/stegsolve/install" target="_blank">https://github.com/zardus/ctf-tools/blob/master/stegsolve/install</a><br>
<a href="http://www.caesum.com/handbook/Stegsolve.jar" target="_blank">http://www.caesum.com/handbook/Stegsolve.jar</a><br>
<a href="https://www.hanynet.com/isteg" target="_blank">https://www.hanynet.com/isteg</a><br>
<a href="https://github.com/rafiibrahim8/iSteg" target="_blank">https://github.com/rafiibrahim8/iSteg</a><br><br>
</details>

<details markdown>
  <summary>[Stego - iSteg]</summary>
<a href="https://github.com/rafiibrahim8/iSteg" target="_blank"></a>https://github.com/rafiibrahim8/iSteg<br>
1. Navigated to: https://github.com/rafiibrahim8/iSteg/releases/tag/v2.1.<br>
2. Downloaded the file: iSteg-v2.1_GUI.jar.<br>
3. Ran chmod +x on the download file to give it executable permissions.<br>
└─# chmod +x iSteg-v2.1_GUI.jar<br>
4. Launched the program in Java:<br>
└─# java -jar iSteg-v2.1_GUI.jar<br>
<img src="images/image211.png"><br><br>
5. Chose the hidden.png file and it opened to the flag, flag{YouFoundMe}:<br>
<img src="images/image213.png"><br><br>
</details>

<details markdown>
  <summary>[StegSolve]</summary>
<a href="https://github.com/zardus/ctf-tools/blob/master/stegsolve/install" target="_blank"></a>https://github.com/zardus/ctf-tools/blob/master/stegsolve/install<br>
<a href="http://www.caesum.com/handbook/Stegsolve.jar" target="_blank"></a>http://www.caesum.com/handbook/Stegsolve.jar<br>
1. wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar<br>
2. chmod +x stegsolve.jar<br>
3. Run by typing: java –jar stegsolve.jar (make sure you’re in the same directory)<br>
4. Choose “File” --> Open and load your picture:<br>
<img src="images/image211.png"><br><br>
</details>
























