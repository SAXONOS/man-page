# man-page
Sketch of a man page for "mycommand" in roff language.

troff is the perfect tool when writing on-screen documentation that will only ever be a text file. All the formatting needed for documentation gets called up as a help file from the command line. Internal documentation for configuration files or even comments and explanations within source code, can all be formatted using troff. 

TERMINAL COMMANDS:

Create a new file for your man page, mycommand.7       NOTE: 7 is allusive to "man man" guidelines, but can be any number.

>> vim mycommand.7

Write the content using the appropriate troff macros.

Save the file and exit the text editor (in nano, press CTRL+X, then Y, then Enter) (in Vim, press Ctrl+O, Enter, Ctrl+X) 

Use groff (GNU roff) to format page and view it:

>> groff -man -Tascii mycommand.7 | less

Above command tells groff to use the -man macro package and format the file for ASCII output, which is then piped to less for viewing.

If the man page is for a command created by user, it usually should go into /usr/local/share/man/

>> sudo mkdir -p /usr/local/share/man/man7

NOTE: Type "man man" and you will see that 7 corresponds to "Miscellaneous macro  packages, man(7), groff(7), man-pages(7)

ONE directory per command must be created!

>> sudo mkdir -p /usr/local/share/man/man7

Copy your roff file into new directory and remember that it is a read-only directory, the reason for the tranfer...

>> sudo cp ~/home/yourusername/mycommand.7 /usr/local/share/man/man7/

UPDATE Manual database!

>> sudo mandb

TO VIEW... Call your new command, cool?

>> man mycommand   





