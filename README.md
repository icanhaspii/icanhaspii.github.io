<html lang="en-US">
<head>
<title>icanhaspii CTF STUFF</title>
<meta name="Keywords" content="CTF, Tutorials, Programming, Web Development, Training, Learning, Linux">
<meta name="Description" content="Well organized and easy to understand CTF and Linux tutorial with lots of examples.">
<meta property="og:description" content="Well organized and easy to understand CTF and Linux tutorial with lots of examples.">
</head>
<body>
<h1>icanhaspii-CTF CheatSheet</h1>
<details>
  <summary>[Linux Analysis Commands]</summary>
<ul>
  <li><B>file</B></li>
    <ul>
      <li>Run this to determine what type of file you are dealing with:</li>
      <BR>
<img src="images/File_Screenshot 2023-10-03 203208.png">
      <BR>
    </ul>
  <BR>
  <li><B>binwalk</B></li>
    <ul>
      <li>Run this to view a summary of the file contents:</li>
      <BR>
<img src="images/BinWalk_Screenshot 2023-10-03 203227.png">
      <BR>
    </ul>
  <BR>
  <li><B>strings</B></li>
    <ul>
      <li>Run this to get the list of printable characters from files.  You can even run strings on a Pcap!  Or, say for example, that you have something you think contains a flag and you know that flag is in the typical CTF format of flag{some_bonus}, you can run the following to cut down on the amount of data you have to parse through. The following will only yield lines of 8 characters or more:</li>
<BR>
<img src="images/Strings_Screenshot 2023-05-12 172558.jpg">
<BR>
<BR>
You can even combine strings and grep:
<BR>
<BR>
<img src="images/Strings_Screenshot 2023-05-12 174704.jpg">
<BR>
   </ul>
<BR>
<li><B>java -jar</B></li>
    <ul>
      <li>The java -jar command will open a .jar file:</li>
<BR>
<img src="images\Java_JarStegSolveHowTo.png">
  </ul>
<BR>
 <li><B>java</B></li>
    <ul>
      <li>The java command will open a .java file:</li>
      <BR>
<img src="images/Java_Screenshot 2022-06-15 085349_Edited.png">
      <BR>
    </ul>
 <BR>
<li><B>base64</B></li>
<UL>
<li>The base64 decode command will decode a b64 string.  There’s more than one way to invoke the base64 decode command, here are few:
<BR>
<BR>
1. Grab a base64 encoded string such as: Umlja19SMGxsM2Q=
<BR>
<BR>
2. Type the following into your Linux command prompt to echo/print to screen:
<BR>
<BR>
echo 'Umlja19SMGxsM2Q=' | base64 -d
<BR>
<BR>
3. Hit ENTER
<BR>
<BR>
<img src="images/Base64_Screenshot 2023-11-08 172521.png">
<BR>
<BR>
4. If you’re feeling really fancy, and you are playing a CTF, you can run the following to echo/print your decoded b64 in standard flag format to your screen:
<BR>
<BR>
echo "flag{$(echo 'Umlja19SMGxsM2Q=' | base64 -d)}"
<BR>
<BR>
<img src="images/Base64_Screenshot 2023-11-08 180945.png">
<BR>
<BR>
-Here’s another way:
<BR>
<BR>
1. Grab a base64 encoded string such as: Umlja19SMGxsM2Q=
<BR>
<BR>
2. Type the following into your Linux command prompt:
<BR>
<BR>
Base64 –d
<BR>
<BR>
3. Hit ENTER 
<BR>
<BR>
<img src="images/Base64_Screenshot 2023-11-08 173111.png">
<BR>
<BR>
4. At the prompt, paste in your base64 encoded string:
<BR>
<BR>
<img src="images/Base64_Screenshot 2023-11-08 173249.png">
<BR>
<BR>
5. Hit ENTER again:
<BR>
<BR>
<img src="images/Base64_Screenshot 2023-11-08 173640.png">
<BR>
<BR>
6. Finally, hit Control-D on your keyboard:
<BR>
<BR>
<img src="images/Base64_Screenshot 2023-11-08 172847.png">
<BR>
<BR>
-And yet another method:
<BR>
<BR>
1. Save your base64 encoded string into a text editor:
<BR>
<BR>
<img src="images/Base64_Screenshot 2023-11-08 174625.png">
<BR>
<BR>
2. Type the following into your Linux command prompt to echo/print to screen:
<BR>
<BR>
base64 -d dns.txt >decoded.txt
<BR>
<BR>
<img src="images/Base64_Screenshot 2023-11-08 174546.png">
<BR>
<BR>
3. Open your new file, “decoded.txt”:
<BR>
<BR>
<img src="images/Base64_Screenshot 2023-11-08 174720.png">
<BR>
<BR>
If you run across encoding similar to below:
<BR>
<BR>
IO.Compression.DeflateStream([IO.MemoryStream][Convert]::FromBase64String
<BR>
[IO.Compression.CompressionMode]::Decompress
<BR>
<BR>
You can try the following “Recipe” in CyberChef to decode:
<BR>
<BR>
(a)From_Base64('A-Za-z0-9%2B/%3D',true,false)
<BR>
(b) Raw_Inflate(0,0,%5B'Adaptive','Block'%5D,false,false)
<BR>
</UL>
<BR CLEAR=ALL>
<li><B>ifconfig</B></li>
<ul>
<li>To find your ip address and network configuration, you can use the old ifconfig command (considered depreciated), or the newer ip address command.  It works with any of the following, and of course more in depth combined with switches:</li>
<BR>
<img src="images/ip_Screenshot 2023-11-09 105007.png">
<BR>
<BR>
<img src="images/ip_Screenshot 2023-11-09 104951.png">
<BR>
<BR>
<img src="images/ip_Screenshot 2023-11-09 104928.png">
<BR>
<BR>







  
</details>


</body>
</html>



