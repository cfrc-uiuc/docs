SAS can be configured to run SAS programs any time SAS is loaded. This
can be useful for things like setting global variables for all programs
automatically. This has been setup on CFRC Linux workstations
(probably).

## Includes Dot SAS

A file should exist in the user's \~/.sas directory called
"includes.sas". You may edit this file to your liking. It is a good
place to assign variables when SAS loads or call other SAS programs, and
should contain a format similar to:

    %let user = &SYSUSERID;
    %let path = /home/&user/Projects/Git/CFRC/SAS;

For assigning paths to variables, please be conscious of how a trailing
slash may affect your programs in some cases.

#### Usage

The above variables could be called from a SAS program by just
referencing the variable:

    %include "&path/macros/myMacro.sas";
