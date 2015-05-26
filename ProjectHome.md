Simply Put, Tesseract takes awhile to teach new languages, and this will assist line by line so you dont have to. The program is provided compiled on the downloads page for those of you who dont feel like messing with autoit, but read the directions below.
Once compiled or downloaded
```
1.Save the original document as tesseract.txt in RTF-8 format
2.Place the Compiled file from downloads in the same directory
3.Open your box file
4.Run program(follow message box directions)
5.Program stops only when finished or the autoit icon in the system tray is right clicked.
 I cannot imagine the havoc getting 30 different characters sent to the wrong screen would
 cause... So Dont try to stop it any other way.
```

```
;save all text as a text file, go download autoit3 from http://www.autoitscript.com/site/autoit/ then compile this text file you made and read below.
;disclaimer, as is, easy to fuck up, designed for people who know what the are doing. ; are comment lines
;put compiled file in the same directory as the tesseract.txt file that you will make from your font, look at line 5 for more instructions
$msg=FileRead(@ScriptDir&"\tesseract.txt")
;line 5: save a copy of your font as tesseract.txt in RTF-8 Format
$msg1=StringStripWS ( $msg, 8 )
;removes blank spaces and carriage returns
$boundaries=StringLen($msg1)
;figures out how characters are in the file after removing White Space
$pos=0
;Sets the variable initial value
MsgBox(4096,"Warning","After Pressing OK you will have 20 seconds to position your insert point at the first line of the box file")
;gives you a warning and time to open the text file, when this file starts, it dosent stop until its done
;UNLESS you right click the Blue Circle A icon in the system tray(pauses and opens up a context menu) then press exit
Sleep(20000)
;time in miliseconds
Do
	;sets a loop that will repeat until every character is read
	$pos=$pos+1
	;increments the loop by one each time
$msg2=StringMid($msg1,$pos,1)
;reads the character at the position
;send("{delete}")
Send($msg2,1)
send("{down}{left}")
;removes current character
;sends the proper character
;positions to the next line
Until $pos=$boundaries
;the exit of the loop

```