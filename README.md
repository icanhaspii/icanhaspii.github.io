# icanhaspii-CTF CheatSheet
<html>
<body>
<details>
  <summary>[Linux Analysis Commands]</summary>
<ul>
  <li><B>file</B>
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
   </ul>
 </li>
<BR>
  <li><B>java -jar</B></li>
    <ul>
      <li>The java -jar command will open a .jar file:</li>
      <BR>
<img src="images\Java_JarStegSolveHowTo.png">
      <BR>
    </ul>
  <BR>
<ul>
 <li><B>java</B></li>
    <ul>
      <li>The java command will open a .java file:</li>
      <BR>
<img src="images/Java_Screenshot 2022-06-15 085349_Edited.png">
      <BR>
    </ul>
 <BR>
<ul>
 <li><B>base64</B></li>
    <ul>
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
4. If you’re feeling really fancy, and you are playing a CTF, you can run the following to echo/print your decoded base64 in standard flag forma to your screent: 
<BR>
echo "flag{$(echo 'Umlja19SMGxsM2Q=' | base64 -d)}"
<BR>
<BR>
<img src="images/Base64_Screenshot 2023-11-08 180945.png">
<BR>
<BR>
-Here’s another way: 
<BR>
1. Grab a base64 encoded string such as: Umlja19SMGxsM2Q= 
<BR>
<BR>
<img src="images/Base64_Screenshot 2023-11-08 173111.png">
<BR>
<BR>
2. Type the following into your Linux command prompt: 
<BR>
Base64 –d 
<BR>
<BR>
<img src="images/Base64_Screenshot 2023-11-08 172847.png">
<BR>
<BR>
3. Hit ENTER 






</ul>
</details>





</body>
</html>



