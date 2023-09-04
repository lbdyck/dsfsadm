# dsfsadm
Simple ISPF Dialogs to help with Administering and Using DFSFS under z/OS

This ISPF dialog makes is easy to invoke the DSFS Administration commands and the user commands.

It isn't perfect but it is a start.

## Installation:
 - If you received the package as a TSO XMIT file then
     - Do a TSO RECEIVE of the XMIT file
     - execute the $RECV member to reconstitute the EXEC and PANELS members
 - update the DSFSADM member in the EXEC PDS to reference your libaries and copy into a library in your SYSEXEC or SYSPROC allocation
   ** this is optional as it will use ALTLIB and LIBDEF to access the dialog in the recived libraries
 - OR
   Copy the EXEC PDS members into a SYSEXEC/SYSPROC library in your standard allocation
   *and*
   Copy the PANELS PDS members into a library in your ISPPLIB standard allocation

## Usage:
 - if you copied only the DSFSADM exec then:
   from a ISPF command line (or option 6) enter
      TSO %DSFSADM option
 - if you copied both received libraries then from a ISPF command line (or option 6) enter
      TSO %DSFSMENU option

  Where option is A for the admin, D for dsadm, or U for user (U is the default)

  Note: User are the dsadm commands - some user and some admin

## Notes:
    1. dsadm appropos was not implemented as it seemed redundant with help
    2. dsadm config was not implemented as it seemed too powerful
       - let the user update the config manually
    3. dsadm createparm only support fb and vb
    4. There is NO WAY to list existing createparm's

