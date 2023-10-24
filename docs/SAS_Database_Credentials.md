SAS has the ability to connect to data sources stored in various
relational database backends. To connect to these databases, appropriate
database credentials are needed.

## Libname Statements

Connections to remote data sources (to a relational database) will still
use a libname statement, as would be the case with a local data source
(SAS files). Ideally, libname statements should be kept in separate
files and those files should be shared among all users, as we all tend
to share data sources. These libname statements will be stored in
**/share/libnames/** on the data server. An libname file will appear as
the sample below:

    %include '~/.sas/credentials.sas';

    libname lgc postgres server='192.17.36.20' port=5432 user=&usr
    password=&pwd database='DBName' schema='dbo'
    conopts="sslmode=require";

    %let usr=;
    %let pwd=;

The first line "include" line calls a credentials file that should be
housed in your local folder. That file will be discussed later. Next
comes the libname statement. The notable parts of this are the "user="
and the "password=" arguments. These arguments will use variables to
retrieve your user credentials when the libname statement is run.
Finally, we have the last two lines of this fill which clears the
information in those variables (your NetID username and password) from
memory.

## Credentials file

The file which will hold your database credentials will be stored in the
".sas" hidden directory in your user's home directory, and will be named
"credentials.sas" (as in, /home/<user>/.sas/credentials.sas). This file
will appear as the sample below:

    %let usr=Joe;
    %let pwd=joespassword;

While this file containing your credentials should be stored in your
home directory there is still the problem of having your NetID password
stored in plain text. This is where we implement SAS' "pwencode" proc to
obfuscate your password.

### Obfuscating stuff

SAS can encode (encrypt) text which will be readable by SAS but not
easily decoded. An example of how we could use this for our passwords to
avoid storing them in plain text is as follows:

    proc pwencode in="yourpassword";
    run;

After running the above code once, look in the SAS log for the encoded
password. It will look something like
"{SAS002}718373011A8AC53B451D8A0B124B051F". Now take the encoded
password and use it in place of your plain text password in your
credentials file:

    %let pwd="{SAS002}718373011A8AC53B451D8A0B124B051F";

This will add a little more security to your credential storage.

[Category:Data](Category:Data "wikilink")
[Category:SAS](Category:SAS "wikilink")