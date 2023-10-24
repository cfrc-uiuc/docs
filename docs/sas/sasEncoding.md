## SAS and Latin1 Encoding

SAS has some difficulty working with text fields when using *UTF-8*
character encoding. With *UTF-8* encoding selected, SAS seems to pad the
text fields to the maximum allowable size. SAS comes with two executable
files - one to load SAS with *UTF-8* encoding, and another to load SAS
with *Latin1* encoding. To rectify this issue, the Virtual Machines
(cfrc-vm06 and cfrc-vm07) have been configured to run SAS with *Latin1*
encoding enabled by default.

## Notes

It is believed that using *Latin1* encoding for DCFS data does not
result in any loss of data. Additionally, PostgreSQL tables (all tables
in our PostgreSQL database use *UTF-8*) that use a *text* field type
seem to be populated normally by SAS sessions loaded with *Latin1*
encoding enabled by default.
