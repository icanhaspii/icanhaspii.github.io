# icanhaspii - CTF CheatSheet
<html>
<body>
<details>
  <summary>[Commands]</summary>
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
You can even combine strings and grep:
<BR>
<BR>
<img src="images/Strings_Screenshot 2023-05-12 174704.jpg">
   </ul>
 </li>
<BR>
  <li><B>java -jar</B></li>
    <ul>
      <li>This command will open a .jar file:</li>
      <BR>
<img src="images\JavaJarStegSolveHowTo.png">
      <BR>
    </ul>
  <BR>




</ul>
</details>





</body>
</html>



