For programs that do not have support for PostgreSQL directly, such as
SPSS and Stata, ODBC drivers are needed. ODBC drivers are already
installed on the SAS server. In order to connect to data sources using
the ODBC driver, you will need to configure an appropriate ".odbc.ini"
file. For your reference, a sample ".odbc.ini" file can be found at
/share/odbc.ini.

## Contents of odbc.ini

The data contained in this file is relatively simple and should be
pretty straight forward. A working configuration for the OregonDR data
can be seen below:

``` bash
[OregonDR]
Driver = PostgreSQL
Description = PostgreSQL Data Source
Servername = db1.cfrc.illinois.edu
Port = 5432
Username =
Password =
Database = OregonDR
ReadOnly = yes
Protocol = 9.4
SSLmode = require
```

bash

An odbc.ini file may contain multiple ODBC connections. The name of the
connection will appear in brackets before the connection parameters. In
this case, the connection name is "OregonDR". For the most part, all of
these configuration parameters will be provided to you. All that you
will need to change will be the "Username" and "Password" parameters,
which should match your NetID username and password.

## Location of odbc.ini

The odbc.ini file will need to be placed within the root of your home
directory as a hidden file. In Linux, a file can be turned into a hidden
file by placing a period (.) before the file name. An example path for
your odbc.ini would be:

``` bash
/home/aburn02s/.odbc.ini
```

A simple way of coping the odbc.ini file to the appropriate location in
your home directory would be to run the following command (excluding the
"\$"):

``` bash
$ cp /share/odbc.ini ~/.odbc.ini
```

You will also want to change permissions on this file accordingly:

``` bash
$ chmod 600 ~/.odbc.ini
```

From there, you could edit the file to contain your specific user
credentials. Naturally, if you do not have access to the data source
listed, access will be denied once a connection is attempted.
