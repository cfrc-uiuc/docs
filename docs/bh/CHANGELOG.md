---
layout: default
title: BH Changelog
parent: BH
nav_order: 1
---

# BH Data

### FY2020 (July 2019 - June 2020)

\## **\[FY2020.Jan2020\]**

\### Changes in Indicator <b>1D</b> (Maltreatment in Substitute Care)

- Added event=19 (Armed services/other/unknown) to exclusions.
- Re-created cps_alleg table to include incident date and used that date
  when possible. If the incident date is blank or missing, then use
  report date (reptdate).

\#### Reported by Kyle.


<hr>

\## **\[FY2020.Nov2019\]**

\### Data changes in the BH indicators

- As far as the demographic characteristics are concerned, in the CPS
  part, Martin pulled the recent demographic information for the child.
  If child’s demographic information is missing in the recently reported
  data, he went back to the previous case (if exists) and used the
  demographic information.
- In case of CYCIS, this process was not carried out; the CYCIS data do
  not have the historical records.

\#### Reported by Satomi.


<hr>

\## **\[FY2020.Sept2019\]**

\### Data changes in the BH indicators

- Before we start running the next quarter BH data, which will happen
  some time in October 2019, the programmers need to make two changes to
  the SAS programming files.
  - (a) a detail table has to have an ID in each case.
  - (b) if the race is coded as missing/unknown, recode as NULL (or
  blank) and exclude from "Other" category. Note - the case where the
  race is missing will be included in overall data but will be excluded
  when reporting at the race/ethnicity breakdown.

\#### Reported by Satomi.


<hr>

\## **\[FY2020.Sept2019\]**

\### Data changes in coding schemes to demographics

- Martin made a couple changes to the SAS programming files,
  <i>cps_demogs.sas</i>. These changes of coding demographic information
  are likely to affect the following indicators: Maltreatment recurrence
  <b>(1A)</b> and maltreatment recurrence among children receiving no
  services <b>(1C)</b>.
- If the child’s demographic information is missing for the record, we
  go back to the previous report (if it exists) and use the demographic
  information for the missing part. If the child’s race is coded as
  missing (‘NULL’) or” unknown,”, code the case as missing in race. For
  this change, the “other race” will be mainly consist of three racial
  groups: AO (Asian), NA (Native American), and PI (Pacific Islanders).
  In Quarter 3, we made these changes to two indicators only, and it
  will be applied to all indicators in the next quarter (in October,
  2019).
- Martin showed us a SAS programming file (“ind1a_recur.sas”) to compare
  the differences between the quarters, and the file is available in the
  “datacheck_detailindi” branch.

\#### Reported by Satomi.


<hr>

\## **\[FY2020.Sept2019\]**

\### Data changes in race/ethnicity

- Martin coded the missing (null) cases in race/ethnicity as missing.
  Note that it used to be recorded as "Other race/ethnicity" if the
  race/ethnicity was missing previously.

\#### Reported by Satomi.


<hr>

### FY2019 (July 2018 - June 2019)

\## **\[FY2019.May2019\]**

\### Data changes in the BH Report

- Satomi excluded "missing (null)" cases from the "Other Ethnicity"
  category when she produced the child population data.

\#### Reported by Ling, C.


<hr>

\## **\[FY2019.April2019\]**

\### Data changes in the BH Report

- Use the last 15 years of data, instead of 20 years.
- Definition of race/ethnicity.

\#### Reported by Ling, C.


<hr>

\## **\[FY2019.February2019\]**

\### Issues re: "Other" ethnicity

- After we finished last year's report, we decided to use race in
  "invest_subj" which contains the most recent investigations.
- In the SACWIS, three files contain race info.
- In the last report, Martin used Race@DCFS for race and person@DCFS for
  ethnicity to create the race column in CPS table.
- In the current CPS table, Martin uses the invest_subj@DCFS since the
  file contains the most recent investigations and both race and
  ethnicity.
- The increasing number in "other ethnicity" in this year's report is
  due to missing race/ethnicity.

\#### Reported by Ling, C.


<hr>

\## **\[FY2019.February2019\]**

\### Changed - Indicator <b>3J</b> (re-entry in foster care)

-Range of years was incorrect. This year we will include from
2010-2016.

\#### Reported by Kyle, A.


<hr>

\## **\[FY2019.February2019\]**

\### Changed - Indicators for Chapter 1

-Indicators for Chapter 1 were re-run with facilities included.

\#### Reported by Kyle, A.


<hr>

\## **\[FY2019.January2019\]**

\### Changed - Investigation cases


- Kyle found the numbers of investigation was smaller before 2003 for
  the 20 year trend when he ran the report this time.
- Martin investigated and found DCFS dropped the investigation cases
  before 2003 between June and December 2018. The last DCFS data updates
  had 2.4 millions observations in investigation table; while the
  current DCFS data updates (Aaron downloaded it on January 2, 2019)
  have 1.3 millions observations.

\#### Reported by Kyle, A.


<hr>

\## **\[FY2019.January2019\]**

\### Added - Constraint/Reference tables

-Shufen added a reference table for "events."

\#### Reported by Shufen, W.


<hr>

\## **\[FY2019.December2018\]**

\### Reported - Null dates

-Two types of dates are used for the null dates: 01-01-0101 and
12-31-9999.

\#### Reported by Satomi, W.


<hr>

\## **\[FY2019.December2018\]**

\### Added - Constraint/Reference table

-A reference table for age group was created.

\#### Reported by Satomi, W.


<hr>

\## **\[FY2019.November2018\]**

\### Added - Constraint/Reference tables

-Satomi and Martin created the following constraint tables:

- Subregion
- County
- Race
- Gender
- Allegation
- Living arrangement (livarcode)


\#### Reported by Satomi, W.


<hr>

\## **\[FY2019.July2018\]**

\### Changes for the next year's BH Report

-Kyle used <b>hmr_monitor</b> for CFSR; yet, Shufen used <b>master
event</b> for BH. From the next reprot, they should use the same tables
so the number will be consistent. We need to discuss which table to
choose.

\#### Reported by Ling, C.


<hr>

### FY2018 (July 2017 - June 2018)

\## **\[FY2018.Junel2018\]**

\### Modified - Reunification

-We include all the "home of parents" and "home of adaptive parent" at
the case closed into "reunification". Previously we put them in the
"otherwise exit."

\#### Reported by Ling, C.


<hr>

\## **\[FY2018.April2018\]**

\### Modified - living with relatives

We added living with relatives as a choice for the permanency.

- There are two types of living arrangement: (a) the placement is
  kinship home when exiting from substitute care and (b) placement ended
  with home of parent (HMP), but the legal custody was relatives.
- In the previous reports, cases where a child exited to relative
  guardianship were treated as “otherwise exit.” For some cases they
  were considered as “reunification” if the child returns to the
  parent(s) and they live with relatives (or the child custody belongs
  to the relatives).

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.April2018\]**

\### Modified - family cluster ID <i>(clusid)</i>

We identified the family cluster ID differently from the previous years.

- The <i>cftvcr9100</i> table in LGC has history of <i>clusid</i> for
  each person. To identify siblings for end-of-year placement this
  method is more accurate. So we switched to use the <i>cftvcr9100</i>
  table and link it with <i>cyc_case</i> to run the indicator.
- This change affects Indicator <b>2C</b> (initial placement with
  siblings).

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.April2018\]**

\### Modified - Home of Parent (HMP)

-Old version: Excluding AA and AD. New version: Including AA and AD if
their custody is under DCFS.

\#### Reported by Ling, C.


<hr>

\## **\[FY2018.April2018\]**

\### Modified - independent living

- Independent living is excluded from Chapter 2 indicators.
- For permanency stability indicators, independent living is excluded
  when re-entry was counted.
- Note that in Indicator <b>1D</b> (maltreatment in foster care) the
  children placed in independent living are included in the base
  population.
- Previously, independent living was included in Chapter 2. Independent
  living was included in the re-entry categories in Chapter 3.




<hr>

\## **\[FY2018.April2018\]**

\### New table - <b>master_spell_legal</b>

This new table includes the legal spell information.

- Indicators <b>2B</b> (end-of-year placement) and 2D (end-of-year
  placement with siblings): For the case with HMP if the custody is in
  DCFS, it is included in the base population.
- Indicator <b>2F</b> (runaway): First legal spell was used. (If the
  spell is less than a year, use spell ending date. If the spell is more
  than a year, use open date + 365 days.)
- Indicator <b>2G</b> (median length of stay): First legal spell was
  used. We noticed for some cases that even though a child exits from
  substitute care, the legal custody is unchanged. Consequently, the
  length of stay will be longer (technically) since we are using the
  legal spell
- Indicators in Chapter 3: <i>Master_spell_legal</i> table was used
  except Indicator <b>3F</b> (Permanency stability – Guardianship).

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.April2018\]**

\### Modified - Inclusion of HMP (Home of Parent)

- HMP is considered a type of substitute care.
- This change affects:
  - Indicator <b>1D</b>(maltreatment in foster care, CFSR measure) - We
    include HMP. However, HMP with the open code 'AA'(adoption
    assistance) is not included because it was not considered as
    substitute care.
  - Indicators <b>2A</b> and <b>2C</b> (initial placement) - We include
    HMP. However, HMP with the open code 'AA'(adoption assistance) is
    not included because it is not considered as substitute care.
    Previously, we did not include HMP as an initial placement since we
    considered out-of-home care only as substitute care.
  - Indicators <b>2B</b> and <b>2D</b> (end-of-year placement) - HMP is
    included only (a) if legal custody is in DCFS and (b) their open
    code is not 'AA' or'AD.' Previously, an HMP case was not considered
    as an out-of-placement.
    </li>
  - Indicators <b>2F</b> and <b>2G</b> (run away and median length) and
    all indicators in Chapter 3 - the <i>master_spell_legal</i> table
    was used, and HMP was integrated in the table.
    </li>
  - Note: HMP is NOT included in Indicator <b>2E</b> (stability). In
    addition to HMP, the following ‘events’ are excluded from substitute
    care:
    - HMP (home of parents)
    - SGH (subsidized guardianship)
    - Deceased
    - CUS (college/university scholarship)
    - JTP (job training)
    - YIC (youth in college)
    - YIE (youth in employment
    - ASD (armed services duty)
    - PGH (private guardian home)
    - OTH
    - UNK
    - Runaway
      </li>

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.March2018\]**

\### Modified - Appendix A in BH Report

-Indicator <b>1A</b> excludes the children 17 years and older as CFSR
requires. The rest indicators exclude children 18 and older.

\#### Reported by Ling, C.


<hr>

\## **\[FY2018.March2018\]**

\### Modified - Indicators 3A/3C/3E

-Shufen excludes AA cases from the base population.

\#### Reported by Ling, C.


<hr>

\## **\[FY2018.March2018\]**

\### Modified - Reunification

- Some children stayed home (about 100-200 cases each year) while their
  child cases were open. Their custody was under DCFS and then
  transferred to parents. We will count them as reunification.
- Shufen will apply the same rule to permanency stability.

\#### Reported by Ling, C.


<hr>

\## **\[FY2018.March2018\]**

\### Modified - Child's age in Chapter 1 CFSR measures

-We excluded children who were 18 years old and older from the base
population.

\#### Reported by Ling, C.


<hr>

\## **\[FY2018.March2018\]**

\### Modified - Spell-related Tables (e.g., Length of stay)

-For those with spells ended but no follow-up placement event and no
legal info, we use close date to calculate length of stay.

\#### Reported by Ling, C.


<hr>

\## **\[FY2018.March2018\]**

\### Modified - Table re: legal custody

-In <b>cftvcm9400</b> table, there are circumstances where the first
legal spell starts some time after case opening. It could be days or
years after case opening. Shufen created one spell with opening date as
the starting date, and ending date is the starting date of the first
legal record in cftvcm9400.

\#### Reported by Shufen, W.


<hr>

\## **\[FY2018.February2018\]**

\### Reported - Tables re: legal custody

<u>cfrvcm9500</u>
-This table has unduplicated records for children.

<u>cftvcm9400</u>
-<i>lel_grdn_code</i>: this variable identifies if the legal custody
goes back to parents or not. The "GA" does not mean the legal custody
goes to a guardian (e.g., a relative). It might mean the guardianship is
under a guardian other than parents but the parents still owns the
custody. Emancipation minors can seek for independent from their
parents, which might be called as GA as well. The blank in this variable
refers to DCFS wards.

\#### Reported by Martin, N.


<hr>

\## **\[FY2018.February2018\]**

\### Modified - Downloading LGC data


- LGC has a lot of bad date data -- importing SQL file from DCFS always
  gives Aaron errors. He tried to tune the server so we can download the
  data quickly when we need to do monthly updates.
- Aaron is attempting to script CSV imports and data cleaning
  procedures. CSV using PostgreSQL bulkloading, which requires clean
  data for successful imports.

\#### Reported by Aaron B.


<hr>

\## **\[FY2018.February2018\]**

\### Modified - age in Indicators <b>1B</b> and <b>1C</b>

-We exclude all the children whose age is over 18. Note that we do not
apply this rule to <b>2A</b> (Maltreatment in foster care) because we
count everyone as long as DCFS defines them as "victim."

\#### Reported by Ling C.


<hr>

\## **\[FY2018.February2018\]**

\### Modified - <b>cycfamily</b> in LGC

- We created this file. We did not have all the family cases (history)
  in this table. Now Martin used <b>cftvcm9100</b> table that contains
  family case history to redo the cycfamilycase.
- In LGC there is only a table with the family's most recent case, no
  history records.
- <b>cftvln1500</b> includes all the cases opening id (including the
  history of all the case openings for each family) but no much other
  information related to cases. Martin linked the id from
  <b>cftvln1500</b>, back to SACWIS, and tried to find family history
  information.

\#### Reported by Martin N.


<hr>

\## **\[FY2018.February2018\]**

\### Reported - <b>cftvcm9100</b> in LGC

- This file includes all of the child and family cases.
- <i>oct_type</i>: "o" refers case opening, "c" refers to closing, and
  "t" refers to transfer a team.
- <i>otc_rsn_code</i>: "NG" means neglect.
- When a case opened with AA(adoption), the SACWIS ID is 00 because they
  don't assign them a id.
- <i>case_id</i> ending with 00 refers to family case id.
- <i>case_rsf</i> is the unit assignment. Some cases had both units
  during their case opening periods.

\#### Reported by Martin N.


<hr>

\## **\[FY2018.February2018\]**

\### Added - POS and DCFS units in intact family services (re:
<b>org_entity</b> in SACWIS)

- Martin figured out how to identify the two units, POS vs. DCFS.
- Team assignment indicator is a little bit confusing because DCFS
  usually assigns persons to supervise POS. So they looked like a DCFS
  unit but maybe a POS unit.
- <i>id_org_ent</i> is the agency id.
- cd_agcy: 0 or 1 refer to DCFS; 2 refers to POS
- <i>id_rsf</i>: if the last two digits are letters, they are POS; if
  the last two digits are blank or numbers, they are DCFS.
  </li>

\#### Reported by Martin N.


<hr>

\## **\[FY2018.January2018\]**

\### Modified - Runaway (also Indicator 3B: Reunification Stability)


- When a child ran away for one day and the date is as the same as the
  reunification date, Chapin Hall categorized it as reunification and
  ignored the runaway record when creating the <b>subcare_spell</b>
  table. (Note - Censor field in subcare_spell has
  'Runaway/other/missing' category. Ignoring one-day runaway impacts
  subcare_spell, but does not impact master_spell.)
- Shufen did an adjustment based Chapin Hall's method related to
  reunification.

\#### Reported by Ling C.


<hr>

\## **\[FY2018.January2018\]**

\### Added/Modified - Emergency Foster Home (EFH)

-Emergency Foster Home used to be under "traditional foster homes."
-Tami decides to include EFH under "emergency shelter" category.

\#### Reported by Ling C.


<hr>

\## **\[FY2018.January2018\]**

\### Modified - <b>Adopt_link</b> table


- The <b>cftvma2000</b> table from legacy golden copy (LGC) links both
  IDs for pre- and post-adoption. In the past, we created the adopt_link
  table on our own.
- Tami asked: "Why did we use adoption link for doing reunification
  indicator?" -- because some children have both reunification and
  adoption records at the time when reaching permanency. We need to make
  sure we do not double count the records.

\#### Shufen W.


<hr>

\## **\[FY2018.January2018\]**

\### Modified - Allegation \#60: CPS investigation and allegation files

- Individuals who were indicated for Allegation \#60 between Oct 1, 2001
  – July 12, 2012, July 13, 2012 – Dec 31, 2013, or May 31, 2014 – June
  11, 2014 were removed from the State Central Register and the
  indicated findings in SACWIS were to be expunged.
- We decided not to use the data files that include Allegation \#60
  between 2001 and 2014. Consequently, the outputs will be similar to
  what DCFS reports.
- This change only affects historical data. Data and indicators after
  2014 are not affected.

\#### Reported by Satomi W.


<hr>

\## **\[FY2018.January2018\]**

\### Modified - County for the indicators in Chapters 2 and 3

- The county is based on the address of where the child resided.
- For each indicator we are adopting the same rule as the rules for
  region. See the table reported on 11/9/17 for more details.
- The data from Chapin Hall included the valid codes only, and the case
  was blank if the county information is missing. However, some of the
  records do not refer to actual counties in the new data sets. They
  are:
  103-Out of state
  104-Unknown
  106-Out of country
  107-Dept of corrections
  108-Other state funded public schools
  999-Missing
  We are planning to recode these cases as ‘invalid,’ and we will
  exclude them when we tabulate the outcomes in the data center on the
  CFRC website.

\#### Reported by Satomi W.


<hr>

\## **\[FY2018.January2018\]**

\### Modified - Adoption link (Table: <i>adopt_link</i>)

- We used to create adopt_link on our own. Now cftvma2000 from LGC links
  <i>adoptid</i> and <i>precycid</i>.
- Affected indicators: Indicators 3B and 3D.

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.January2018\]**

\### New - <i>Master_spell</i> table

We created the <i>master_spell</i> table by our own using the
<i>liverhist</i> database table, and we did some modifications to this
table. Here are more details:

- If the case closing date is the same as the last spell ending date,
  and the case close reason is Completed Adoption (‘CA’), censor was
  coded as adoption.
- We found out that there is a new living arrangement code, ‘PGH’
  (Private Guardianship Home). If a spell ended with ‘PGH’ (Private
  Guardianship Home), the censor was coded as subsidized guardianship.
- EFC (Emergency Foster Care): this is a new code. We decided to report
  this substitute care together with emergency shelter.
- HFK (Home of Fictive Kin): this is a new code. In the future, we might
  have a separate outcome for this substitute care, but not this year.
- Previously, we used <i>master_spell</i> table created by Chapin Hall.

\#### Reported by Shufen, W.


<hr>

\## **\[FY2018.January2018\]**

\### Modified - placement_master_spell.sas

- Modified for cases with opencode 'AA.'

- If their closersn is 'CA' (completed adoption), and the final
  placement has missing servicecd and livarcd='FHA' (foster home
  adoption) with prvid '000000', I coded the placement as adoption. Thus
  their exit is adoption.
- If their closersn is 'SC' (service completed) but the rest of fields
  stay the same (the final placement has missing servicecd, livarcd
  ='FHA' with prvid '000000', ), I coded the placement as traditional
  foster care. Their exit is otherwise exit. These cases usually have
  the same pattern of placement history.

\- Chronologically, the history will be

1.  servicecd as adoptive placement, livarcd='HMP' and a none-zero prvid
2.  servicecd as '4901' or '4999' (interim payment), livarcd='FHA' with
    a different none-zero prvid
3.  missing servicecd, livarcd='FHA' with prvid '000000'.

\- Affected tables are the following :

- hmr_monitor
- master_spell
- new_monitor

\#### Reported by Shufen, W.


<hr>

\## **\[FY2018.January2018\]**

\### New data extraction method

- We imported data from DCFS Data Warehouse for the BH report, and the
  extraction date is January 1 , 2018.
- In the past we used the September 30 data extract of IL DCFS
  Integrated Database, which is maintained by Chapin Hall.

<hr>

\## **\[FY2018.January2018\]**

\### Modified - Age for Indicator 1b

- The SAS programming file for Indicator 1b has been revised.
- The data file that we access to has more detailed information on
  intact service opening and closing dates. Thus, we can find out the
  child’s actual age during the time that the intact service was
  provided. Since we did not have detailed information in the past, it
  was possible a person considered to be a child in the data might have
  been 18 years old or older.

\#### Reported by Kyle A.


<hr>

\## **\[FY2018.January2018\]**

\### Modified - cps_child (Coding schema in race/ethnicity)


- We changed the coding scheme for race and ethnicity when creating the
  cps_child data file. The main changes are likely to affect the
  "Hispanic" and "Other Ethnicity" categories.
- In the past a white child with Hispanic heritage might have been
  categorized as "White," but based on this scheme, the child will be
  categorized as “Hispanic.”
- In the past it was likely that in the past some Hispanics were coded
  as “Others.”
- Indicators affected: Indicators <b>1A</b> (Maltreatment recurrence)
  and <b>1C</b> (Maltreatment recurrence - no services).

\#### Reported by Martin N.


<hr>

\## **\[FY2018.December2017\]**

\### Modified - Table for Indicator 1B (Intact services)

-Martin made some changes to the table <b>chinntact</b> (available at
/share/m-nieto/Data/bh2018).

- <i>kroladult</i>=’Yes’ indicates that the child is older than 18 years
  old when his/her family received the intact family.
- <i>birthaftercc</i>=’Yes’ indicates that the child was born after the
  intact case is closed.
- <i>shortfamc</i>=1 indicates that the duration between open and close
  dates is shorter than 8 days.

\#### Reported by Satomi W.


<hr>

\## **\[FY2018.December2017\]**

\### Modified - Base population for Indicator 2A (Initial Placement)

-Base population is the number of children in substitute care which
includes kinship, traditional, specialized, group home, institution,
independent living, emergency shelter, emergency foster care, runaway,
college/university, unauthorized placement, armed services duty, and
missing/unknown. We excluded <u>runaway, college/university,
unauthorized placement, armed services duty, and missing/unknown in
previous reports</u>.


<hr>

\## **\[FY2018.November2017\]**

\### Modified - Event exclusion in Indicators 2A and 2H

Indicator <b>2A</b> (Maltreatment in Care)
\*if event not in ('HAP','HMP','SGH','000','ZZZ','ZZA','ASD','CUS',
'ILO','OTH','PND','RNY','UNK','GDN')

Other indicators except placement stability
\*if event not in
('000','ABD','ASD','CUS','DEC','GDN','HAP','HHF','HMP',
'JTP','MIS','OTH','PND','RNY','SGH','UAP','UNK','UAH','WCC','WUK','YIC','YIE','ZZZ');

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.November2017\]**

\### Modified - County field for CYCIS indicators

-Provider county is in <i>livarhist</i> table. Shufen will check the
completeness of this field and if it looks okay, it will be added to
<b>master_event</b> and <b>new_monitor</b> tables.

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.November2017\]**

\### Modified - <i>livarcd</i>

-Separate new <i>livarcd</i> when creating <b>master_event</b> and
<b>new_monitor</b>

- '01'='Home of parent'
- '02'='Kinship foster home'
- '03'='Adoptive placement'
- '04'='Traditional foster home'
- '05'='Specialized foster home'
- '06'='Group home'
- '07'='Institution'
- '08'='Adoption subsidy'/\*adoption subsidy\*/
- '09'='Independent living'
- '10'='Subsidized guardianship'
- '11'='Emergency shelter'
- '12'='Emergency foster care'
- '13'='Runaway(RNY,ABD,WCC,WUK)'/\*'RNY','ABD','WCC','WUK'\*/
- '14'='DET,IDC'
- '15'='Unauthorized (UAP,UAH)'/\*'UAP','UAH'\*/
- '16'='Deceased(DEC)'/\*'DEC'\*/
- '17'='HHF'
- '18'='CUS,JTP,YIC,YIE'
- '19'='ASD,OTH,UNK'
- '20'='HFM'
- '21'='HFP'
- '22'='PGH'

-HFK is flagged by a vairable named hfk (1 is hfk, 0 is not).

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.November2017\]**

\### Modified - Intact family table

- Jeremy Harvey requested an analysis related to the maltreatment in
  intact families and maltreatment in care. Martin got the population
  numbers matched, but age seems awkward. Age is calculated from
  <i>bdate</i> in client registration table.
- The table that flags Intact family only includes records in recent
  years. At this point, we will go with our way to identify intact
  families rather than combining our way and flagging table. Cftvcr9600
  includes cli_id (family cluster id) and family members. K is for kids.

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.November2017\]**

\### Modified - Indicators 3D and 3F (stability disruption)

- Adoption disruption: Livarcd ‘FHA’ usually comes with ‘4901’,’4999’
  servicecd for ‘AA’ opencode cases. Chapin coded them as ‘FHA’ and
  indicator program excluded them when counting disruption. A case could
  have multiple FHA with different <i>prvid</i>. Martin decided to
  consider them as adoption disruption. The output numbers for adoption
  disruption will thus be smaller compared with previous reports.
- Reunification: Shufen tried to run ind3b using master_spell instead of
  subcare_spell. Both the numerator and denominator are larger for each
  FY compared to Chapin numbers. But the percentages are similar.
- Martin suggests running in3f, guardianship stability using
  master_spell and see the output numbers. The goal is to make it
  consistent for permanency stability. Currently, Indicator 3B uses
  <b>subcare_spell</b> and 3F uses <b>new_monitor</b>.

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.November2017\]**

\### Modified - First placement(s) with the same starting date and
ending date in <i>livarhist</i>

-Some cases in livarhist have first placement(s) with the same
<i>livarstrtdt</i> and <i>livarenddt</i>. This could be because:

- put kids in placement while opening case, and then place them in
  another placement following case opening.
- documenting issue.
- case workers try to place kids in that placement, but it does not
  work. They have to change placement.

These placements are not meaningful at this point. Remove them when
creating master_event.

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.November2017\]**

\### Modified - Region code

- Region in Casersf is not complete. For ‘AA’ cases, there is only
  region information at case closing. Martin pulled case open region
  from <i>livarhist</i> table and added to casersf/case_region table.
  (also for caseopnrsn ‘YI’, ‘JJ’ which also tend to have a short
  history of placement)
- Shufen kept case open region(oregion) and case close region(cregion)
  in cyc_case. When running entry cohort indicators, use open region
  instead of case_region file.

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.November2017\]**

\### New - <i>livarcd</i> in livarhist table

- Separate them out for future use.
- Create a variable that flags ‘HFK’ placements.
  - HFK: children stay with foster home parents for a while, and they
    see them as ‘relatives’. Subsidized guardianship is only for
    relatives. HFK code makes these foster home parents eligible for
    subsidized guardianship. We can look into them in more details when
    we have time.
    </li>

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.November2017\]**

\### Modified - Exit type in Indicator 3A

- If censor=4 and endevent in
  ('FHA','FHI','FHP','FHS','FHB','HMR','ZZZ','OTH','UNK','UAP','UAH','ASD')
  and agelastpl \>= 17 then exittype='Aged Out ';
- else if censor=4 and endevent in
  ('HHF','IPA','NCF','GRH','IMH','IRS','ICF') then exittype='Hosp/Inst';
- else if censor=4 and endevent in
  ('ILO','CIL','TLP','YIC','JTP','YIE','CUS',) then exittype='Ind Liv';
- else if censor=4 and endevent in ('DET','IDC') then
  exittype='Incarcerated';
- else if censor=4 and endevent in ('RNY','ABD','WUK','WCC') then
  exittype='Runaway';
- else if censor=4 and endevent in ('DEC') then exittype='Death';
  </li>
- else if censor=4 and endevent in
  ('FHA','FHI','FHP','FHS','HMR','OTH','ZZZ','UNK','FHB','UAP','DRA')
  then exittype='Other';

<li>

Check GRH freq.

</li>
<li>

Group YIE, CUS into independent living.

</li>
<li>

Add FHB to aged out.

</li>
<li>

DRA is not used after 1997.

</li>
</ul>

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.November2017\]**

\### New - livarcd in <i>livarhist</i> table

HFM, HFP, EFC. Martin will download new code description and save the
file under his share folder.

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.November2017\]**

\### Modified - Table re: intact families

Martin used cftvcr9600, cftvln1500, livarhist table to identify intact
families. This is a new table which indicates intact families. Martin
will run that to compare output numbers.

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.November2017\]**

\### Modified - Region in Legacy Golden Copy

- In the previous reports, the region information was a combination of
  case open region and region at case closing. In other words, if the
  case is closed, use the region at the case closing.
- We use the DCFS administrative region at the case opening if we
  examine the outcomes at the initial placement. For the outcomes
  related to the end-of-year placement, we used the closest effective
  date to the end of the year within the FY.
- Indicators affected: Indicators in Chapters 2 and 3. For more details,
  see the table below.

<h5>

Operational Definition of Region

</h5>

| Indicator | Title                                                                            | Rule                                            |
|-----------|----------------------------------------------------------------------------------|-------------------------------------------------|
| 1A        | Maltreatment Recurrence (CFSR)                                                   | Region where the investigation took place       |
| 1B        | Maltreatment Among Children in Intact Family Cases                               | Region at the case opening date                 |
| 1C        | Maltreatment Recurrence Among Children Receiving No Services                     | Region where the investigation took place       |
| 1D        | Maltreatment in Substitute Care (CFSR)                                           | Region of the 1st placement for the FY          |
| 2A1-2A6   | Initial Placement                                                                | Region at the case opening date                 |
| 2B1-2B7   | End of Year Placement                                                            | Region at the end of the year                   |
| 2C        | Initial Placement with Siblings                                                  | Region at the case opening date                 |
| 2D        | End of Year Placement with Siblings                                              | Region at the end of the year                   |
| 2E        | Placement Stability (CFSR)                                                       | Region at the case opening date                 |
| 2F        | Children Who Run Away from Substitute Care                                       | Region at the case opening date                 |
| 2G        | Median Length of Stay in Substitute Care                                         | Region at the case opening date                 |
| 3A1-3A3   | Reunification (within 12, 24, & 36 months)                                       | Region at the case opening date                 |
| 3B1-3B4   | Stability of Reunification (1, 2, 5, & 10 years)                                 | Region where the reunification happened         |
| 3C1, 3C2  | Adoption (within 24 & 36 months)                                                 | Region at the case opening date                 |
| 3D1-3D3   | Stability of Adoption (at 2, 5, & 10 years)                                      | Region of Adoption assistance case opening date |
| 3E1, 3E2  | Guardianship (within 24 & 36 months)                                             | Region at the case opening date                 |
| 3F1-3F3   | Stability of Guardianship (at 2, 5 & 10 years)                                   | Region where the guardianship becomes effective |
| 3G        | Permanency in 12 Months for Children Entering Substitute Care (CFSR)             | Region at the case opening date                 |
| 3H        | Permanency in 12 Months for Children in Substitute Care12 – 23 months (CFSR)     | Region at the case opening date                 |
| 3I        | Permanency in 12 months for Children in Substitute Care 24 months or more (CFSR) | Region at the case opening date                 |
| 3J        | Re-entry to Substitute Care among Children in Care Less Than 12 months (CFSR)    | Region at the case opening date                 |
| 3K        | Re-entry to Substitute Care among Children in Care 12 – 23 months                | Region at the case opening date                 |
| 3L        | Re-entry to Substitute Care among Children in Care 24 months or more             | Region at the case opening date                 |
|           | Living with Relatives (within 24 & 36 months)                                    | Region at the case opening date                 |
|           | Stability of Permanence – Living with Relatives (at 2, 5 & 10 years)             | Region where living with relatives started      |

\#### Reported by Shufen W.


<hr>

\## **\[FY2018.November2017\]**

\### Modified - subcare_spell

-In creating <i>subcare_spell</i> table, Shufen grouped relative,
traditional, specialized foster care, group homes, institutions,
emergency shelters, and some other living arrangement
('HFK','HHF','PGH','UAP','UAH') into subcare based on examining Chapin
Hall <i>subcare_spell</i> table.

\#### Reported by Shufen, W.


<hr>

\## **\[FY2018.November2017\]**

\### New - Emergency Foster Care (EFC)

-The <i>livarhist</i> table includes a new livarcd code, EFC (emergency
foster care) recently (The earliest record that this code appeared is
Dec. 2016). Servicecd associated with EFC are 0104, 0911, 9104, 9011,
and 9911. These servicecd's have (livarcd) FHA/FHB/FHS etc.
previously.
-Our BH report might need to report emergency foster care separately.
Currently, they are grouped into other substitute care, such as
traditional/kinship/specialized, etc.

\#### Reported by Shufen, W.


<hr>

\## **\[FY2018.October2017\]**

\### Changed: <i>livarhist</i>

-There are two types of missing values in the field for case closing
date (casecloseddt). One is blank and another one is '31DEC9999.'

\#### Reported by Shufen, W.


<hr>
