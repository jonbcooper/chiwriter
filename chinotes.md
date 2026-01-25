# ChiWriter notes

The program files can be obtained from: [https://horstmann.com/ChiWriter/](https://horstmann.com/ChiWriter/) 

Install **DosBox**

If you extract all the ChiWriter files in a folder called DOS, they will go into a subdirectory called CW4. 

***

The following command should start DosBox, mount the DOS subdirectory as the windows C: drive, move to the DOS folder and start ChiWriter. Files will be saved in the DOS folder and the DOS window will exit when ChiWriter exits. 

	dosbox -c "mount c: ~/DOS" -c "c:" -c "c:\cw4\cw.exe" -c "exit"

<u>Hint</u>: Toggle Alt-enter to full-screen it. 

<u>Hint</u>: Ctrl-F10 frees the mouse if it gets stuck in the dosbox window.

<u>Hint</u>: To paste text into ChiWriter seems at first to be impossible as it does not listen to the clipboard. However, there is a way round this which works on linux and I am sure there will be a way to do the same thing on Windows, etc, but I can't test that easily. Anyway, the basis of it is to select a chunk of text e.g. from the web, by left-clicking and highlighting it and then copying it to the clipboard with the option that comes up with a right mouse click in the usual way. The copied text can then be converted to a series of key strokes for ChiWriter by executing the following terminal command: 

	xdotool sleep 3 type --delay 50 "$(xclip -o -selection clipboard)"

This command gives you 3 seconds to move the mouse into the ChiWriter window and click a few times exactly where you want the text to be inserted. I suggest clicking the top-left icon of the ChiWriter window first to say "Layer" -> "Always on top" to facilitate doing this step quickly. With a short piece of text, the "--delay 50" is not needed but with a bigger chunk, it helps the letters to arrive in the right order by putting a 50 millisecond delay between each keystroke. If you accidentally click the mouse while the clipboard text is being 'typed in', the insertion point will change and pure chaos will reign. Just delete the inserted text and start again. This method does require xdotool and xclip to be installed first, which is easily done with a package manager. 

The above command can be put into a button in your favorite file manager for easy execution when desired. 

***

<u>To get nice pdf output</u>.

Print -> Options -> select Times or Helvetica. 

Print puts ps in xx.BIN file. 

Type: ps2pdf xx.BIN xx.pdf. 

***

<u>Adding pictures</u> in ChiWriter itself seems well-dodgy so leave gaps for them and add them to the pdf with Xournal. Of the pdf editors I tested, Xournal was definitely the best, i.e. the text remains searchable and the output file is compact with figures at a good resolution. 

***

<u>Tip</u>: In the .dosbox hidden folder is a single configuration file and this can be edited to set windowresolution=840x630 and output=opengl to make the ChiWriter window bigger. Set autolock to false to stop the mouse getting stuck in the ChiWriter window. 

In the .dosbox file also change keyboardlayout to uk.

***

You can also use **dosemu** which is much quicker to start and looks better in fullscreen, but it goes a bit weird sometimes and its impossible to set up the working directory fully. 

With dosemu Ctrl-alt-F to toggle fullscreen and Ctrl-Alt-Home to grab mouse.

Also, in the file /etc/dosemu/dosemu.conf the keyboard settings need to say $_layout="uk". 

The default directory in which ChiWriter should look for the documents is set in Options -> Global e.g. use '.' for the current folder or '..' for the parent directory. 


<small>There are newer versions of DosBox (DosBox-X) and dosemu (dosemu2) which I am sure are better but they won't install easily on my ancient machine.</small> 

---


<b>Other tips and tricks</b>

<u>To get &#8491; symbol</u> enter Alt-F, Alt-X and shift-@. It is in the extended font which can be got to from View&rarr;Font chart by pressing Alt-X until it extended fonts become visible. This works in the standard, small, italics and bold fonts. 

<u>Non-expanding space</u> or tie is the t character in the symbol font i.e. F6 t will do it.  

