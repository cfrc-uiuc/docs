<h1>

Programs for Online Visualization Tool

</h1>
<h2>

Procedure for Updating the Data Table

</h2>
<h3>

With SAS

</h3>
<h4>

Shufen's Part

</h4>

Run the following three program files in the following sequence in order
to create table malt2014profile.

**Sib_fambased.sas**
The program file creates number of siblings and number of wards for
family based care and creates the data table, sib_fambased which was
saved in mpublic schema.

**Predictor.sas**
The program file creates predictor variables, such as case open reason,
time in care, number of prior indicated reports, prior allegation types,
number of spells, child race, child age, child disability, region, case
worker education. The data table ag17_sib was generated after running
the program and it included the variables listed above.

**Profile.sas**
The program file includes three parts. The first part adds a few more
predictor variables, such as prior congregate care, permanency goal of
returning home. The second part adds outcome, and caseworker-related
variables. The third part adds maltreatment profile-related variables,
such as allegation type, perpetrator, and reporter, and data were
restructured to make the unit of analysis at the report level.

**ind1d_maltincare_placementx2.sas**
The program creates the data file mpublic.ind1dmaltrpts. The numbers of
maltreatment reports in the file should match the website numbers for
ind1d.

**chrtdata.sas**
The program file joins the data file produced from profile.sas program
with ind1d data table and generates the final table for dashboard. The
two long tables related to allegation types and perpetrator groups are
also generated in the chrtdata.sas.

<h4>

Martin's Part

</h4>

**Alternative for running DASHBOARD data update early -Programs will
need to be run with data downloaded a month before the end of the
quarter except for *ind1d_maltreats.sas* and *chartprofiler.sas* which
should be run as soon as the quarter ends.**

The programs for the maltreatment in care dashboard online visualization
tool

The early downloads, etc need to be run on the vm06 server which, at
this point, is the only one setup to connect to the dcfs database from
within SAS. In other words I do all the early downloads from sas. I have
started to run all of the programs on the vm06 server.

**early_download.sas**: Needs connection to the dcfs vpn and dcfs
database server. Saves everything that is downloaded to the metabase
public schema known as mpublic. I think it is cleanish so it should run
completely once you add the credentials. Running this program takes a
while (hours) because it is downloading a bunch of tables, some that are
really big. And because it is sas. Create early version of the
providernoid data file: This step involves two programs:
prov_direct_read.sas which reads the provider information into a
temporary file and

**prvlicadd_cryp.sas** which uses the temporary file created by the
first program and applies the conversion into providernoid.sas7bdat data
file. These programs are not in the repository at the moment and I am
not sure that they should be so Aaron will need to access my home
directory. The programs are in /home/m-nieto/provs/. The
**prov_direct_read.sas** needs be run first with dcfs vpn connected and
then the **prvlicadd_cyp.sas** should be run, both need to be run during
the same sas session so nothing with identifiers gets save on the
server. Make sure that the %lib(mbase) as active in order for the file
to be save to mpublic.

**lgc_regionfile.sas**: in the dashexp folder also needs to be run early
while the dcfs-vpn connection is in placed. The information in the file
is used for the profile data table.

If the above programs run properly the rest should not need dcfs-vpn
connection any more.

**Earlyplace.sas**: Creates early version of master event to be save in
mpublic.

**sib_fambasedr.sas**: Creates sib_fambase data file with sibling/ward
count at start of placement.

**Predictor_rpt.sas**: Run this file to create the big file with all
placements with predictors for the observation period.

**malt2014.sas**: This program creates the data file malt2014r which
should include all maltreatment reports with dates during a placement
for the overall observation period. It includes all reports regardless
of finding which it is used to link the worker contacts just prior to
the date of the report and worker caseload at the start of the
placement.

**sam_cntc_chwkrag16r.sas**: Takes the malt2014r data file created by
the preceding program and adds the raw contacts between the child and
case worker. It includes both contact recorded under the child’s case
and the family case.

**sam_cntc_ag16parproviderr.sas**: Takes the malt2014r data file created
by the preceding program and adds the raw contacts between the caregiver
and case worker. It includes both contact recorded under the child’s
case and the family case.

**chcase_famc_ag16r.sas**: Creates the contact variables for the
contacts between the child-case worker selecting the last contact in the
previous 30 days before the maltreatment report or end of placement.
Again it takes the contact recorded under the child case as well as the
contacts recorded under the family case.

**chcase_wkrfpc_ag16r.sas**: Creates the contact variables for the
contacts between the caregiver-case worker selecting the last contact in
the previous 30 days before the maltreatment report or end of placement.
Again it takes the contact recorded under the child case as well as the
contacts recorded under the family case.

**malt_prvlicr.sas**: Adds the license status prior to the maltreatment
report or end of event, caseload at the start of the event, and the
different contact variables into a single file. Produces the
mpublic.maltloadallr data file.

**Profiler.sas**: Run the rest of the profile program to create the
malt2014profile(a). Each time we update the dates for the corresponding
years and quarter will need to be edited unless…

<font color=red>**NEEDS TO BE RUN AS SOON AS QUARTER ENDS** with dcfs
connection if possible. </font></br> **ind1d_maltreats.sas** creates a
file with the indicated reports for the observation period following the
inclussion/exclusion criteria outlined in the cfsr indiator. Dcfs-vpn,
and dcfs data connection needed. Adjust the year trend like the
indicator programs. Update dates on line 721+-; Define some of the
latest quarter starting in line 784 to check pattern of numbers. Latest
quarter is generally lower.

<font color=red> **RUN THIS PROGRAM AT THE END.**</font></br>
**chartprofiler.sas**: It verifies that only reports that fit the cfrs
maltreatment in care criteria are counted and then creates the final
data file and load it to metabase_data.chart_data. The quarter part
needs to be updated. Change date in line 19 to reflect the end of the
last quarter to be included in the year count. On line-132 after adding
the agency name check frequencies of agency names due to misspellings or
miss-capitalized characters. Add the latest quarter to the file starting
on line-154.

<h3>

With SQL

</h3>

♦ Note - it might take 2-8 hours(?) to see the new quarter or new year
in Metabase.

<h4>

How to Update a Quarter

</h4>

We need to list 16 quarters in the dashboard (=4 quarters x 4 years). To
update a quarter, do the following:
**Edit the SQL file: \~/BH/dashexp/sql/ref_quarter_fy.sql**
1) Add a new quarter. For example,

> Insert into chart_data.quarter_ref (pk_id, q_include, quarter) values
> (31, 1, ‘2022 Q3’);

2\) Remove the oldest quarter. For example,

> Update chart_data.quarter_ref set q_include=null, quarter=null where
> quarter in (‘2018 Q3’);

<h4>

How to Update a Year

</h4>

We need to list four (fiscal) years in the dashboard. To update a year,
do the following:
**Edit the SQL file: \~/BH/dashexp/sql/ref_quarter_fy.sql**
1) Add a new year. For example,

> Insert into chart_data.year_ref (pk_id, y_include, fyear) values (7,
> 1, ‘2023’);

2\) Remove the oldest year. For example,

> Update chart_data.year_ref set y_include=null, fyear=null where fyear
> in (2018);

<h3>

With Metabase

</h3>
<h4>

How to Update a Quarter Filter

</h4>

1\) Go to <https://metabase.cfrc.illinois.edu/dcfs>.
2) Click “Child Maltreatment in Care Dashboard.”
3) Open “Quarterly-based Maltreatment in Care Dashboard” and make
changes to the “Quarter(s)” filter.
We need to list 4 quarters in the filter. Add the new quarter to the
filter and remove the old quarter from the filter (e.g., add ‘2022 Q3’
and remove ‘2018 Q3’). For more details, see
<https://mediaspace.illinois.edu/media/t/1_wx1and9s>
4) Save “Quarterly-based Maltreatment in Care Dashboard.”

<h4>

How to Update a Year Filter

</h4>

1\) Go to <https://metabase.cfrc.illinois.edu/dcfs>.
2) Click “Child Maltreatment in Care Dashboard.”
3) Open “Yearly-based Maltreatment in Care Dashboard” and make changes
to the “Fiscal year(s)” filter.
We need to list 4 years in the filter. Add the new year to the filter
and remove the old year from the filter (e.g., add ‘2023’ and remove
‘2018’). For more details, see
<https://mediaspace.illinois.edu/media/t/1_wx1and9s>
4) Save “Yearly-based Maltreatment in Care Dashboard.”

<h1>

Link to the Maltreatment in Care Dashboard

</h1>

<https://metabase.cfrc.illinois.edu/dcfs/public/dashboard/a5564ce6-51d8-44c9-b4e7-3f8026aa04f9>