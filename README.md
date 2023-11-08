# icanhaspii - CTF CheatSheet
<html>
<body>
<details markdown>
  <summary>[Commands]</summary>
<ul>
  <li><B>file</B>
    <ul>
      <li>Run this to determine what type of file you are dealing with:</li>
      <BR>
      <BR>
<img src="images/File_Screenshot 2023-10-03 203208.png">
      <BR>
      <BR>
    </ul>
  </li>
  <BR>
  <li><B>binwalk</B></li>
    <ul>
      <li>Run this to view a summary of the file contents:</li>
      <BR>
      <BR>
<img src="images/BinWalk_Screenshot 2023-10-03 203227.png">
      <BR>
      <BR>
    </ul>
  <BR>
  <li><B>strings</B></li>
    <ul>
      <li>Run this to get the list of printable characters from files.  You can even run strings on a Pcap!  Or, say for example, that you have something you think contains a flag and you know that flag is in the typical CTF format of flag{some_bonus}, you can run the following to cut down on the amount of data you have to parse through. The following will only yield lines of 8 characters or more:
<BR>
<BR>
<img src="images/Strings_Screenshot 2023-05-12 172558.jpg">
<BR>
<BR>
You can even combine strings and grep:
<BR>
<BR>
<img src="images/Strings_Screenshot 2023-05-12 174704.jpg">


 
      
      </li>
    </ul>


</ul>

</details>

  <details>
  <br>
  <summary>[binwalk] Shows file contents</summary>
  Run to find a summary of file contents.

</details>
<details>
  <br>
  <summary>[strings] Spits out code</summary>
  You can run strings on a Pcap!

  Or, let’s say, for example, that you have something you think contains a flag and you know that flag is in the typical CTF format of flag{some_bonus}, you can run the following to cut down on the amount of data you have to parse through. The following will only yield lines of 8 characters or more - Credit to Noah Heckman at BHIS:

</details>

</body>
</html>



