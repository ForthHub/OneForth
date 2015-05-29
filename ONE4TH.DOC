  15Jun89

  While OneForth is basically a hack of Laxon & Perry's F83, there are 
some important differences between the two systems.  Please take close
note of the following syntax:

  10 CREATE-FILE URK.BLK creates a blank 10k file called URK.BLK.
  USE URK.BLK opens that file as the current source file.

  1 E invokes the editor at screen 1.
  <esc> <esc> exits the editor.
  <esc> <Q> from the editor exits without updating the screen.

  FROM <filename> opens a secondary source file.
       Check out screen #1 in EXTEND to see how FROM is used.
  FROM <filename> 1 6 TO 4 CONVEY moves screens 1 thru 6 from a secondary
       file to the current file, starting at screen 4.

  ' <topword> IS BOOT sets the boot vector for system startup.
  SAVE-SYSTEM <filename> saves the executable image of the current system.

  Note that OneForth's .TTP files take a filename on the command line, and
will USE that file as the current source file.  Look over the code in EXTEND
and KERNEL.BLK (particularly references to DEFAULT) to learn how to do that.

  Access to addresses outside of Forth's 16bit address space is accomplished
via the long fetch and store words LC@, LC!, L@ and L!.  These work just like
C@!, C!, @ and !, but expect 32 bit addresses.  ADD-BASE extends a local Forth
address into a 32bit address.

  The GEMDOS library is documented in the file GEMDOS.BLK.  The actual GEMDOS
code that gets compiles is in EXTEND, except for a few of the calls which you
will find in KERNEL.BLK.  The essential file words are on screens 90-92 there.
 
  Laxon & Perry's VIEW has been removed to save space in headers.  You can 
still type SEE <word> to decompile any high-level Forth word.

  Here are a few conveniences I've added to the system:
 
  HA@ and HB@ return the handles of the current and secondary source files.
  adr INC increments the value at adr.
  adr DEC decrements the value at adr.
  QX provides a quick index of the current source file.
  adr len DUMP does a dump of len bytes at adr.
  adr DU dumps 64 bytes from adr, returns with adr+64 on the stack.
  The prompt shows the stack depth. 
  DCX is a quick abbreviation for DECIMAL.
  .B prints the top of stack as binary, .H as hex.

  Laxon & Perry's VIEW word has been removed to save dictionary space.
  SEE <word> will decompile any high level Forth word.  

  To regenerate the kernel, invoke META.TTP with KERNEL.BLK on the command 
line, then type OK (which is the same as 1 LOAD).  This will create a new
KERNEL.TTP.  To regenerate the higher system, invoke KERNEL.TTP with EXTEND
on the command line.  Type OK to generate ED1FORTH.TTP, or type 15 LOAD to
generate 1FORTH.TTP.  Note that GEMDOS merrily allows duplicate filenames, 
and that SAVE-SYSTEM doesn't check for that condition.  If you write a fix
for this, please send it to me.
 
  Bob Lee (b0b)
  NiteOwl BBS - US (707)823-3052
  8pm-8am Pacific time  2400 baud
