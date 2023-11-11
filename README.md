<html lang="en-US">
<head>
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
You can also combine strings and grep:
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
<li>The base64 decode command will decode a b64 string.  There’s more than one way to invoke the base64 decode command, here are few:</li>
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
</ul>
<BR>
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
</ul>
  </ul>
</details>
<details>
<summary>[Pcap Analysis]</summary>
<ul>
  <li><B>Strings</B></li>
    <ul>
      <li>You can run strings on a Pcap! Below are a couple examples (I like to pipe my results to a .txt file for easier review):</li>
      <BR>
<img src="images/StringsPcap_Screenshot 2023-11-09 184958.png">
      <BR>
    </ul>
  <BR>
  <li><B>TShark</B></li>
    <ul>
      <li><a href="https://osqa-ask.wireshark.org/questions/38071/how-to-extract-ip-addresses-from-cap-file-to-text-file" target="_blank">You can extract ip addresses from a Pcap using Tshark</a></li>
<BR>
To extract just the destination ip, type the following command:
<BR>
<BR>
<img src="images/TShark_Screenshot 2023-03-16 211016.jpg">
<BR>
<BR>
To extract both the destination ip and the source ip, type the following command:
<BR>
<BR>
<img src="images/TShark_Screenshot 2023-03-16 211435.jpg">
<BR>
</ul>
<BR>
<li><B>Zeek</B></li>
  <ul>
<li><a href="https://www.youtube.com/watch?v=bznH1yMyjjo&ab_channel=JohnHubbard" target="_blank">John Hubbard has a fantastic install video</a></li>
<BR>
Zeek installs itself here: 
<img src="images/Zeek_Screenshot 2023-03-24 201006_Edited.jpg">
<BR>
<BR>
To export logs from a Pcap into Zeek format, type the following syntax (r is for read):
<BR>
<img src="images/Zeek_Screenshot 2023-03-24 201006.jpg">
<BR>
</ul>
<BR>
<li><B>realpath</B></li>
    <ul>
      <li>realpath converts each filename argument to an absolute pathname, which has no components that are symbolic links or the special . or .. directory entries. (See realpath(3) for more information.)</span></p><p class="c4"><span class="c2">Each path component in the filename must exist, otherwise realpath will fail and non-zero exit status will be returned.</span></p></ul>
	  
	  <p class="c3"><span class="c2"></span></p><ul class="c8 lst-kix_list_16-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://linux.die.net/man/1/realpath&amp;sa=D&amp;source=editors&amp;ust=1699590511374365&amp;usg=AOvVaw1FkT0L7tNSOCrQIqhPv2FA">https://linux.die.net/man/1/realpath</a></span></li></ul>


</ul>
  </ul>
</details>
<details>
<summary>[Audio Analysis]</summary>
<ul>
  <li><B>Audio Decoders/Analyzers:</B></li>


<ul class="c8 lst-kix_list_73-0 start"><li class="c37 c55 li-bullet-0"><h1 style="display:inline"><span class="c35">Note from Dcode:</span></h1></li></ul><ol class="c8 lst-kix_list_1-2 start" start="1"><li class="c28"><h3 style="display:inline"><span class="c53">T9 vs Multitap Confusion</span></h3></li></ol><p class="c4"><span class="c25">Multitap ABC should not be confused with </span><span class="c42">T9 predictive text</span><span class="c25">. &#39;DCODE&#39; is written &#39;3222666333&#39; in Multitap and &#39;32633&#39; in T9.</span></p>

<ul class="c8 lst-kix_list_74-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.audacityteam.org/download&amp;sa=D&amp;source=editors&amp;ust=1699590511452912&amp;usg=AOvVaw2QZV0JaRdRjc-gCdKlBvpF">https://www.audacityteam.org/download</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.sonicvisualiser.org/download.html&amp;sa=D&amp;source=editors&amp;ust=1699590511453392&amp;usg=AOvVaw2Qy7sx64kDtnsqX9bY0HEt">https://www.sonicvisualiser.org/download.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=http://dialabc.com/sound/detect/index.html&amp;sa=D&amp;source=editors&amp;ust=1699590511453747&amp;usg=AOvVaw0kaG3YIbpA9RJVKR_vgBhl">http://dialabc.com/sound/detect/index.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=http://www.polar-electric.com/DTMF/Index.html&amp;sa=D&amp;source=editors&amp;ust=1699590511454071&amp;usg=AOvVaw16zUJuCHCAK5-0fEtUC5Y7">http://www.polar-electric.com/DTMF/Index.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://twitter.com/_johnhammond/status/1244277165316857857?lang%3Den&amp;sa=D&amp;source=editors&amp;ust=1699590511454420&amp;usg=AOvVaw3EMjT6Cp3EcHH9Y5_pne5J">https://twitter.com/_johnhammond/status/1244277165316857857?lang=en</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://forums.radioreference.com/threads/twotonedetect-beta.120010&amp;sa=D&amp;source=editors&amp;ust=1699590511454799&amp;usg=AOvVaw2dklZItiI_dNMMrXig7WOg">https://forums.radioreference.com/threads/twotonedetect-beta.120010</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://onlinetonegenerator.com/dtmf.html&amp;sa=D&amp;source=editors&amp;ust=1699590511455211&amp;usg=AOvVaw2StEXRFmuI2hz4EEh5XW1_">https://onlinetonegenerator.com/dtmf.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.venea.net/web/dtmf_generator&amp;sa=D&amp;source=editors&amp;ust=1699590511455635&amp;usg=AOvVaw1DFPNu59tmWZwTfnSzZLSe">https://www.venea.net/web/dtmf_generator</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/ribt/dtmf-decoder&amp;sa=D&amp;source=editors&amp;ust=1699590511455975&amp;usg=AOvVaw1zvce9h6o-Kn7QZ8uRjoFk">https://github.com/ribt/dtmf-decoder</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.dcode.fr/multitap-abc-cipher&amp;sa=D&amp;source=editors&amp;ust=1699590511456372&amp;usg=AOvVaw1SxtEHJ-SJmCNppmjGOKvf">https://www.dcode.fr/multitap-abc-cipher</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.dcode.fr/t9-cipheraudi&amp;sa=D&amp;source=editors&amp;ust=1699590511456713&amp;usg=AOvVaw2amwI4OQdTxU-xUspqNuCo">https://www.dcode.fr/t9-cipheraudi</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.windows7download.com/win7-dtmf-tone-decoder/mgbuqfct.html&amp;sa=D&amp;source=editors&amp;ust=1699590511457141&amp;usg=AOvVaw0ttPUxPqXzDRJ-bZR3Bh09">https://www.windows7download.com/win7-dtmf-tone-decoder/mgbuqfct.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=http://www.windows7download.com/win7-dtmf-tone-decoder/download-mgbuqfct.html&amp;sa=D&amp;source=editors&amp;ust=1699590511457577&amp;usg=AOvVaw0SIXJjjtcEchaOX7czKbs-">http://www.windows7download.com/win7-dtmf-tone-decoder/download-mgbuqfct.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.windows7download.com/win7-dtmf-tone-decoder/download-mgbuqfct.html&amp;sa=D&amp;source=editors&amp;ust=1699590511457976&amp;usg=AOvVaw2MgfzTNxtNbfgTp9dIoP1X">https://www.windows7download.com/win7-dtmf-tone-decoder/download-mgbuqfct.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://dtmf.netlify.app/&amp;sa=D&amp;source=editors&amp;ust=1699590511458343&amp;usg=AOvVaw0FAmLfAUEUYM1NXpWkHwUH">https://dtmf.netlify.app</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://jpinsoft.net/deepsound/download.aspx&amp;sa=D&amp;source=editors&amp;ust=1699590511458709&amp;usg=AOvVaw1yqe2kr28mZEc6fwucto_1">https://jpinsoft.net/deepsound/download.aspx</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.youtube.com/watch?v%3DVZbZa99ocPU%26ab_channel%3Dmdthib&amp;sa=D&amp;source=editors&amp;ust=1699590511459082&amp;usg=AOvVaw2DtibT2D8vUZMxWQuzaA7K">https://www.youtube.com/watch?v=VZbZa99ocPU&amp;ab_channel=mdthib</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.youtube.com/watch?v%3DrAGkm4pv44s&amp;sa=D&amp;source=editors&amp;ust=1699590511459479&amp;usg=AOvVaw0ZLHIAf_Ba0LxP_uUjGDXV">https://www.youtube.com/watch?v=rAGkm4pv44s</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.aperisolve.com/&amp;sa=D&amp;source=editors&amp;ust=1699590511459836&amp;usg=AOvVaw02tPOepx6gfx8SI7YZzYq8">https://www.aperisolve.com</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.aperisolve.com/cheatsheet&amp;sa=D&amp;source=editors&amp;ust=1699590511460149&amp;usg=AOvVaw3GWdDTvVlZn3GfBb0VuBXv">https://www.aperisolve.com/cheatsheet</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.dcode.fr/spectral-analysis&amp;sa=D&amp;source=editors&amp;ust=1699590511460521&amp;usg=AOvVaw1eqC9KSd5iLeeNldO3gqcX">https://www.dcode.fr/spectral-analysis</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://gqrx.dk/&amp;sa=D&amp;source=editors&amp;ust=1699590511460879&amp;usg=AOvVaw1iw_9S_X58jcOPn-NMyTEh">https://gqrx.dk</a></span></li></ul>


</li>
</ul>
<ul>
  <li><B>Extract Morse Code from an audio file:</B></li>

<ul class="c8 lst-kix_list_76-0 start"><li class="c0 li-bullet-0"><span class="c13"><a class="c6" href="https://www.google.com/url?q=https://morsecode.world/international/decoder/audio-decoder-adaptive.html&amp;sa=D&amp;source=editors&amp;ust=1699590511461429&amp;usg=AOvVaw2wEGICynnHkrYlToVmXtnp">https://morsecode.world/international/decoder/audio-decoder-adaptive.html</a></span></li><li class="c0 li-bullet-0"><span class="c13"><a class="c6" href="https://www.google.com/url?q=https://databorder.com/transfer/morse-sound-receiver&amp;sa=D&amp;source=editors&amp;ust=1699590511461784&amp;usg=AOvVaw06xdLYFFSg04sW08pCzQ89">https://databorder.com/transfer/morse-sound-receiver</a></span></li></ul>

</li>
</ul>
<ul>
  <li><B>Large Number/Big Integer/Big Number converter:</B></li>

<ul class="c8 lst-kix_list_2-0"><li class="c5 c40 li-bullet-0"><span class="c39"><a class="c6" href="https://www.google.com/url?q=http://www.onedollardata.com/encoder.php&amp;sa=D&amp;source=editors&amp;ust=1699590511462302&amp;usg=AOvVaw3q4Ui_w_hqUug-cYWtjkzN">http://www.onedollardata.com/encoder.php</a></span></li></ul>

</li>
</ul>
<ul>
  <li><B>Stego:</B></li>

<ul class="c8 lst-kix_list_78-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://fareedfauzi.gitbook.io/ctf-checklist-for-beginner/steganography&amp;sa=D&amp;source=editors&amp;ust=1699590511462785&amp;usg=AOvVaw3_4gNtVAgqsxY9cQOYDV6q">https://fareedfauzi.gitbook.io/ctf-checklist-for-beginner/steganography</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.kali.org/tools/steghide&amp;sa=D&amp;source=editors&amp;ust=1699590511463108&amp;usg=AOvVaw3PyLddht9ICuD5wAJL7XOR">https://www.kali.org/tools/steghide</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://steghide.sourceforge.net/&amp;sa=D&amp;source=editors&amp;ust=1699590511463421&amp;usg=AOvVaw3YjMg5aBgrYXi1oA3fs1MH">https://steghide.sourceforge.net</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.geeksforgeeks.org/how-to-install-steghide-tool-in-linux&amp;sa=D&amp;source=editors&amp;ust=1699590511463830&amp;usg=AOvVaw18QAz0QCXb6OnaypPH3uvw">https://www.geeksforgeeks.org/how-to-install-steghide-tool-in-linux</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://stegonline.georgeom.net/upload&amp;sa=D&amp;source=editors&amp;ust=1699590511464181&amp;usg=AOvVaw3-d5H--MBlevGIodMgiNzr">https://stegonline.georgeom.net/upload</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=http://magiceye.ecksdee.co.uk/&amp;sa=D&amp;source=editors&amp;ust=1699590511464534&amp;usg=AOvVaw20jt0nxjbt2nPHq9CcQiPb">http://magiceye.ecksdee.co.uk</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://manytools.org/hacker-tools/steganography-encode-text-into-image&amp;sa=D&amp;source=editors&amp;ust=1699590511464922&amp;usg=AOvVaw0CAV-qblYsY9TekZCyzn8I">https://manytools.org/hacker-tools/steganography-encode-text-into-image</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.mobilefish.com/services/steganography/steganography.php&amp;sa=D&amp;source=editors&amp;ust=1699590511465291&amp;usg=AOvVaw27LCgEPsUZ227blMjNYUA5">https://www.mobilefish.com/services/steganography/steganography.php</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=http://stylesuxx.github.io/steganography&amp;sa=D&amp;source=editors&amp;ust=1699590511465647&amp;usg=AOvVaw0XUnAi2QLpAt3hfNB9mJ1p">http://stylesuxx.github.io/steganography</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://futureboy.us/stegano&amp;sa=D&amp;source=editors&amp;ust=1699590511466008&amp;usg=AOvVaw1JEVoF-w0bY886h5ozKN4A">https://futureboy.us/stegano</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://neatnik.net/steganographr&amp;sa=D&amp;source=editors&amp;ust=1699590511466354&amp;usg=AOvVaw2JMCZ_97g-zZ2xKqFUl9eK">https://neatnik.net/steganographr</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://wiki.bi0s.in/steganography/zsteg&amp;sa=D&amp;source=editors&amp;ust=1699590511466671&amp;usg=AOvVaw05Pz8TTPAiuhMrc8a_cDo4">https://wiki.bi0s.in/steganography/zsteg</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/zed-0xff/zsteg&amp;sa=D&amp;source=editors&amp;ust=1699590511467013&amp;usg=AOvVaw2DCMCggoM4YZ_bOv4Qs-q5">https://github.com/zed-0xff/zsteg</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/ragibson/Steganography%23WavSteg&amp;sa=D&amp;source=editors&amp;ust=1699590511467369&amp;usg=AOvVaw03fmejgasbSx97jy18s8IW">https://github.com/ragibson/Steganography#WavSteg</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/ragibson/Steganography%23lsbsteg&amp;sa=D&amp;source=editors&amp;ust=1699590511467789&amp;usg=AOvVaw2AS1Wq06OXBDdOLlAdknSs">https://github.com/ragibson/Steganography#lsbsteg</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/ragibson/Steganography%23stegdetect&amp;sa=D&amp;source=editors&amp;ust=1699590511468158&amp;usg=AOvVaw3vU2mUvp1aMIYHxBW4n0nf">https://github.com/ragibson/Steganography#stegdetect</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/pavanchhatpar/wav-steg-py&amp;sa=D&amp;source=editors&amp;ust=1699590511468488&amp;usg=AOvVaw08DpzB34dBzltUuLDu5kUH">https://github.com/pavanchhatpar/wav-steg-py</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://0xrick.github.io/lists/stego&amp;sa=D&amp;source=editors&amp;ust=1699590511468830&amp;usg=AOvVaw1WenFDPy724ASIQfDz1E-9">https://0xrick.github.io/lists/stego</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.linuxlinks.com/wavsteg-uses-least-significant-bit-steganography&amp;sa=D&amp;source=editors&amp;ust=1699590511469189&amp;usg=AOvVaw08VcEnJ70Js39y2150dXQz">https://www.linuxlinks.com/wavsteg-uses-least-significant-bit-steganography</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.abc.se/~re/Coagula/Coagula.html&amp;sa=D&amp;source=editors&amp;ust=1699590511469587&amp;usg=AOvVaw2GXap11o6Lz2ip4f1hE3ZY">https://www.abc.se/~re/Coagula/Coagula.html</a></span></li><li class="c0 li-bullet-0"><span class="c13"><a class="c6" href="https://www.google.com/url?q=https://www.stenge.info/post/steganography&amp;sa=D&amp;source=editors&amp;ust=1699590511469927&amp;usg=AOvVaw1AI0Hk4eIz3EfthHnrny1Q">https://www.stenge.info/post/steganography</a></span></li><li class="c0 li-bullet-0"><span class="c13"><a class="c6" href="https://www.google.com/url?q=https://cheatography.com/aleksandrm/cheat-sheets/coagula-cheat-sheet&amp;sa=D&amp;source=editors&amp;ust=1699590511470311&amp;usg=AOvVaw0pdQH45Y7NM5HyHASir8yR">https://cheatography.com/aleksandrm/cheat-sheets/coagula-cheat-sheet</a></span></li><li class="c0 li-bullet-0"><span class="c13"><a class="c6" href="https://www.google.com/url?q=https://github.com/zardus/ctf-tools/blob/master/stegsolve/install&amp;sa=D&amp;source=editors&amp;ust=1699590511470688&amp;usg=AOvVaw1QRKdjvpv1I-TbqfGSsXFl">https://github.com/zardus/ctf-tools/blob/master/stegsolve/install</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=http://www.caesum.com/handbook/Stegsolve.jar&amp;sa=D&amp;source=editors&amp;ust=1699590511471018&amp;usg=AOvVaw0d32hmvlcoeDxZTug0QUWM">http://www.caesum.com/handbook/Stegsolve.jar</a></span></li><li class="c0 li-bullet-0"><span class="c13"><a class="c6" href="https://www.google.com/url?q=https://www.hanynet.com/isteg&amp;sa=D&amp;source=editors&amp;ust=1699590511471371&amp;usg=AOvVaw2xHxNHaPjuF3wscQw13KVV">https://www.hanynet.com/isteg</a></span></li><li class="c0 li-bullet-0"><span class="c13"><a class="c6" href="https://www.google.com/url?q=https://github.com/rafiibrahim8/iSteg&amp;sa=D&amp;source=editors&amp;ust=1699590511471712&amp;usg=AOvVaw2l3UUqSzmUPCQLbz7Ve-Rd">https://github.com/rafiibrahim8/iSteg</a></span></li></ul>



</li>
</ul>
<ul>
  <li><B>iSteg:</B></li>


<ul class="c8 lst-kix_list_78-0"><li class="c0 li-bullet-0"><span class="c13"><a class="c6" href="https://www.google.com/url?q=https://github.com/rafiibrahim8/iSteg&amp;sa=D&amp;source=editors&amp;ust=1699590511474222&amp;usg=AOvVaw2K75Md6eBDLX-_LKm8QAwc">https://github.com/rafiibrahim8/iSteg</a></span></li></ul><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c2">1. Navigated to: </span><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/rafiibrahim8/iSteg/releases/tag/v2.1&amp;sa=D&amp;source=editors&amp;ust=1699590511474631&amp;usg=AOvVaw2amYHoBiUhPKfaCOe7-JO4">https://github.com/rafiibrahim8/iSteg/releases/tag/v2.1</a></span><span class="c2">.</span></p><p class="c4"><span class="c2">2. Downloaded the file: iSteg-v2.1_GUI.jar.</span></p><p class="c4"><span class="c2">3. Ran chmod +x on the download file to give it executable permissions.</span></p><p class="c4"><span class="c2">&#9484;&#9472;&#9472;(root&#12927;kali)-[/home/kali/Desktop]</span></p><p class="c4"><span class="c2">&#9492;&#9472;# chmod +x iSteg-v2.1_GUI.jar </span></p><p class="c4"><span class="c2">4. Launched the program in Java:</span></p><p class="c4"><span class="c2">&#9484;&#9472;&#9472;(root&#12927;kali)-[/home/kali/Desktop]</span></p><p class="c4"><span class="c2">&#9492;&#9472;# java -jar iSteg-v2.1_GUI.jar &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 299.00px; height: 71.00px;"><img alt="" src="images/image213.png" style="width: 299.00px; height: 71.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p>
<p class="c4"><span class="c2">5. Chose the hidden.png file and it opened to the flag: flag{YouFoundMe}</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 712.87px; height: 215.33px;"><img alt="" src="images/image211.png" style="width: 712.87px; height: 215.33px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></li></ul>


</li>
</ul>
<ul>
  <li><B>StegSolve:</B></li>

<ul class="c8 lst-kix_list_80-0"><li class="c0 li-bullet-0"><span class="c13"><a class="c6" href="https://www.google.com/url?q=https://github.com/zardus/ctf-tools/blob/master/stegsolve/install&amp;sa=D&amp;source=editors&amp;ust=1699590511476051&amp;usg=AOvVaw3yDtXImWHG0S5LawOM3P6w">https://github.com/zardus/ctf-tools/blob/master/stegsolve/install</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=http://www.caesum.com/handbook/Stegsolve.jar&amp;sa=D&amp;source=editors&amp;ust=1699590511476413&amp;usg=AOvVaw1MrSXRqAyfGI56tc5GgVqc">http://www.caesum.com/handbook/Stegsolve.jar</a></span></li></ul><p class="c3"><span class="c2"></span></p><ol class="c8 lst-kix_list_81-0 start" start="1"><li class="c0 li-bullet-0"><span class="c2">wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar</span></li><li class="c0 li-bullet-0"><span class="c2">chmod +x stegsolve.jar</span></li><li class="c0 li-bullet-0"><span class="c2">Run by typing: java &ndash;jar stegsolve.jar (make sure you&rsquo;re in the same directory)</span></li><li class="c0 li-bullet-0"><span class="c2">Choose &ldquo;File&rdquo; --&gt; Open and load your picture:</span></li></ol><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 614.07px; height: 284.00px;"><img alt="" src="images/image201.png" style="width: 614.07px; height: 284.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></li></ul>





</li>
</ul>
<ul>
  <li><B>File Headers/Magic Bytes/File Types/Carving Files:</B></li>

<ul class="c8 lst-kix_list_79-0"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://gist.github.com/leommoore/f9e57ba2aa4bf197ebc5&amp;sa=D&amp;source=editors&amp;ust=1699590511477307&amp;usg=AOvVaw09JZcrysZY_JU2WqhpwRVh">https://gist.github.com/leommoore/f9e57ba2aa4bf197ebc5</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://en.wikipedia.org/wiki/List_of_file_signatures&amp;sa=D&amp;source=editors&amp;ust=1699590511477692&amp;usg=AOvVaw1mFrp2v81Kz8togN7PJQOt">https://en.wikipedia.org/wiki/List_of_file_signatures</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.garykessler.net/library/file_sigs.html&amp;sa=D&amp;source=editors&amp;ust=1699590511478057&amp;usg=AOvVaw0ZOaqbal9ne5UO7dCr9CBN">https://www.garykessler.net/library/file_sigs.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.netspi.com/blog/technical/web-application-penetration-testing/magic-bytes-identifying-common-file-formats-at-a-glance&amp;sa=D&amp;source=editors&amp;ust=1699590511478459&amp;usg=AOvVaw1wuVsAKTjYXnf8T7lrYxzW">https://www.netspi.com/blog/technical/web-application-penetration-testing/magic-bytes-identifying-common-file-formats-at-a-glance</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://anilsoni85.blogspot.com/2014/11/basics-of-png-file-format-with-libpng.html&amp;sa=D&amp;source=editors&amp;ust=1699590511478812&amp;usg=AOvVaw2a_hhyV-C31viIMLViYWzZ">https://anilsoni85.blogspot.com/2014/11/basics-of-png-file-format-with-libpng.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://asecuritysite.com/forensics/png?file%3D%252Flog%252Fbasn0g01.png&amp;sa=D&amp;source=editors&amp;ust=1699590511479192&amp;usg=AOvVaw3mWljfwyBUzEeq71QdkiE5">https://asecuritysite.com/forensics/png?file=%2Flog%2Fbasn0g01.png</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.red-gate.com/simple-talk/blogs/anatomy-of-a-net-assembly-pe-headers&amp;sa=D&amp;source=editors&amp;ust=1699590511479630&amp;usg=AOvVaw0h0Qb5xVcsLKNPYyiUyws0">https://www.red-gate.com/simple-talk/blogs/anatomy-of-a-net-assembly-pe-headers</a></span></li><li class="c0 li-bullet-0"><span class="c13"><a class="c6" href="https://www.google.com/url?q=https://www.youtube.com/watch?v%3D-8f8avZ2V7s%26t%3D614s&amp;sa=D&amp;source=editors&amp;ust=1699590511479965&amp;usg=AOvVaw27DyYTGy6PphTByGlQb3lM">https://www.youtube.com/watch?v=-8f8avZ2V7s&amp;t=614s</a></span></li></ul><p class="c3"><span class="c2"></span></li></ul>


</li>
</ul>
<ul>
  <li><B>OCR - Google Image Search now offers OCR:</B></li>

<ul class="c8 lst-kix_list_83-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.google.com/imghp?hl%3Den%26tab%3Dri%26ogbl&amp;sa=D&amp;source=editors&amp;ust=1699590511480422&amp;usg=AOvVaw3DPDXkvE-j2jmVYozrYhPo">https://www.google.com/imghp?hl=en&amp;tab=ri&amp;ogbl</a></span></li></ul><p class="c3"><span class="c2"></span></li></ul>



</li>
</ul>
<ul>
  <li><B>Reverse Text/Mirror Text/Backward Text/Upsidedown Text:</B></li>

<ul class="c8 lst-kix_list_83-0"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.flipyourtext.com/&amp;sa=D&amp;source=editors&amp;ust=1699590511480864&amp;usg=AOvVaw2qkXocSMny_GWXkLxqRQzZ">https://www.flipyourtext.com</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.upsidedowntext.com/&amp;sa=D&amp;source=editors&amp;ust=1699590511481170&amp;usg=AOvVaw3d2EXEAytkXjNqQXeCFsQN">https://www.upsidedowntext.com</a></span></li></ul><p class="c3"><span class="c2"></span></li></ul>


</ul>
  </ul>
</details>
<details>
<summary>[Binary Analysis]</summary>
<ul>
  <li><B>dmesg command:</B></li>

<ul class="c8 lst-kix_list_73-0 start"><li class="c0 li-bullet-0"><span class="c11">Note: Run after you launch an app that you want to find out more about, errors and such.</span></p><p class="c4"><span class="c2">The dmesg command is a Linux utility that displays kernel-related messages retrieved from the kernel ring buffer. The ring buffer stores information about hardware, device driver initialization, and messages from kernel modules that take place during system startup.</span></li></ul>

<ul class="c8 lst-kix_list_14-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://phoenixnap.com/kb/dmesg-linux&amp;sa=D&amp;source=editors&amp;ust=1699590511372003&amp;usg=AOvVaw1CelZUQR1WgyECN3MI6KFT">https://phoenixnap.com/kb/dmesg-linux</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.geeksforgeeks.org/how-to-use-the-dmesg-command-on-linux&amp;sa=D&amp;source=editors&amp;ust=1699590511372389&amp;usg=AOvVaw2-juWxHD5Hqh1Uf6zaHP10">https://www.geeksforgeeks.org/how-to-use-the-dmesg-command-on-linux</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://linuxize.com/post/dmesg-command-in-linux&amp;sa=D&amp;source=editors&amp;ust=1699590511372714&amp;usg=AOvVaw1IKLNyxiK90pLcmHARf-Ib">https://linuxize.com/post/dmesg-command-in-linux</a></span></li></ul><p class="c3"><span class="c2"></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 416.00px; height: 51.87px;"><img alt="" src="images/image68.png" style="width: 416.00px; height: 51.87px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 600.67px; height: 529.73px;"><img alt="" src="images/image70.png" style="width: 600.67px; height: 529.73px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></li></ul>



</li>
</ul>
<ul>
  <li><B>readelf command:</B></li>

<ul class="c8 lst-kix_list_73-0 start"><li class="c0 li-bullet-0"><span class="c11">readelf displays information about one or more ELF format object files. &nbsp;The options control what particular information to display.</span></p><p class="c4"><span class="c2">elffile... are the object files to be examined. &nbsp;32-bit and 64-bit ELF files are supported, as are archives containing ELF files. This program performs a similar function to objdump but it goes into more detail and it exists independently of the BFD library, so if there is a bug in BFD then readelf will not be affected.</span></li></ul>

<ul class="c8 lst-kix_list_14-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://phoenixnap.com/kb/dmesg-linux&amp;sa=D&amp;source=editors&amp;ust=1699590511372003&amp;usg=AOvVaw1CelZUQR1WgyECN3MI6KFT">https://phoenixnap.com/kb/dmesg-linux</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.geeksforgeeks.org/how-to-use-the-dmesg-command-on-linux&amp;sa=D&amp;source=editors&amp;ust=1699590511372389&amp;usg=AOvVaw2-juWxHD5Hqh1Uf6zaHP10">https://man7.org/linux/man-pages/man1/readelf.1.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://man7.org/linux/man-pages/man1/readelf.1.html&amp;sa=D&amp;source=editors&amp;ust=1699590511373665&amp;usg=AOvVaw1nJb1CVu_9Puz684CMeAmM">https://linuxize.com/post/dmesg-command-in-linux</a></span></li></ul><p class="c3"><span class="c2"></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 416.00px; height: 51.87px;"><img alt="" src="images/image68.png" style="width: 416.00px; height: 51.87px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 600.67px; height: 529.73px;"><img alt="" src="images/image70.png" style="width: 600.67px; height: 529.73px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></li></ul>



</li>
</ul>
<ul>
  <li><B>GDB:</B></li>

<ul class="c8 lst-kix_list_83-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://web.stanford.edu/class/archive/cs/cs107/cs107.1186/guide/gdb.html&amp;sa=D&amp;source=editors&amp;ust=1699590511375280&amp;usg=AOvVaw0mToWLuynwSI6zw_IbBYOp">https://web.stanford.edu/class/archive/cs/cs107/cs107.1186/guide/gdb.html</a></span></li></ul><p class="c3"><span class="c2"></span></li></ul>



</li>
</ul>
<ul>
  <li><B>Install GEF to enhance GDB:</B></li>

<ul class="c8 lst-kix_list_18-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/hugsy/gef&amp;sa=D&amp;source=editors&amp;ust=1699590511376098&amp;usg=AOvVaw0GXm-ss9gQN1_xLPjbM4Q0">https://github.com/hugsy/gef</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://hugsy.github.io/gef&amp;sa=D&amp;source=editors&amp;ust=1699590511376593&amp;usg=AOvVaw13AitU_j1Cy892FsU4pcX7">https://hugsy.github.io/gef</a></span></li></ul><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c45">Instant Setup - WHAT WORKED FOR ME IS FROM INSIDE GDB, SCROLL DOWN...:</span></p><p class="c4"><span class="c2">Simply make sure you have GDB 8.0 or higher compiled with Python3.6+ bindings, then:</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c2"># via the install script</span></p><p class="c4"><span class="c2">## using curl</span></p><p class="c4"><span class="c2">$ bash -c &quot;$(curl -fsSL </span><span class="c2"><a class="c6" href="https://www.google.com/url?q=https://gef.blah.cat/sh&amp;sa=D&amp;source=editors&amp;ust=1699590511377684&amp;usg=AOvVaw1AaWCLTlUKYmI62sEUT9Vs">https://gef.blah.cat/sh</a></span><span class="c2">)&quot;</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c2">## using wget</span></p><p class="c4"><span class="c2">$ bash -c &quot;$(wget </span><span class="c2"><a class="c6" href="https://www.google.com/url?q=https://gef.blah.cat/sh&amp;sa=D&amp;source=editors&amp;ust=1699590511378109&amp;usg=AOvVaw0dIBwT-GdeP2TZUV8dYAJZ">https://gef.blah.cat/sh</a></span><span class="c2">&nbsp;-O -)&quot;</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c2"># or manually</span></p><p class="c4"><span class="c2">$ wget -O ~/.gdbinit-gef.py -q </span><span class="c2"><a class="c6" href="https://www.google.com/url?q=https://gef.blah.cat/py&amp;sa=D&amp;source=editors&amp;ust=1699590511378548&amp;usg=AOvVaw0fg1AWc7-Lbxge6dg-eG1k">https://gef.blah.cat/py</a></span></p><p class="c4"><span class="c2">$ echo source ~/.gdbinit-gef.py &gt;&gt; ~/.gdbinit</span></p><p class="c3"><span class="c2 c36"></span></p><p class="c4"><span class="c9"># or alternatively from inside gdb directly</span></p><p class="c4"><span class="c2">$ gdb -q</span></p><p class="c4"><span class="c2">(gdb) </span><span class="c34">pi import urllib.request as u, tempfile as t; g=t.NamedTemporaryFile(suffix=&#39;-gef.py&#39;); open(g.name, &#39;wb+&#39;).write(u.urlopen(&#39;https://tinyurl.com/gef-main&#39;).read()); gdb.execute(&#39;source %s&#39; % g.name)</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 710.00px; height: 90.20px;"><img alt="" src="images/image36.png" style="width: 710.00px; height: 90.20px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span class="c2">Note: to fetch the latest of GEF (i.e. from the dev branch), simply replace in the URL to </span><span class="c2"><a class="c6" href="https://www.google.com/url?q=https://gef.blah.cat/dev&amp;sa=D&amp;source=editors&amp;ust=1699590511379665&amp;usg=AOvVaw3p3JAISluy-mk4RejpIWIB">https://gef.blah.cat/dev</a></span><span class="c2">. &nbsp;</span><span class="c9">--&gt; This is the one I used, however I modified the script just a bit as the given TinyURL was no longer working, but I believe the documentation is now updated.:</span></p><p class="c3"><span class="c9"></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 624.00px; height: 80.60px;"><img alt="" src="images/image38.png" style="width: 624.00px; height: 80.60px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 432.00px; height: 142.00px;"><img alt="" src="images/image40.png" style="width: 432.00px; height: 142.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3"><span class="c2"></span></p><p class="c4 c5"><span class="c9">Step 1. Make sure you are root, or at least use sudo.</span></p><p class="c3 c5"><span class="c9"></span></p><p class="c4 c5"><span class="c9">Step 2. Type gdb ./vuln (name of executable)</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 604.60px; height: 296.00px;"><img alt="" src="images/image42.png" style="width: 604.60px; height: 296.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c9"></span></p><p class="c4 c5"><span class="c9">Step 3: Launch gef</span></p><p class="c3 c5"><span class="c1"></span></p><p class="c4 c5"><span class="c2">pi import urllib.request as u, tempfile as t; g=t.NamedTemporaryFile(suffix=&#39;-gef.py&#39;); open(g.name, &#39;wb+&#39;).write(u.urlopen(&#39;https://tinyurl.com/gef-main&#39;).read()); gdb.execute(&#39;source %s&#39; % g.name)</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c9">Step 4: Set a break at &ldquo;Main&rdquo; and run the program, within gef</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 710.00px; height: 636.07px;"><img alt="" src="images/image44.png" style="width: 710.00px; height: 636.07px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4 c5"><span class="c9">Step 5: Now we can use grep inside of gdb for things like the following</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 621.67px; height: 351.00px;"><img alt="" src="images/image46.png" style="width: 621.67px; height: 351.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></li></ul>



</li>
</ul>
<ul>
  <li><B>PLT vs. GOT:</B></li>

<p class="c4 c5"><span class="c9">PLT stands for Procedure Linkage Table </span><span class="c2">which is, put simply, used to call external procedures/functions whose address isn&#39;t known in the time of linking, and is left to be resolved by the dynamic linker at run time.</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c9">GOT stands for Global Offsets Table</span><span class="c2">&nbsp;and is similarly used to resolve addresses. Both PLT and GOT and other relocation information is explained in greater length in this article.</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">Also, Ian Lance Taylor, the author of GOLD has put up an article series on his blog which is totally worth reading (twenty parts!): entry point here &quot;Linkers part 1&quot;.</span></p>

<ul class="c8 lst-kix_list_18-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://reverseengineering.stackexchange.com/questions/1992/what-is-plt-got&amp;sa=D&amp;source=editors&amp;ust=1699590511382697&amp;usg=AOvVaw0bao83JdurDx5pCN2tGTG4">https://reverseengineering.stackexchange.com/questions/1992/what-is-plt-got</a></span></li><li class="c0 c5 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://systemoverlord.com/2017/03/19/got-and-plt-for-pwning.html&amp;sa=D&amp;source=editors&amp;ust=1699590511383100&amp;usg=AOvVaw318zJP1jA8Nrxi6RYqS_DK">https://systemoverlord.com/2017/03/19/got-and-plt-for-pwning.html</a></span></li><li class="c0 c5 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.technovelty.org/linux/plt-and-got-the-key-to-code-sharing-and-dynamic-libraries.html&amp;sa=D&amp;source=editors&amp;ust=1699590511383482&amp;usg=AOvVaw32XtD_mS1cf7PuWxxbrHOj">https://www.technovelty.org/linux/plt-and-got-the-key-to-code-sharing-and-dynamic-libraries.html</a></span></li><li class="c0 c5 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.airs.com/blog/archives/38&amp;sa=D&amp;source=editors&amp;ust=1699590511383954&amp;usg=AOvVaw0fn3WNqchJBTvgYN63PDXG">https://www.airs.com/blog/archives/38</a></span></li></ul><p class="c3 c5"><span class="c9"></span></p><p class="c4 c5"><span class="c14">Possible Alternative Steps:</span></p><p class="c3 c5"><span class="c9"></span></p><p class="c4"><span class="c9">Step 2. Type gdb -q - ENTER:</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 345.73px; height: 83.07px;"><img alt="" src="images/image47.png" style="width: 345.73px; height: 83.07px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c9"></span></p><p class="c4 c5"><span class="c9">Step 3. Before you can run gef against your executable, you&#39;ll need to launch your program inside of gdb first:</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 377.00px; height: 55.80px;"><img alt="" src="images/image49.png" style="width: 377.00px; height: 55.80px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 709.93px; height: 95.80px;"><img alt="" src="images/image93.png" style="width: 709.93px; height: 95.80px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span class="c9">Step4: From within GDB, I typed the following:</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 711.67px; height: 517.47px;"><img alt="" src="images/image95.png" style="width: 711.67px; height: 517.47px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 709.00px; height: 638.07px;"><img alt="" src="images/image97.png" style="width: 709.00px; height: 638.07px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></li></ul>




</li>
</ul>
<ul>
  <li><B>msf-pattern_create command (Buffer Overflow/Segmentation Fault):</B></li>

<p class="c4"><span class="c2">Generates a unique pattern of characters so that if you want to refer back to where the segmentation fault happened, you can search that due to the text having unique characters.</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 713.33px; height: 433.00px;"><img alt="" src="images/image99.png" style="width: 713.33px; height: 433.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></li></ul>




</li>
</ul>
<ul>
  <li><B>gef pattern create command (Buffer Overflow/Segmentation Fault):</B></li>

<p class="c4"><span class="c2">We can also create a pattern from within &quot;gef&quot;.</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 682.00px; height: 208.00px;"><img alt="" src="images/image101.png" style="width: 682.00px; height: 208.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 689.00px; height: 387.00px;"><img alt="" src="images/image103.png" style="width: 689.00px; height: 387.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_21-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://gef-legacy.readthedocs.io/en/latest/commands/pattern&amp;sa=D&amp;source=editors&amp;ust=1699590511386521&amp;usg=AOvVaw2ZZrZlpEs55F7vb6Qxf2y8">https://gef-legacy.readthedocs.io/en/latest/commands/pattern</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://hugsy.github.io/gef/commands/pattern/%23pattern-create&amp;sa=D&amp;source=editors&amp;ust=1699590511387057&amp;usg=AOvVaw11iHVC6scoSBLcN0rptm0v">https://hugsy.github.io/gef/commands/pattern/#pattern-create</a></span></li></ul><p class="c3"><span class="c2"></span></li></ul>





</li>
</ul>
<ul>
  <li><B>checksec Command Helps Identify Security Properties and Vulnerabilities:</B></li>

<ul class="c8 lst-kix_list_22-0 start"><li class="c0 li-bullet-0"><span class="c2">Must be root, then type: checksec --file=vuln (in this example, vuln is the name of the file we wish to check)</span></li></ul><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c2">&#9492;&#9472;# checksec --file=vuln</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c9">Example1:</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 714.00px; height: 46.13px;"><img alt="" src="images/image105.png" style="width: 714.00px; height: 46.13px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span class="c9">Example2:</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 711.93px; height: 72.20px;"><img alt="" src="images/image107.png" style="width: 711.93px; height: 72.20px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_23-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://opensource.com/article/21/6/linux-checksec&amp;sa=D&amp;source=editors&amp;ust=1699590511388628&amp;usg=AOvVaw1BrF4ZbSjc8sWMKZS4KUZ_">https://opensource.com/article/21/6/linux-checksec</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.systutorials.com/docs/linux/man/7-checksec&amp;sa=D&amp;source=editors&amp;ust=1699590511389118&amp;usg=AOvVaw1YjXZpGNZTVpNHDRxXbL0h">https://www.systutorials.com/docs/linux/man/7-checksec</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/slimm609/checksec.sh/blob/main/docs/index.md&amp;sa=D&amp;source=editors&amp;ust=1699590511389641&amp;usg=AOvVaw12rOn3mj2XieyTTkJwOOki">https://github.com/slimm609/checksec.sh/blob/main/docs/index.md</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://docs.pwntools.com/en/stable/commandline.html%23pwn-checksec&amp;sa=D&amp;source=editors&amp;ust=1699590511390142&amp;usg=AOvVaw3-eRZkLatYbqxYHzFYzuGl">https://docs.pwntools.com/en/stable/commandline.html#pwn-checksec</a></span></li></ul>




</li>
</ul>
<ul>
  <li><B>pwntools has a similar function:</B></li>

<ul class="c8 lst-kix_list_24-0 start"><li class="c15 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://docs.pwntools.com/&amp;sa=D&amp;source=editors&amp;ust=1699590511390675&amp;usg=AOvVaw3lFoWo10yUVGGmHacU8e07">https://docs.pwntools.com</a></span></li></ul><p class="c4"><span class="c2">------</span></p><p class="c4"><span class="c2">#!/usr/bin/env python3</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c2">import argparse</span></p><p class="c4"><span class="c2">import pwn</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c2">elf = pwn.ELF(&quot;./vuln&quot;)</span></p><p class="c4"><span class="c2">print(hex(elf.symbols[&quot;win&quot;]))</span></p><p class="c4"><span class="c2">------</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 276.00px; height: 213.00px;"><img alt="" src="images/image108.png" style="width: 276.00px; height: 213.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3"><span class="c2"></span></li></ul>





</li>
</ul>
<ul>
  <li><B>ROPgadget:</B></li>

<p class="c4"><span class="c2">&ldquo;ROPgadget comes installed with PWN Tools, so if you have those installed, you should just be able to run ROPgadget. &nbsp;This will list out all of the potential locations in the binary, based off their address, that will do different, particular things.&rdquo; -John Hammond</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c2">Type: ROPgadget --binary vuln</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 656.47px; height: 279.00px;"><img alt="" src="images/image109.png" style="width: 656.47px; height: 279.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span class="c2">&lt;snipped&gt;</span></p><p class="c4"><span class="c2">Unique gadgets found: 32,148</span></p>

<p class="c4"><span class="c2">Because there were so many results, we reran ROPgadget and piped the results to a text file for easier searching:</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 342.00px; height: 96.00px;"><img alt="" src="images/image91.png" style="width: 342.00px; height: 96.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p>

<ul class="c8 lst-kix_list_27-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/JonathanSalwan/ROPgadget&amp;sa=D&amp;source=editors&amp;ust=1699590511393645&amp;usg=AOvVaw3f7LOlLunCUs5D3HALZDLB">https://github.com/JonathanSalwan/ROPgadget</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=http://shell-storm.org/project/ROPgadget&amp;sa=D&amp;source=editors&amp;ust=1699590511394127&amp;usg=AOvVaw3dHO4jL0t1PMGgRbmdoosI">http://shell-storm.org/project/ROPgadget</a></span></li></ul>





</li>
</ul>
<ul>
  <li><B>STrace:</B></li>

<ul class="c8 lst-kix_list_25-0"><li class="c0 li-bullet-0"><span class="c9">The strace command displays the system calls when a command is executed. You specify the command and its arguments following strace. The system calls and their arguments and returned values are displayed on standard error output.</span></p><p class="c3"><span class="c20"></span></p><p class="c4"><span class="c23">Note: By default, STrace will only spit out 32 characters, but if your output is getting cut off, you can extend that by customizing how many characters you want to push out, see examples below:</span></p><p class="c3"><span class="c23"></span></p><p class="c4"><span class="c23">This was the output of a partial CTF flag with default STrace settings:</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 536.80px; height: 161.60px;"><img alt="" src="images/image75.jpg" style="width: 536.80px; height: 161.60px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3"><span class="c23"></span></p><p class="c4"><span class="c23">This was the output of the full CTF flag once I customized my STrace output settings:</span></p><p class="c3"><span class="c23"></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 704.07px; height: 542.73px;"><img alt="" src="images/image77.jpg" style="width: 704.07px; height: 542.73px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></li></ul>






</li>
</ul>
<ul>
  <li><B>LTrace:</B></li>

<ul class="c8 lst-kix_list_28-0 start"><li class="c0 li-bullet-0"><span class="c9">Just as strace displays system calls, ltrace displays the functions, arguments, and results of the executed command in the standard error output. ltrace does not reveal from which libraries functions are called.</span></li></ul>




</li>
</ul>
<ul>
  <li><B>ObjDump:</B></li>

<ul class="c8 lst-kix_list_29-0 start"><li class="c0 li-bullet-0"><span class="c9">ObjDump is a command-line program for displaying various information about object files on Unix-like operating systems. For instance, it can be used as a disassembler to view an executable in assembly form.</span></li></ul>
<BR>
<ul class="c8 lst-kix_list_83-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://en.wikipedia.org/wiki/Objdump&amp;sa=D&amp;source=editors&amp;ust=1699590511395469&amp;usg=AOvVaw2TH6QXDfUUba_pbNJVA4Ji">https://en.wikipedia.org/wiki/Objdump</a></span></li><li class="c0 li-bullet-0"><span class="c13"><a class="c6" href="https://www.google.com/url?q=https://www.matteomalvica.com/minutes/binary_analysis&amp;sa=D&amp;source=editors&amp;ust=1699590511395830&amp;usg=AOvVaw1IbvvmOQGGSNWXG7sLX_0q">https://www.matteomalvica.com/minutes/binary_analysis</a></span></li></ul><p class="c3"><span class="c2"></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 711.93px; height: 221.00px;"><img alt="" src="images/image79.png" style="width: 711.93px; height: 221.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></li></ul>





</li>
</ul>
<ul>
  <li><B>ObjCopy:</B></li>

<ul class="c8 lst-kix_list_29-0"><li class="c0 li-bullet-0"><span class="c9">The GNU objcopy utility copies the contents of an object file to another. objcopy uses the GNU BFD Library to read and write the object files. It can write the destination object file in a format different from that of the source object file.</span></p><ul class="c8 lst-kix_list_31-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.oreilly.com/library/view/linux-in-a/0596004826/re308.html&amp;sa=D&amp;source=editors&amp;ust=1699590511396457&amp;usg=AOvVaw3XKjaHUrWKzUIwd5ymYlme">https://www.oreilly.com/library/view/linux-in-a/0596004826/re308.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://sourceware.org/binutils/docs/https:/www.oreilly.com/library/view/linux-in-a/0596004826/re308.htmlbinutils/objcopy.html&amp;sa=D&amp;source=editors&amp;ust=1699590511396899&amp;usg=AOvVaw0R34FfArWPrrCHE4404V8H">https://sourceware.org/binutils/docs/https://www.oreilly.com/library/view/linux-in-a/0596004826/re308.htmlbinutils/objcopy.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://en.wikipedia.org/wiki/GNU_Binutils&amp;sa=D&amp;source=editors&amp;ust=1699590511397225&amp;usg=AOvVaw3Nw5sILa9M_8k2eS-enpuC">https://en.wikipedia.org/wiki/GNU_Binutils</a></span></li></ul>




</ul>
  </ul>
</details>
<details>
<summary>[Network Discovery]</summary>
<ul>
 <li><B>Nmap:</B></li>

<ul class="c8 lst-kix_list_51-0 start"><li class="c0 li-bullet-0"><span class="c9">CompariTech Nmap CheatSheet:</span></li></ul><p class="c3"><span class="c9"></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 421.40px; height: 535.13px;"><img alt="" src="images/image134.jpg" style="width: 421.40px; height: 535.13px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></li></ul>


<ul>
<p class="c3"><span class="c1"></span></p><ul class="c8 lst-kix_list_52-0 start"><li class="c0 li-bullet-0"><span class="c2 c22">Here's a quick initial scan which pipes the output to a file called &ldquo;scan.initial&rdquo;:</span></li></ul><p class="c4 c5"><span class="c2">Sudo nmap -sV -sC -oN scan.initial 10.10.147.28</span></p><p class="c3"><span class="c1"></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 705.40px; height: 226.33px;"><img alt="" src="images/image135.jpg" style="width: 705.40px; height: 226.33px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3"><span class="c1"></span></p><ul class="c8 lst-kix_list_53-0 start"><li class="c0 li-bullet-0"><span class="c2 c22">Here's another initial scan example which pipes the output to a file called &ldquo;scan.initial&rdquo; - this one took quite a bit longer to finish.</span></li></ul><p class="c4 c5"><span class="c2">Sudo nmap -A -oN scan.initial 10.10.20.194</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 706.00px; height: 613.33px;"><img alt="" src="images/image136.jpg" style="width: 706.00px; height: 613.33px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_54-0 start"><li class="c0 c5 li-bullet-0"><span class="c2 c22">Here&rsquo;s an example that we can run on a port that we know is open, so here we know port 80 is open, and we can pipe those results to a file called scan.initial:</span></li></ul><p class="c4 c5"><span class="c2 c22">nmap -A -p 80 10.10.129.65 -oN scan.initial</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 480.00px; height: 56.00px;"><img alt="" src="images/image120.jpg" style="width: 480.00px; height: 56.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3 c5"><span class="c2"></span></p><ul class="c8 lst-kix_list_55-0 start"><li class="c0 li-bullet-0"><span class="c2 c22">One more example here which pipes the output to a file called &ldquo;scan.initial&rdquo; I've heard this called "a classic IppSec scan" since he often begins with this scan:</span></li></ul><p class="c4"><span class="c2">nmap -sV -sC -oN scan.initial 10.10.73.1</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 685.53px; height: 357.07px;"><img alt="" src="images/image121.jpg" style="width: 685.53px; height: 357.07px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span class="c2 c22">For all of us IppSec fans out there, this is also a common IppSec scan:</span></p><p class="c4"><span class="c2 c22">nmap -sC -sV -oA nmapScan1 10.10.10.5</span></p><p class="c4"><span class="c2 c22">-The sC is for safe scripts or the most common scripts, sV is for &quot;Enumerate Versions&quot;, and oA is for &quot;Output All Formats&quot;, and then we call the file &ldquo;NmapScan1&rdquo;.</span></p><ul class="c8 lst-kix_list_56-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://nmap.org/book/nse-usage.html&amp;sa=D&amp;source=editors&amp;ust=1699590511440516&amp;usg=AOvVaw3yh9bk39egvyuMrc3xu-9K">https://nmap.org/book/nse-usage.html</a></span></li><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://www.youtube.com/watch?v%3D2LNyAbroZUk%26ab_channel%3DIppSec&amp;sa=D&amp;source=editors&amp;ust=1699590511440935&amp;usg=AOvVaw2oF1RRx3ejMktAxMoQJ3yS">https://www.youtube.com/watch?v=2LNyAbroZUk&amp;ab_channel=IppSec</a></span></li></ul><p class="c3"><span class="c2"></span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 480.00px; height: 333.00px;"><img alt="" src="images/image123.png" style="width: 480.00px; height: 333.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span class="c2">sudo nmap -F -sV 10.10.11.143</span></p><p class="c4"><span class="c2">sudo nmap -v -sC -sV -oA nm nmap/PlayerTwo 10.10.11.143</span></p><p class="c4"><span class="c2">Sudo nmap -sS -A -sC -sV -p- -T 410.10.11.143</span></p><p class="c3"><span class="c2"></span></p><p class="c4"><span class="c2">-sC for default enumeration scripts</span></p><p class="c4"><span class="c2">-sV for enumerating versions</span></p><p class="c4"><span class="c2">-F for a Fast Scan</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 300.00px; height: 42.00px;"><img alt="" src="images/image125.png" style="width: 300.00px; height: 42.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3"><span class="c2"></span></p><ul class="c8 lst-kix_list_57-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Nmap Port Scan:</span></li></ul><p class="c4"><span class="c2">-p0- asks Nmap to scan every possible TCP port, -v asks Nmap to be verbose about it, -A enables aggressive tests such as remote OS detection, service/version detection, and the Nmap Scripting Engine (NSE). Finally, -T4 enables a more aggressive timing policy to speed up the scan.</span></p><p class="c3 c5"><span class="c2"></span></p><p class="c4 c5"><span class="c2">Example: nmap -p0- -v -A -T4 scanme.nmap.org</span></p><ul class="c8 lst-kix_list_58-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://nmap.org/book/port-scanning-tutorial.html&amp;sa=D&amp;source=editors&amp;ust=1699590511442202&amp;usg=AOvVaw3Ils4avcr2GqOvfDO0VoTf">https://nmap.org/book/port-scanning-tutorial.html</a></span></li></ul><p class="c3"><span class="c2"></span></p><ul class="c8 lst-kix_list_59-0 start"><li class="c0 c5 li-bullet-0"><span class="c9">Nmap w/ Service enumeration on all ports:</span></li></ul><p class="c4 c5"><span class="c12">nmap -p- -sV target_ip</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 710.00px; height: 217.47px;"><img alt="" src="images/image127.png" style="width: 710.00px; height: 217.47px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_57-0"><li class="c0 c5 li-bullet-0"><span class="c9">Nmap Version Detection Scan:</span></li></ul><p class="c4 c5"><span class="c2">-sV (Version detection). &nbsp;Alternatively, you can use -A, which enables version detection among other things.</span></p><ul class="c8 lst-kix_list_60-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://nmap.org/book/man-version-detection.html&amp;sa=D&amp;source=editors&amp;ust=1699590511442967&amp;usg=AOvVaw0p-_IJpk4FXWBFsQgQYoDB">https://nmap.org/book/man-version-detection.html</a></span></li></ul><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 297.00px; height: 48.00px;"><img alt="" src="images/image128.jpg" style="width: 297.00px; height: 48.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3"><span class="c2"></span></p><ul class="c8 lst-kix_list_59-0"><li class="c0 c5 li-bullet-0"><span class="c9">Nmap Full Scan on all ports w/ -oA FullScan which pipes our output to a file called &ldquo;FullScan&rdquo;:</span></li></ul><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 435.00px; height: 41.00px;"><img alt="" src="images/image130.jpg" style="width: 435.00px; height: 41.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c4"><span class="c2">&#9492;&#9472;# nmap -sVC -T4 -Pn -p- 10.129.136.188 -oA FullScan</span></p><p class="c3"><span class="c2"></span></p><ul class="c8 lst-kix_list_57-0"><li class="c0 c5 li-bullet-0"><span class="c9">Nmap Syn Scan:</span></li></ul><p class="c4 c5"><span class="c2">nmap -sS</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 297.00px; height: 40.00px;"><img alt="" src="images/image113.png" style="width: 297.00px; height: 40.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><ul class="c8 lst-kix_list_61-0 start"><li class="c0 li-bullet-0"><span class="c9">Nmap Ping Scan</span><span class="c2">:</span></li></ul><p class="c4"><span class="c2">nmap -sn 10.10.89.196</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 294.00px; height: 47.00px;"><img alt="" src="images/image115.png" style="width: 294.00px; height: 47.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></p><p class="c3"><span class="c2"></span></p><ul class="c8 lst-kix_list_62-0 start"><li class="c0 li-bullet-0"><span class="c9">Nmap Version Enumeration Scan:</span></li></ul><p class="c4"><span class="c2">nmap -sV 10.10.89.196</span></p></span></li></ul>



</li>
</ul>
<ul>
  <li><B>MasScan</B></li>
<ul class="c8 lst-kix_list_63-0 start"><li class="c0 li-bullet-0"><span class="c11"><a class="c6" href="https://www.google.com/url?q=https://github.com/robertdavidgraham/masscan&amp;sa=D&amp;source=editors&amp;ust=1699590511444638&amp;usg=AOvVaw2aVMSMXkGxmgsBEN29qsks">https://github.com/robertdavidgraham/masscan</a></span></li></ul><p class="c3"><span class="c2"></span></p><ul class="c8 lst-kix_list_64-0 start"><li class="c0 li-bullet-0"><span class="c2">MasScan is incredibly powerful and quick but it can break things, for example be careful scanning ICS.</span></li></ul><p class="c4"><span class="c2">masscan -p1-65535 10.10.129.65 --rate=1000 -e tun0</span></p><p class="c4"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 446.00px; height: 38.00px;"><img alt="" src="images/image118.jpg" style="width: 446.00px; height: 38.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></li></ul>




</li>
</ul>
<ul>
<li><B>SMBmap</B></li>
<p class="c4"><span class="c2">smbmap -u ubuntu -p S@nta2022 -d workgroup -H 10.10.112.67</span></p><p class="c4 c5"><span style="overflow: hidden; display: inline-block; margin: 0.00px 0.00px; border: 0.00px solid #000000; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px); width: 480.00px; height: 57.00px;"><img alt="" src="images/image175.png" style="width: 480.00px; height: 57.00px; margin-left: 0.00px; margin-top: 0.00px; transform: rotate(0.00rad) translateZ(0px); -webkit-transform: rotate(0.00rad) translateZ(0px);" title=""></span></li></ul>














</ul>
  </ul>
</details>












</body>
</html>



