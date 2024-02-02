<h1>

Introduction

</h1>

The Children and Family Research Center (CFRC) monitors the performance
of the Illinois child welfare system by evaluating how well it achieves
its stated goals of child safety, permanency, and well-being. Using the
administrative data processed by the Illinois Department of Children and
Family Services (DCFS), we produce various safety and permanency outcome
indicators of children served by DCFS. The *Monitoring Report of the
B.H. Consent Degree* (**the *B.H.* report**) is the culmination of the
CFRC’s efforts to provide clear and comprehensive data to a variety of
stakeholders who are concerned with the outcomes of maltreated children
in Illinois.

The administrative data are extracted from two DCFS information systems:
SACWIS (the Statewide Automated Child Welfare Information System) and
LGC (Legacy Golden Copy). The SACWIS data mainly track allegations and
findings of abuse and neglect reported to and investigated by DCFS. The
LGC data include detailed client, service provision, and payment records
for children and families who receive DCFS child welfare services. Four
times a year (March, June, September, and December) we transfer data
from the DCFS data warehouse to our database.

Each of the tables was developed based on the data file we used to
receive from the Chapin Hall Center for Children. Prior to FY2018, CFRC
utilized DCFS administrative data processed by Chapin Hall (Integrated
Database, known as IDB) to compute the outcome indicators included in
the *B.H.* report. In FY2016 CFRC was given direct access to the DCFS
data warehouse, which contains information from the numerous data
systems currently in use at the Department. In FY2018 CFRC switched the
data source from the Chapin Hall Integrated Database to data extracted
from the DCFS data warehouse to compute the outcome indicators in the
*B.H.* report. Although the data contained in the two data sources are
similar, they are not equivalent. For more details about the data
changes, please read the introduction chapter and Appendix E in [the
FY2018 *B.H.*
report](https://www.cfrc.illinois.edu/pubs/rp_20181029_ConditionsOfChildrenInOrAtRiskOfFosterCareInIllinoisFY2018MonitoringReportOfTheBHConsentDecree.pdf).

After the database tables in the BH schema are updated,
indicator-specific database tables are created and saved in the BH_IND
schema. BH and CFSR (Child and Family Services Reviews) indicator
outcomes are produced for the *B.H.* report and Data Center. To see the
list of the BH outcome indicators and the performance trend, visit
[CFRC's Data Center
webpage](https://www.cfrc.illinois.edu/outcome-indicator-tables.php).
Results in each BH outcome indicator are sorted by child's age, race,
and gender. You can learn the trend not only by all children in Illinois
but also in a specific region, subregion, or county. The [CFSR Indicator
Table](https://www.cfrc.illinois.edu/cfsr-tables.php) page in Data
Center is a good start to learn about the CFSR measures that are used
for the *B.H.* report. See the file */CFRC/SAS/BH/readme* for more
details about the sequence of programs that is run to produce the
database tables for the BH and BH_IND schemas.

<h1>

Tables in BH Schema

</h1>

We extract the administrative data from DCFS and clean them. After that,
we create a series of BH database tables in the BH schema.

<h1>

Tables in BH_IND Schema

</h1>

The table below presents the indicator name, programming file, and the
data table used for creating the indicator. Each indicator-specific
table is saved in the BH_IND schema.  

| Indicator name                                                           | Programming file            | BH database table |
|--------------------------------------------------------------------------|-----------------------------|-------------------|
| Maltreatment Recurrence                                                  | ind1ac_cfsr_malt_recur      | cps_alleg         |
|                                                                          |                             | cps_inv           |
|                                                                          |                             | cps_child         |
|                                                                          |                             | client_xref       |
|                                                                          |                             | livarhist         |
|                                                                          |                             | cftvcr9600        |
|                                                                          |                             | family_xref       |
|                                                                          |                             | client_xref       |
|                                                                          |                             | child_intact      |
| Maltreatment Among Children in Intact Family Cases                       | ind1b_cfsr_maltreat_intact  | child_intact      |
|                                                                          |                             | cps_alleg         |
| Maltreatment Recurrence Among Children Receiving No Services             | ind1ac_cfsr_malt_recur      | cps_alleg         |
|                                                                          |                             | cps_inv           |
|                                                                          |                             | cps_child         |
|                                                                          |                             | client_xref       |
|                                                                          |                             | livarhist         |
|                                                                          |                             | cftvcr9600        |
|                                                                          |                             | family_xref       |
|                                                                          |                             | client_xref       |
|                                                                          |                             | child_intact      |
| Maltreatment in Substitute Care                                          | CFSR_number_of_days_V2      | master_event      |
|                                                                          |                             | cps_inv           |
|                                                                          |                             | cps_alleg         |
|                                                                          |                             | cyc_child         |
|                                                                          |                             | case_region       |
|                                                                          |                             | cpscyc_link       |
| Initial Placement                                                        | in2a_ini_placetype          | master_event      |
|                                                                          |                             | master_spell      |
|                                                                          |                             | cyc_case          |
| End of Year Placement                                                    | ind2b_eoy_placetype         | master_event      |
|                                                                          |                             | cyc_case          |
|                                                                          |                             | master_spell      |
|                                                                          |                             | case_region       |
|                                                                          |                             | cyc_child         |
| Initial Placement with Siblings                                          | ind2c_ini_sibling           | master_event      |
|                                                                          |                             | master_spell      |
|                                                                          |                             | cyc_case          |
| End of Year Placement with Siblings                                      | ind2d_eoy_sibling           | master_event      |
|                                                                          |                             | cyc_case          |
|                                                                          |                             | master_spell      |
|                                                                          |                             | case_region       |
|                                                                          |                             | cyc_child         |
|                                                                          |                             | cftvcr9100        |
| Children Who Run Away from Substitute Care                               | ind2f_runaway_1styr         | master_event      |
|                                                                          |                             | master_spell      |
|                                                                          |                             | cyc_case          |
| Median Length of Stay in Substitute Care                                 | ind2g_lengthofstay          | master_event      |
|                                                                          |                             | master_spell      |
|                                                                          |                             | cyc_case          |
| Exit to Permanence                                                       | ind3aceg_exittoperm         | master_event      |
|                                                                          |                             | master_spell      |
|                                                                          |                             | cyc_case          |
| Stability of Reunification                                               | ind3b_permstab_reunify      | master_spell      |
|                                                                          |                             | cyc_child         |
|                                                                          |                             | cyc_case          |
|                                                                          |                             | case_region       |
| Stability of Adoption                                                    | ind3d_permstab_adopt        | master_spell      |
|                                                                          |                             | adopt_link        |
|                                                                          |                             | cyc_child         |
|                                                                          |                             | cyc_case          |
|                                                                          |                             | case_region       |
| Stability of Guardianship                                                | ind3f_permstab_gship        | master_spell      |
|                                                                          |                             | cyc_child         |
|                                                                          |                             | cyc_case          |
|                                                                          |                             | case_region       |
| Stability of Living with Relatives                                       | ind3h_permstab_relative     | master_spell      |
|                                                                          |                             | case_region       |
|                                                                          |                             | cyc_child         |
|                                                                          |                             | cyc_case          |
| Placement Stability                                                      | CFSR_stability_V3           | hmr_monitor       |
| Permanency in 12 months for Children Enterting Substitue Care            | ind3g_cfsr_exit_to_perm12   | master_spell      |
|                                                                          |                             | hmr_monitor       |
| Permanency in 12 Months for Children in Care 12 to 23 Months             | ind3hi_cfsr_exit_to_perm    | master_spell      |
|                                                                          |                             | hmr_monitor       |
| Permanency in 12 Months for Children in Care 24 Months or More           | ind3hi_cfsr_exit_to_perm    | master_spell      |
|                                                                          |                             | hmr_monitor       |
| Re-Entry to Substitute Care Among Children in Care Less Than 12 Months   | ind3j_cfsr_reentry_12       | adopt_link        |
|                                                                          |                             | master_spell      |
| Re-Entry to Substitute Care Among Children in Care for 12 to 23 Months   | ind3k_cfsr_reentry_12to23   | adopt_link        |
|                                                                          |                             | master_spell      |
| Re-Entry to Substitute Care Among Children in Care for 24 or More Months | ind3l_cfsr_reentry_24ormore | adopt_link        |
|                                                                          |                             | master_spell      |

<h1>

Issues with Allegation 60 (or *Ashley M.* or *Julie Q.*)

</h1>

The Illinois Supreme Court issued a decision in the case of *Julie Q. v.
Illinois Department of Children and Family Services*, 2013 IL 113783
(March 21, 2013), in which the court held that Allegation 60 was void
because DCFS did not have the authority to investigate and indicate an
allegation based on an “environment injurious” because the “injurious
environment” language was removed from the definition of neglected child
in the Abused and Neglected Child Reporting Act in 1980. Individuals
investigated and indicated for Allegation 60 prior to July 13, 2012 will
be removed as indicated perpetrators of child abuse and neglect for
Allegation 60 from the department’s State Central Register in light of
the court’s decision. All other indicated findings remain unchanged.

Effective July 13, 2012, the Illinois General Assembly reinstated the
term “environment injurious” in the definition of neglected child in the
Abused and Neglected Child Reporting Act. All indicated findings for
Allegation 60 investigated and indicated on and after July 13, 2012 will
remain on the State Central Register unless they are removed in
accordance with the department’s normal retention period, pursuant to a
final administrative decision of the director or other court order. [^1]

*Ashley M.* and *Julie Q.* are the two class action suits leading to
court orders to unfound indicated reports. During the periods covered by
these reports all allegation 60 - 'Risk of Harm'- indicated findings are
reversed (unfounded). Findings for allegation 60 for reports outside
those periods remain unaffected.

The result is inconsistency in counts of indicated reports across time
and inconsistency counting indicated reports within a period at two
different times when these court orders are implemented. Trends can be
established for total number of reports investigated and numbers of
non-risk of harm allegations indicated, just not for indicated reports,
for the affected allegation, or indicated victims if the only indicated
allegation is that affected allegation. [^2]

| Class Action Lawsuit | Period Affected                   |
|---------------------|----------------------------------|
| Julie Q.             | October 1, 2001 - July 12, 2012   |
| Ashley M.            | July 13, 2012 - December 31, 2013 |
| Ashley M.            | May 31, 2014 - June 11, 2014      |

- To learn more about Allegation 60, *Julie Q.* issues, and the effects
  on the data, read Appendix D "*Julie Q. v. Department of Children and
  Family Services*: What Implication Does It Have for Outcome Monitoring
  in Illinois" in [the 2014 *B.H.*
  report](https://www.cfrc.illinois.edu/pubs/rp_20160201_ConditionsOfChildrenInOrAtRiskOfFosterCareInIllinois2014MonitoringReportOfTheB.H.ConsentDecree.pdf).
- For more technical details on how to recode Allegation 60 (alleg=31)
  in our programming file, see */SAS/BH/cps_alleg.sas*.

<h1>

New DCFS Report on Subsequent Oral Reports Date (scrseq)

</h1>

To learn more about the changes in the definitions of subsequent oral
reports date, see: (a) *Overview: New DCFS Report on Child Protective
Services (pp. 2-3)* in the DCFS document [Six-year Statistics on Child
Protective Services: Data as of March 31,
2018](pdfs/2018_March_six_year_stats.pdf)
and/or (b)*Note on Subsequent Oral Reports Date (on p.2)* in the DCFS
document [Six-year Statistics on Child Protective Services: Data as of
June 30,
2018](pdfs//2018_June_six_year_stats.pdf).

<h1>

Glossary

</h1>

## Adoption dissolution

- Means a circumstance where the child is removed from an adoptive
  placement after the adoption is finalized. \[750 ILCS 50/1(AA)\] [^3]

## Adoption subsidy (or Adoption assistance)

- Our database does not contain an specific indicator for the number of
  former DCFS wards who are, at any given time, living at home with
  adoptive parents, nor does it contain and indicator of how many of
  these adoptions are temporarily or permanently disturbed. A majority
  of adoption completed through DCFS are subsidized, typically until the
  children reaches 18. Therefore, the number of open adoption subsidy
  cases is used as an indicator of the number of children living with
  adoptive parent.
- If the type of service arrangement is coded as one of the following
  service payment codes, we define the case as an adoption subsidy (or
  adoption assistance).

| cd_type_serv | Description                              |
|-------------|-----------------------------------------|
| 301          | Adoption Subsidy / Ongoing               |
| 302          | Adoption Subsidy / Legal                 |
| 303          | Adoption Subsidy / Medical               |
| 304          | Adoption Subsidy / Health Insurance      |
| 313          | Adoption Subsidy - Standard Age Rate     |
| 314          | Adoption Subsidy - Intensive Age Rate    |
| 315          | Adoption Subsidy - Benefit Reduced       |
| 316          | Adoption Subsidy - Specialized Rate      |
| 317          | Adopt Subsidy-Reg Fc Rate 7/1/08         |
| 318          | Adopt Subsidy-Reg Fc Rate Nonward 7/1/08 |
| 323          | Adoption Subsidy - Standard Age Rate     |
| 324          | Adoption Subsidy - Intensive Age Rate    |
| 326          | Adoption Subsidy - Specialized Rate      |
| 327          | Individually Calculated Subsidies        |
| 331          | Adoption Subsidy - Reg.F.C. Prior 7/1/95 |
| 332          | Adoption Subsidy -Reg F.C.After 6/30/95  |
| 333          | Adoption Subsidy -Intensive Prior 7/1/95 |
| 334          | Adoption Subsidy -Intensive After6/30/95 |
| 335          | Adoption Subsidy-Eligible Other Benefits |
| 336          | Adoption Subsidy-Spec Rate/Manual Enter  |
| 337          | Adoption Subsidy-Inc.Necess/Manual Calc  |
| 338          | Adoption Subsidy-No Cola                 |
| 339          | Adoption Subsidy-Reg Non Ward            |
| 346          | Adoption Subsidy-Reg Fc 7/01/06          |
| 347          | Adoption Subsidy-Reg Fc Non-Ward 7/01/06 |
| 349          | Adoption Subsidy-Spec Nonward            |
| 350          | Adoption Subsidy Under 19 In School      |
| 351          | Adopt Sub-Under 19 In School Nonward     |
| 352          | Adopt Sub-Under 21 W/Disability Nonward  |
| 355          | Adoption Subsidy Under 21 W/ Disability  |

Note that in addition to the codes listed above, the following service
arrangement type codes are included in the adoption subsidy (Adoption
assistance): '319', '321', '325', '329', '353' and '395'. These codes
are not listed on the current SACWIS table.

## Age

- Child age is used for the age category. For more details for each
  indicator, see the table below.
- If the child's age was unknown due to the missing birth date or
  yielded a negative value (\< 0), we coded the value as missing and
  excluded from the percent calculations in the age category.

|          | Indicator Name                                                                   | Variable used for computing age | Age is assigned based on how old a child is:                  |
|----------|----------------------------------------------------------------------------------|---------------------------------|---------------------------------------------------------------|
| 1.A      | Maltreatment Recurrence (CFSR)                                                   | reptdate                        | At the initial indicated report date                          |
| 1.B      | Maltreatment Among Children in Intact Family Cases                               | opendate                        | At the intact case opening date                               |
| 1.C      | Maltreatment Recurrence Among Children Receiving No Services                     | reptdate                        | At the initial indicated report date                          |
| 1.D      | Maltreatment in Substitute Care (CFSR)                                           | plac_strtdate                   | At the first date of the placement                            |
| 2.A      | Initial Placement                                                                | odate                           | At the case opening date                                      |
| 2.B      | End of Year Placement                                                            | endyr                           | At the last day of the fiscal year (June 30)                  |
| 2.E      | Placement Stability (CFSR)                                                       | sdate                           | At the first date of the first placement                      |
| 2.F      | Children Who Run Away from Substitute Care                                       | odate                           | At the case opening date                                      |
| 2.G      | Median Length of Stay in Substitute Care                                         | odate                           | At the case opening date                                      |
| 3A/3C/3E | Permanence - Reunification/Adoption/Guardianship                                 | odate                           | At the case opening date                                      |
| 3.B      | Stability of Reunification                                                       | hmpdate                         | At the exit (to reunification) date                           |
| 3.D      | Stability of Adoption                                                            | adptdate                        | At the exit (to adoption) date                                |
| 3.F      | Stability of Guardianship                                                        | gdate                           | At the exit (to guardianship) date                            |
| 3.G      | Permanency in 12 Months for Children Entering Substitute Care (CFSR)             | opendate                        | At the case opening date                                      |
| 3.H      | Permanency in 12 Months for Children in Substitute Care 12 to 23 Months (CFSR)   | strtfy (ageFDyrs)               | First day of the fiscal year which the child had been in care |
| 3.I      | Permanency in 12 Months for Children in Substitute Care 24 Months or More (CFSR) | strtfy (ageFDyrs)               | First day of the fiscal year which the child had been in care |
| 3.J      | Re-entry to Substitute Care Among Children in Care Less Than 12 Months (CFSR)    | opendate                        | At the case opening date                                      |
| 3.K      | Re-entry to Substitute Care Among Children in Care 12 to 23 Months               | strtfy (ageFDyrs)               | First day of the fiscal year which the child had been in care |
| 3.L      | Re-entry to Substitute Care Among Children in Care 24 Months or More             | strtfy (ageFDyrs)               | First day of the fiscal year which the child had been in care |

## Age group

- [Child age](BH_Data#Age) is organized by the following four
  intervals and derived from a child's date of birth.
  - Under 3 years old
  - 3 to 5
  - 6 to 11
  - 12 to 17

<!-- -->

- To show the change of the family allegation reports, the first
  caregiver listed on the family report is broken down into six
  categories. They are:
  - Under 20 years old
  - 20 to 29
  - 30 to 39
  - 40 to 49
  - 50 to 59
  - 60 and older

## Allegation of abuse/neglect

- The allegation system defines moderate to severe harm or the risk of
  moderate to severe harm of a child. Many of the allegations are
  categorized as either abuse or neglect. All abuse allegations of harm
  are coded with a one or two-digit number, 40 and under. All neglect
  allegations of harm are coded with a two-digit number greater than 50.
  <ref name="procedures300A"> Illinois Department of Children and Family
  Services. (2019). Procedures 300, Appendix B: The allegations system.
  Springfield, IL: Author. Retrieved from

<https://www2.illinois.gov/dcfs/aboutus/notices/Documents/Procedures_300_Appendix_B.pdf#search=300%20allegation%20system>

</ref>

- One investigation can have more than one allegation. A victim can have
  more than one household id (scrnum), which indicates that the child
  has changed household over time.
- As of March 31, 2020, 55 allegation codes are active (see the table
  below). To see the compleat list of allegations in SACWIS, including
  the ones currently not in use, see SACWIS.code_desc (id_grp=ALLEGCOD).

| Allegation ID | Description (with old code)                                                                   |
|---------------|-----------------------------------------------------------------------------------------------|
| 1             | 1-Death                                                                                       |
| 2             | 2-Head Injuries                                                                               |
| 3             | 4-Internal Injuries                                                                           |
| 4             | 5-Burns                                                                                       |
| 5             | 6-Poison Noxious Substances                                                                   |
| 6             | 7-Wounds                                                                                      |
| 7             | 9-Bone Fractures                                                                              |
| 8             | 10-Substantial Risk of Physical Injury/Environment Injurious to Health and Welfare            |
| 10            | 11-Cuts Bruises Welts Abrasions and Oral Injuries                                             |
| 11            | 12-Human Bites                                                                                |
| 12            | 13-Sprains/Dislocations                                                                       |
| 13            | 14-Tying/Close Confinement                                                                    |
| 14            | 15-Substance Misuse                                                                           |
| 15            | 16-Torture                                                                                    |
| 16            | 17-Mental Injury                                                                              |
| 17            | 18-Sexually Transmitted Diseases                                                              |
| 18            | 19-Sexual Penetration                                                                         |
| 19            | 20-Sexual Exploitation                                                                        |
| 20            | 21-Sexual Molestation                                                                         |
| 21            | 22a-Substantial Risk of Sexual Abuse - Sex offender has access                                |
| 22            | 22b-Substantial Risk of Sexual Abuse - Sibling of sex abuse victim                            |
| 23            | 22c-Substantial Risk of Sexual Abuse - Sexualized behavior of young child                     |
| 24            | 51-Death by Neglect                                                                           |
| 25            | 52-Head Injuries by Neglect                                                                   |
| 26            | 54-Internal Injuries by Neglect                                                               |
| 27            | 55-Burns by Neglect                                                                           |
| 28            | 56-Poison - Noxious Substances by Neglect                                                     |
| 29            | 57-Wounds by Neglect                                                                          |
| 30            | 59-Bone Fractures by Neglect                                                                  |
| 31            | 60-Substantial Risk of Physical Injury/Environment Injurious to Health and Welfare by Neglect |
| 32            | 61-Cuts Bruises Welts Abrasions and Oral Injuries by Neglect                                  |
| 33            | 62-Human Bites by Neglect                                                                     |
| 34            | 63-Sprains/Dislocations by Neglect                                                            |
| 35            | 65-Substance Misuse by Neglect                                                                |
| 36            | 67-Mental Injury by Neglect                                                                   |
| 38            | 75-Abandonment/Desertion                                                                      |
| 39            | 76-Inadequate Food                                                                            |
| 40            | 77-Inadequate Shelter                                                                         |
| 41            | 78-Inadequate Clothing                                                                        |
| 42            | 79-Medical Neglect                                                                            |
| 43            | 81-Failure to Thrive                                                                          |
| 44            | 82-Environmental Neglect                                                                      |
| 45            | 83-Malnutrition                                                                               |
| 47            | 85-Medical Neglect of Disabled Infants                                                        |
| 75            | 22d-Substantial Risk of Sexual Abuse - Child Pornography                                      |
| 76            | 40-Human Trafficking of Children                                                              |
| 77            | 90-Human Trafficking of Children by Neglect                                                   |
| 78            | 74a-Inadequate Supervision - Left Alone at Home, Outside or in the Community                  |
| 79            | 74b-Inadequate Supervision - Left Alone in Vehicle                                            |
| 80            | 74c-Inadequate Supervision - Left in the Care of an Inadequate Caregiver                      |
| 81            | 74d-Inadequate Supervision - General Category                                                 |
| 93            | 84a-Lock Out - Community Location                                                             |
| 94            | 84b-Lock Out - Psychiatrically Hospitalized                                                   |
| 95            | 84c-Lock Out - Correctional Facility                                                          |
| 96            | 86-Neglect by Agency                                                                          |

## Allegation types

The CFRC uses eight allegation types: sexual abuse; physical abuse;
substance exposure; emotional abuse; risk of harm; lack of supervision;
environmental neglect; and other neglect. There are four allegation
groups in Data Center. See the table below for more details.

| Website                        | Type                  | Description (with old code)                                                                                                                                             | New Code | Note            |
|--------------------------------|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|-----------------|
| Sexual abuse                   | Sexual Abuse          | \(18\) Sexually Transmitted Diseases                                                                                                                                    | 17       |                 |
|                                |                       | \(19\) Sexual Penetration                                                                                                                                               | 18       |                 |
|                                |                       | \(20\) Sexual Exploitation                                                                                                                                              | 19       |                 |
|                                |                       | \(21\) Sexual Molestation                                                                                                                                               | 20       |                 |
|                                |                       | \(40\) Human Trafficking of Children                                                                                                                                    | 76       |                 |
|                                |                       | \(90\) Human Trafficking of Children by Neglect                                                                                                                         | 77       |                 |
| Physical or other abuse        | Physical Abuse        | \(1\) Death                                                                                                                                                             | 1        |                 |
|                                |                       | \(2\) Head Injuries                                                                                                                                                     | 2        |                 |
|                                |                       | \(4\) Internal Injuries                                                                                                                                                 | 3        |                 |
|                                |                       | \(5\) Burns                                                                                                                                                             | 4        |                 |
|                                |                       | \(6\) Poison Noxious Substances                                                                                                                                         | 5        |                 |
|                                |                       | \(7\) Wounds                                                                                                                                                            | 6        |                 |
|                                |                       | \(9\) Bone Fractures                                                                                                                                                    | 7        |                 |
|                                |                       | \(11\) Cuts Bruises Welts Abrasions and Oral Injuries                                                                                                                   | 10       |                 |
|                                |                       | \(12\) Human Bites                                                                                                                                                      | 11       |                 |
|                                |                       | \(13\) Sprains/Dislocations                                                                                                                                             | 12       |                 |
|                                | Substance Exposure    | \(15\) Substance Misuse                                                                                                                                                 | 14       |                 |
|                                |                       | \(65\) Substance Misuse by Neglect                                                                                                                                      | 35       |                 |
|                                | Emotional Abuse       | \(14\) Tying/Close Confinement                                                                                                                                          | 13       |                 |
|                                |                       | \(16\) Torture                                                                                                                                                          | 15       |                 |
|                                |                       | \(17\) Mental Injury                                                                                                                                                    | 16       |                 |
|                                |                       | \(67\) Mental Injury by Neglect                                                                                                                                         | 36       |                 |
| Substantial risk of harm       | Risk of Harm          | \(10\) Substantial Risk of Physical Injury/Environment Injurious to Health and Welfare                                                                                  | 8        |                 |
|                                |                       | (22a) Substantial Risk of Sexual Abuse - Sex offender has access                                                                                                        | 21       |                 |
|                                |                       | (22b) Substantial Risk of Sexual Abuse - Sibling of sex abuse victim                                                                                                    | 22       |                 |
|                                |                       | (22c) Substantial Risk of Sexual Abuse - Sexualized behavior of young child                                                                                             | 23       |                 |
|                                |                       | \(60\) Substantial Risk of Physical Injury/Environment Injurious to Health and Welfare by Neglect                                                                       | 31       |                 |
|                                |                       | (22d) Substantial Risk of Sexual Abuse - Child Pornography                                                                                                              | 75       |                 |
|                                |                       | (86-10a) Substantial Risk of Physical Injury/Environment Injurious to Health and Welfare-Incidents of Violence or Intimidation                                          | 86       |                 |
|                                |                       | (87-10b) Substantial Risk of Physical Injury/Environment Injurious to Health and Welfare-Medical Child Abuse(Factitious Disorder by Proxy or Munchausen by Proxy.....)" | 87       |                 |
|                                |                       | (92-22e) Substantial Risk of Sexual Abuse – Suggestive Behavior                                                                                                         | 92       |                 |
| Lack of supervision or neglect | Lack of Supervision   | \(74\) Inadequate Supervision                                                                                                                                           | 37       |                 |
|                                |                       | \(75\) Abandonment/Desertion                                                                                                                                            | 38       |                 |
|                                |                       | \(84\) Lock Out                                                                                                                                                         | 46       |                 |
|                                |                       | (74a) Inadequate Supervision – Left Alone at Home Outside or in the Community                                                                                           | 78       | Added 9/5/19    |
|                                |                       | (74b) Inadequate Supervision – Left Alone in Vehicle                                                                                                                    | 79       | Added 9/5/19    |
|                                |                       | (74c) Inadequate Supervision – Left in the Care of an Inadequate Caregiver                                                                                              | 80       | Added 9/5/19    |
|                                |                       | (74d) Inadequate Supervision – General Category                                                                                                                         | 81       | Added 9/5/19    |
|                                |                       | (93-84a) Lock-Out-Community Location                                                                                                                                    | 93       |                 |
|                                |                       | (94-84b) Lock-Out-Psychiatrically Hospitalized                                                                                                                          | 94       |                 |
|                                |                       | (95-84c) Lock-Out-Correctional Facility                                                                                                                                 | 95       |                 |
|                                | Environmental Neglect | \(76\) Inadequate Food                                                                                                                                                  | 39       |                 |
|                                |                       | \(77\) Inadequate Shelter                                                                                                                                               | 40       |                 |
|                                |                       | \(78\) Inadequate Clothing                                                                                                                                              | 41       |                 |
|                                |                       | \(82\) Environmental Neglect                                                                                                                                            | 44       |                 |
|                                | Other Neglect         | \(79\) Medical Neglect                                                                                                                                                  | 42       | Medical Neglect |
|                                |                       | \(85\) Medical Neglect of Disabled Infants                                                                                                                              | 47       | Medical Neglect |
|                                |                       | \(51\) Death by Neglect                                                                                                                                                 | 24       | Other Neglect   |
|                                |                       | \(52\) Head Injuries by Neglect                                                                                                                                         | 25       | Other Neglect   |
|                                |                       | \(54\) Internal Injuries by Neglect                                                                                                                                     | 26       | Other Neglect   |
|                                |                       | \(55\) Burns by Neglect                                                                                                                                                 | 27       | Other Neglect   |
|                                |                       | \(56\) Poison – Noxious Substances by Neglect                                                                                                                           | 28       | Other Neglect   |
|                                |                       | \(57\) Wounds by Neglect                                                                                                                                                | 29       | Other Neglect   |
|                                |                       | \(59\) Bone Fractures by Neglect                                                                                                                                        | 30       | Other Neglect   |
|                                |                       | \(61\) Cuts Bruises Welts Abrasions and Oral Injuries by Neglect                                                                                                        | 32       | Other Neglect   |
|                                |                       | \(62\) Human Bites by Neglect                                                                                                                                           | 33       | Other Neglect   |
|                                |                       | \(63\) Sprains/Dislocations by Neglect                                                                                                                                  | 34       | Other Neglect   |
|                                |                       | \(81\) Failure to Thrive                                                                                                                                                | 43       | Other Neglect   |
|                                |                       | \(83\) Malnutrition                                                                                                                                                     | 45       | Other Neglect   |
|                                |                       | (96-86) Neglect by Agency                                                                                                                                               | 96       | Other Neglect   |

## Case opening

- When a family is eligible for DCFS direct or purchased services, a
  family case shall be opened. A child case shall be opened <u>only
  when</u> DCFS has assumed legal responsibility for a child. Case
  opening means the assignment of an identification number and
  completion and terminal entry of the appropriate modules. [^4]

## Central region

- A value of Central region is defined as regions *1B* (Peoria), *3A*
  (Springfield), and *3B* (Champaign).

## Child

- Means any person under the age of 18 years, unless legally emancipated
  by reason of marriage or entry into a branch of the United States
  armed services. \[325 ILCS 5/3\] <ref name="Procedures300">

Illinois Department of Children and Family Services. (2015). Procedures
300: Reports of Child Abuse and Neglect. Springfield, IL: Author.
Retrieved from
<https://www2.illinois.gov/dcfs/aboutus/notices/Documents/procedures_300.pdf>

</ref>

## Child report

Children receiving multiple allegation types are counted multiple times.

## Continuity

- Children should be placed in a safe setting that is the least
  restrictive (most family like) and in close proximity to the parents’
  home. [^5]

## Cook County

- A value of Cook County was defined as county codes *016* (Cook County)
  and *105* (City of Chicago).

## Cook region

- A value of Cook region was defined as regions *2B, 6A, 6B, 6C, 6D and
  6J*. All other regions were defined as NOT COOK.

## County

### Table 1: County ID and County Name

Table 1 shows the county names and codes used in the BH/CFSR indicators
(see id_grp=COUNTYCD in SACWIS.code_desc).

| ID  | County                            |
|-----|-----------------------------------|
| 1   | Adams                             |
| 2   | Alexander                         |
| 3   | Bond                              |
| 4   | Boone                             |
| 5   | Brown                             |
| 6   | Bureau                            |
| 7   | Calhoun                           |
| 8   | Carroll                           |
| 9   | Cass                              |
| 10  | Champaign                         |
| 11  | Christian                         |
| 12  | Clark                             |
| 13  | Clay                              |
| 14  | Clinton                           |
| 15  | Coles                             |
| 16  | Cook                              |
| 17  | Crawford                          |
| 18  | Cumberland                        |
| 19  | De Kalb                           |
| 20  | De Witt                           |
| 21  | Douglas                           |
| 22  | Du Page                           |
| 23  | Edgar                             |
| 24  | Edwards                           |
| 25  | Effingham                         |
| 26  | Fayette                           |
| 27  | Ford                              |
| 28  | Franklin                          |
| 29  | Fulton                            |
| 30  | Gallatin                          |
| 31  | Greene                            |
| 32  | Grundy                            |
| 33  | Hamilton                          |
| 34  | Hancock                           |
| 35  | Hardin                            |
| 36  | Henderson                         |
| 37  | Henry                             |
| 38  | Iroquois                          |
| 39  | Jackson                           |
| 40  | Jasper                            |
| 41  | Jefferson                         |
| 42  | Jersey                            |
| 43  | Jo Daviess                        |
| 44  | Johnson                           |
| 45  | Kane                              |
| 46  | Kankakee                          |
| 47  | Kendall                           |
| 48  | Knox                              |
| 49  | Lake                              |
| 50  | La Salle                          |
| 51  | Lawrence                          |
| 52  | Lee                               |
| 53  | Livingston                        |
| 54  | Logan                             |
| 62  | McDonough                         |
| 63  | McHenry                           |
| 64  | McLean                            |
| 55  | Macon                             |
| 56  | Macoupin                          |
| 57  | Madison                           |
| 58  | Marion                            |
| 59  | Marshall                          |
| 60  | Mason                             |
| 61  | Massac                            |
| 65  | Menard                            |
| 66  | Mercer                            |
| 67  | Monroe                            |
| 68  | Montgomery                        |
| 69  | Morgan                            |
| 70  | Moultrie                          |
| 71  | Ogle                              |
| 72  | Peoria                            |
| 73  | Perry                             |
| 74  | Piatt                             |
| 75  | Pike                              |
| 76  | Pope                              |
| 77  | Pulaski                           |
| 78  | Putnam                            |
| 79  | Randolph                          |
| 80  | Richland                          |
| 81  | Rock Island                       |
| 88  | St. Clair                         |
| 82  | Saline                            |
| 83  | Sangamon                          |
| 84  | Schuyler                          |
| 85  | Scott                             |
| 86  | Shelby                            |
| 87  | Stark                             |
| 89  | Stephenson                        |
| 90  | Tazewell                          |
| 91  | Union                             |
| 92  | Vermilion                         |
| 93  | Wabash                            |
| 94  | Warren                            |
| 95  | Washington                        |
| 96  | Wayne                             |
| 97  | White                             |
| 98  | Whiteside                         |
| 99  | Will                              |
| 100 | Williamson                        |
| 101 | Winnebago                         |
| 102 | Woodford                          |
| 103 | Out of state                      |
| 104 | Unknown                           |
| 105 | City of Chicago                   |
| 106 | Out of country                    |
| 107 | Dept of corrections               |
| 108 | Other state funded public schools |
| 999 | Missing                           |

### Table 2: Rules and Sources in the BH Report

Table 2 shows the source BH tables and decision rules for the county
used in each BH/CFSR indicator.

<table>
<thead>
<tr class="header">
<th><p>Indicator</p></th>
<th><p>Title</p></th>
<th><p>Source Table</p></th>
<th><p>Rule</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1A</p></td>
<td><p>Maltreatment Recurrence (CFSR)</p></td>
<td><p>cps_inv</p></td>
<td><p>County where the initial indicated allegation occurred</p></td>
</tr>
<tr class="even">
<td><p>1B</p></td>
<td><p>Maltreatment Among Children in Intact Family Cases</p></td>
<td><p>cyc_famcase</p></td>
<td><p>County where the family case was opened</p></td>
</tr>
<tr class="odd">
<td><p>1C</p></td>
<td><p>Maltreatment Recurrence Among Children Receiving No
Services</p></td>
<td><p>cps_inv</p></td>
<td><p>County where the initial indicated allegation occurred</p></td>
</tr>
<tr class="even">
<td><p>1D</p></td>
<td><p>Maltreatment in Substitute Care (CFSR)</p></td>
<td><p>master_event_legal</p></td>
<td><p>County of the initial placement</p></td>
</tr>
<tr class="odd">
<td><p>2A1-2A6</p></td>
<td><p>Initial Placement</p></td>
<td><p>master_event</p></td>
<td><p>County of the initial placement</p></td>
</tr>
<tr class="even">
<td><p>2B1-2B7</p></td>
<td><p>End of Year Placement</p></td>
<td><p>master_event</p></td>
<td><p>County of the placement placed on June 30 (end of the fiscal
year)</p></td>
</tr>
<tr class="odd">
<td><p>2C</p></td>
<td><p>Initial Placement with Siblings</p></td>
<td><p>master_event</p></td>
<td><p>County of the initial placement</p></td>
</tr>
<tr class="even">
<td><p>2D</p></td>
<td><p>End of Year Placement with Siblings</p></td>
<td><p>master_event</p></td>
<td><p>County of the placement placed on June 30 (end of the fiscal
year)</p></td>
</tr>
<tr class="odd">
<td><p>2E</p></td>
<td><p>Placement Stability (CFSR)</p></td>
<td><p>hmr_monitor</p></td>
<td><p>County of the initial placement</p></td>
</tr>
<tr class="even">
<td><p>2F</p></td>
<td><p>Children Who Run Away from Substitute Care</p></td>
<td><p>master_event</p></td>
<td><p>County of the initial placement</p></td>
</tr>
<tr class="odd">
<td><p>2G</p></td>
<td><p>Median Length of Stay in Substitute Care</p></td>
<td><p>master_event</p></td>
<td><p>County of the placement when exiting the substitute care</p></td>
</tr>
<tr class="even">
<td><p>3A1-3A3</p></td>
<td><p>Reunification (within 12, 24, &amp; 36 months)</p></td>
<td><p>master_event</p></td>
<td><p>12 month: use permanence county if the child achieved permanence
within 12 month, otherwise use county of the placement at 12 month time
point;<br />
24 month: use permanence county if the child achieved permanency within
24 month, otherwise use county of the placement at 24 month time
point;<br />
36 month: use permanence county if the child achieved permanency within
36 month, otherwise use county of the placement at 36 month time
point.</p></td>
</tr>
<tr class="odd">
<td><p>3B1-3B4</p></td>
<td><p>Stability of Reunification (1, 2, 5, &amp; 10 years)</p></td>
<td><p>master_event</p></td>
<td><p>County of the permanence</p></td>
</tr>
<tr class="even">
<td><p>3C1, 3C2</p></td>
<td><p>Adoption (within 24 &amp; 36 months)</p></td>
<td><p>master_event</p></td>
<td><p>24 month: use permanence county if the child achieved permanency
within 24 month, otherwise use county of the placement at 24 month time
point;<br />
36 month: use permanence county if the child achieved permanency within
36 month, otherwise use county of the placement at 36 month time
point.</p></td>
</tr>
<tr class="odd">
<td><p>3D1-3D3</p></td>
<td><p>Stability of Adoption (at 2, 5, &amp; 10 years)</p></td>
<td><p>master_event</p></td>
<td><p>County of the permanence</p></td>
</tr>
<tr class="even">
<td><p>3E1, 3E2</p></td>
<td><p>Guardianship (within 24 &amp; 36 months)</p></td>
<td><p>master_event</p></td>
<td><p>24 month: use permanence county if the child achieved permanency
within 24 month, otherwise use county of the placement at 24 month time
point;<br />
36 month: use permanence county if the child achieved permanency within
36 month, otherwise use county of the placement at 36 month time
point.</p></td>
</tr>
<tr class="odd">
<td><p>3F1-3F3</p></td>
<td><p>Stability of Guardianship (at 2, 5 &amp; 10 years)</p></td>
<td><p>master_event</p></td>
<td><p>County of the permanence</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Living with Relatives (within 24 &amp; 36 months)</p></td>
<td><p>master_event</p></td>
<td><p>24 month: use permanence county if the child achieved permanency
within 24 month, otherwise use county of the placement at 24 month time
point; 36 month: use permanence county if the child achieved permanency
within 36 month, otherwise use county of the placement at 36 month time
point.</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Stability of Permanence – Living with Relatives (at 2, 5 &amp; 10
years)</p></td>
<td><p>master_event</p></td>
<td><p>County of the permanence</p></td>
</tr>
</tbody>
</table>

<hr>

## Disproportionality

- The underrepresentation or overrepresentation of a racial or ethnic
  group compared to its percentage in the total population.[^6]
- It refers to a group’s representation in a particular category that
  exceeds expectations for that group, or differs substantially from the
  representation of others in that category.
  \[<https://www.nasponline.org/resources-and-publications/resources-and-podcasts/diversity/disproportionality#>:\~:text=Disproportionality%20refers%20to%20a%20group's,of%20others%20in%20that%20category.\]

## Emergency foster home (EFH)

- For the initial placement indicators, a child who enters an emergency
  foster home and stays in EFH for 8 days or longer is counted in the
  *B.H.* report.
- For the end-of-year placement indicators, a child placed in EFH at the
  end of the fiscal year is counted in the *B.H.* report.
- Emergency Foster Home used to be under "traditional foster homes." In
  January, 2018, we decided to include EFH under "emergency shelter"
  category.
- If the type of service arrangement is coded as one of the following
  service payment codes, the placement is defined as an emergency foster
  home.

| cd_type_serv | Description                              |
|--------------|------------------------------------------|
| 104          | Dept Emergency Foster Care               |
| 123          | C-13 Emergency Foster Care               |
| 178          | Agency Foster Care / Shelter Care        |
| 911          | POS Emergency Foster Care Base Code      |
| 5104         | Lic Dept Non-Hmr Emergency In Pa Home    |
| 5192         | Lic Dept Hmr Emergency In Pa Home        |
| 6011         | POS Emer Fost Care-Unlic Non Relative    |
| 6104         | Unlicensed Non-Related Dept Emergency    |
| 6186         | Pos Emer Fost Care-Unlic Adm Vch Pay     |
| 6904         | HMR Child In Unlicensed Emergency FC     |
| 6911         | POS Emer Fost Care-Unlic Relative        |
| 8104         | Appealed Non-Related Dept Emergency      |
| 8904         | HMR Child In Appealed Emergency FC       |
| 9011         | POS Emer Fost Care-Licensed Non Relative |
| 9104         | Licensed Non-Related Emergency FC        |
| 9904         | HMR Child In Licensed Emergency FC       |
| 9911         | POS Emer Fost Care-Licensed Relative     |

- Alternatively, if living arrangement type is coded as an emergency
  foster care (EFC) and there was no type of service code, the the
  placement is defined as EFC.

## Emergency shelter

- Emergency shelters provide temporary living arrangements for children
  if no other possible foster home placements can be arranged. IL DCFS
  policy states that placements in emergency shelters should not exceed
  30 calendar days.[^7]
- For the initial placement indicators, a child who enters an emergency
  shelter and stays in the emergency shelter for 8 days or longer is
  counted in the *B.H.* report.
- For the end-of-year placement indicators, a child placed in an
  emergency shelter at the end of the fiscal year is counted in the
  *B.H.* report.
- If the type of service arrangement is coded as one of the following
  service payment codes, the placement is defined as an emergency
  shelter.

| cd_type_serv | Description                              |
|-------------|-----------------------------------------|
| 178          | Agency Foster Care / Shelter Care        |
| 221          | Emergency Shelters - Institutions        |
| 222          | Emergency Shelter - Group Home           |
| 223          | Youth Emergency Shelters                 |
| 7221         | Medicaid-Emergency Shelters-Institutions |

- Alternatively, if living arrangement type is coded as (a) either youth
  emergency shelter (YES) or shelter (SHL) and (b) there was no type of
  service code, the the placement is defined as an emergency shelter.

## Ethnicity

- The ethnicity variable includes 13 codes designating Hispanic origin
  (see SACWIS.code_desc table for more details; id_grp=ETHNCITY). The
  codes are:
  - 'NH' for Not Hispanic
  - 'HS' for Hispanic South American
  - 'HC' for Hispanic Cuban
  - 'HM' for Hispanic Mexican
  - 'HP' for Hispanic Puerto Rican
  - 'HD' for Hispanic Spanish Descent
  - 'NR' for Not reported (note that currently it is not in use)
  - 'HO' for Hispanic Other
  - 'HN' for Hispanic Dominican
  - 'HA' for Hispanic Central American
  - 'DI' for Declined to Identify
  - 'CV' for Could not be verified
  - 'UK' for Unknown

<!-- -->

- If the ethnicity code is either 'HA', 'HC', 'HM', 'HN', 'HP', 'HS',
  'HD', or 'HO,' the person is coded as Hispanic. After that, we combine
  this variable with the [race](BH_Data#Race) variable to
  create the [race/ethnicity](BH_Data#Race/Ethnicity)
  variable for *B.H.* report.

## End of year placement

- The substitute care that a child was staying on the last day of the
  state fiscal year (June 30).

## Event

- The "event" field includes a placement where a child was placed to.
  See the DATAREF.event_xref table for more updates.

| ID | Event                                                                              |
|----|------------------------------------------------------------------------------------|
| 01 | [Home of parent (HMP)](BH_Data#Home_of_parent_(HMP))                    |
| 02 | Kinship foster home                                                                |
| 03 | Adoptive placement                                                                 |
| 04 | [Traditional foster home](BH_Data#Traditional_foster_home_(TFH))        |
| 05 | [Specialized foster home](BH_Data#Specialized_or_treatment_foster_home) |
| 06 | [Group home](BH_Data#Group_home_(GH))                                   |
| 07 | [Institution](BH_Data#Institution)                                      |
| 08 | Adoption subsidy                                                                   |
| 09 | [Independent living](BH_Data#Independent_living)                        |
| 10 | Subsidized guardianship                                                            |
| 11 | [Emergency shelter](BH_Data#Emergency_shelter)                          |
| 12 | [Emergency foster home](BH_Data#Emergency_foster_home_(EFH))            |
| 13 | Runaway (RNY), Abducted (ABD), Unknown contact (WCC), Whereabouts                  |
| 14 | Detention/institution (DET, IDC)                                                   |
| 15 | Unauthorized home of parent (UAH), Unauthorized placement (UAP)                    |
| 16 | Deceased (DEC)                                                                     |
| 17 | Hospital/healthcare facility (HHF)                                                 |
| 18 | College university scholarship (CUS), Job training                                 |
| 19 | Armed service duty (ASD), Other (OTH), Unknown (UN                                 |
| 20 | Hospital facility medical (HFM)                                                    |
| 21 | Hospital facility psychiatric (HFP)                                                |
| 22 | Private guardianship home (PGH)                                                    |

The BH indicators with event exclusions are shown in the table below.

| Indicator name                                                           | BH indicators program       | Event excluded                         |
|--------------------------------------------------------------------------|-----------------------------|----------------------------------------|
| Maltreatment Recurrence                                                  | ind1ac_cfsr_malt_recur      |                                        |
| Maltreatment Among Children in Intact Family Cases                       | ind1b_cfsr_maltreat_intact  |                                        |
| Maltreatment Recurrence Among Children Receiving No Services             | ind1ac_cfsr_malt_recur      |                                        |
| Maltreatment in Substitute Care                                          | CFSR_number_of_days_V2      |                                        |
| Initial Placement                                                        | in2a_ini_placetype          | 03 08 10 22 13 15 16 17 18 19 20 21 09 |
| End of Year Placement                                                    | ind2b_eoy_placetype         | 03 08 10 22 13 15 16 17 18 19 20 21 09 |
| Initial Placement with Siblings                                          | ind2c_ini_sibling           | 03 08 10 22 13 15 16 17 18 19 20 21 09 |
| End of Year Placement with Siblings                                      | ind2d_eoy_sibling           | 03 08 10 22 13 15 16 17 18 19 20 21 09 |
| Placement Stability                                                      | CFSR_stability_V3           | 01 03 08 10 16 18 19 22 typecode='RNY' |
| Children Who Run Away from Substitute Care                               | ind2f_runaway_1styr         | 03 08 10 22 13 15 16 17 18 19 20 21 09 |
| Median Length of Stay in Substitute Care                                 | ind2g_lengthofstay          | 03 08 10 22 13 15 16 17 18 19 20 21 09 |
| Exit to Permanence                                                       | ind3aceg_exittoperm         | 03 08 10 13 15 16 17 18 19 20 21 22 09 |
| Stability of Reunification                                               | ind3b_permstab_reunify      |                                        |
| Stability of Adoption                                                    | ind3d_permstab_adopt        |                                        |
| Stability of Guardianship                                                | ind3f_permstab_gship        |                                        |
| Permanency in 12 months for Children Enterting Substitue Care            | ind3g_cfsr_exit_to_perm12   | censors 3 and 4                        |
| Permanency in 12 Months for Children in Care 12 to 23 Months             | ind3hi_cfsr_exit_to_perm    | censors 3 and 4                        |
| Permanency in 12 Months for Children in Care 24 Months or More           | ind3hi_cfsr_exit_to_perm    | censors 3 and 4                        |
| Re-Entry to Substitute Care Among Children in Care Less Than 12 Months   | ind3j_cfsr_reentry_12       |                                        |
| Re-Entry to Substitute Care Among Children in Care for 12 to 23 Months   | ind3k_cfsr_reentry_12to23   |                                        |
| Re-Entry to Substitute Care Among Children in Care for 24 or More Months | ind3l_cfsr_reentry_24ormore |                                        |

## Exit from substitute care

- Some children exit from substitute care to achive legal permanence
  (i.e., adoption, reunification, guardianship, and living with
  relatives). Others exit substitute care without ever achieving legal
  permanence (e.g., aged out, entering a hospital or institution,
  independent living, incarcerated, runaway, death, other setting).
- Read [Otherwise exit](BH_Data#Otherwise_exit) for more
  details about other exit type without ever achieving legal permanence.
- The coding scheme for "non-permanency exit from substitute care" was
  changed to the following in November, 2017.

`If censor=4 and endevent in ('FHA','FHI','FHP','FHS','FHB','HMR','ZZZ','OTH','UNK','UAP','UAH','ASD') and agelastpl >= 17 then exittype='Aged Out ';`
`else if censor=4 and endevent in ('HHF','IPA','NCF','GRH','IMH','IRS','ICF') then exittype='Hosp/Inst';`
`else if censor=4 and endevent in ('ILO','CIL','TLP','YIC','JTP','YIE','CUS',) then exittype='Ind Liv';`
`else if censor=4 and endevent in ('DET','IDC') then exittype='Incarcerated';`
`else if censor=4 and endevent in ('RNY','ABD','WUK','WCC') then exittype='Runaway';`
`else if censor=4 and endevent in ('DEC') then exittype='Death';`
`else if censor=4 and endevent in ('FHA','FHI','FHP','FHS','HMR','OTH','ZZZ','UNK','FHB','UAP','DRA') then exittype='Other';`

- Note that we categorized YIE, CUS into independent living.
- Also note that we added FHB to aged out.

## Fictive kin

- A fictive kin is a person who has close personal or emotional ties
  with the child or the child’s family prior to the child’s placement
  with the person. The Placing Worker shall ask the parents and the
  child to identify fictive kin who may be able to serve as a caregiver
  for a child entering substitute care, and shall again inquire, as
  appropriate, any time a child in care requires a new foster home
  placement. <ref name="procedures301">Illinois Department of Children
  and Family Services. (2016). Procedures 301, Placement and Visitation
  Services. Springfield: Author. Retrieved from
  <https://www2.illinois.gov/dcfs/aboutus/notices/Documents/Procedures_301.pdf>

</ref>

## Fiscal year (FY)

- A fiscal year is a 12-month period used by governments. A fiscal year
  starting on July 1, 2018, and ending on June 30, 2019, refers to the
  fiscal year 2019, or FY2019.

## Gender

- Child gender is categorized as Female or Male. Children for whom
  gender is not coded are reported as having a Missing gender and
  excluded from the percent calculations in the gender category.

## Group home (GH)

- It refers to a non-family, community-based residence that houses more
  children than are permitted to reside in a foster family home, but
  fewer than reside in a residential treatment center (in Illinois, the
  number of children in a group home is limited to 10 or fewer). Group
  homes are operated by professional staff who work in rotating
  shifts.[^8]
- For the initial placement indicators, a child who enters GH and stays
  in GH for 8 days or longer is counted in the *B.H.* report.
- For the end-of-year placement indicators, a child placed in GH at the
  end of the fiscal year is counted in the *B.H.* report.
- If the type of service arrangement is coded as one of the following
  service payment codes, the placement is defined as a group home.

| cd_type_serv | Description                     |
|--------------|---------------------------------|
| 203          | Private Group Homes             |
| 233          | Performance Group Home          |
| 7202         | Med GH Fee For Service          |
| 7203         | Medicaid/Private Group Homes    |
| 7233         | Performance Medicaid Group Home |

- Alternatively, if living arrangement type is coded as Group Home (GRH)
  and there was no type of service code, the the placement is defined as
  group home.

## Guardianship

- It refers to subsidized guardianship, which is a program that provides
  financial assistance for caregivers who take legal guardianship of
  children who can no longer live with their parents. ([Children's
  Bureau](https://www.childwelfare.gov/))

## Home of parent (HMP)

- Placement of children with the non-offending parent or in the home of
  the parent(s) prior to reunification or termination of child welfare
  services. When home of parent is used as a placement, DCFS retains
  legal responsibility for the child.[^9]
- Since FY2018, Home of Parent has been included as a placement type in
  the calculation of several indicators related to placement in
  substitute care. Children in HMP with an “AA” (adoption assistance)
  open code are excluded from the initial placements. Children whose
  legal custody is DCFS and the placement type is HMP are included in
  the out-of-home placements when we calculate the end-of-year
  placements, regardless of their open code status.
- Prior to FY2018, HMP was not considered as an out-of-home placement
  type.

## Independent living

- Independent living placements are distinct from substitute care
  placements. According to DCFS policy guides, independent living
  services are defined as “casework and other supportive services that
  are provided to assist eligible youth living in an apartment in the
  community to prepare for transition to adulthood and self-sufficiency,
  and establish (or reestablish) legal relationships and/or permanent
  connections with committed adults.” "This program level is developed
  for youth over 19 years of age who have demonstrated the capacity for
  economic self-sufficiency, graduated from an accredited high school or
  obtained a GED, and are employed or employable." [^10]
- If the type of service arrangement is coded as one of the following
  service payment codes, the placement is defined as an independent
  living placement.

| cd_type_serv | Description                              |
|--------------|------------------------------------------|
| 163          | Pregnant Parenting Teen-I.L.O.-18 / Over |
| 167          | Pregnant Parenting Teen-I.L.V            |
| 204          | Supervised Independent Living            |
| 208          | Refugee Assistance Supervised Ila        |
| 225          | Cila-Community-Integ.Living Arrangement  |
| 244          | Out Of Home-Supervised Ind Liv - Non-Med |
| 267          | ILO/PPT                                  |
| 268          | TLP 1                                    |
| 277          | TLP/PPT                                  |
| 278          | TLP 2                                    |
| 291          | Contracted Over 21 Placement Costs       |
| 292          | Non Contracted Over 21 Placement Costs   |
| 294          | TLP/DD                                   |
| 295          | TLP/MI                                   |
| 296          | TLP/SBP                                  |
| 297          | TLP/JJ                                   |
| 298          | TLP 3                                    |
| 701          | Youth In Transition / Grants             |
| 704          | Cuban/Haitian-Youth In Transition/Grants |
| 705          | Other Refugee-Youth In Transition/Grants |
| 706          | Youth In Transition / Grants / Cus       |
| 708          | Employee Incentive Program/Grant         |
| 720          | Youth In College / Grants                |
| 723          | Cuban/Haitian - Youth In College Grants  |
| 724          | Other Refugee - Youth In College Grants  |
| 725          | Youth In College / Grants                |
| 730          | Self Selected Placements/Ind Living      |
| 801          | Department Scholarship Living Exp        |
| 804          | Cuban/Haitian - Department Scholarship   |
| 805          | Other Refugee - Department Scholarship   |
| 806          | Department Scholarship Living Exp        |
| 6167         | Pregant Parenting Teen-Ilv Unlic,Unrelat |
| 6967         | Pregant Parenting Teen-Ilv Unlic,Related |
| 7167         | Medicaid/Pregnant Parenting Teen-Ilv     |
| 7204         | Medicaid/Supervised Independent Living   |
| 7205         | Medicaid-Independent Living Fee For Ser  |
| 7267         | Ilo/Ppt Medicaid                         |
| 7268         | Medicaid Tlp 1                           |
| 7278         | Medicaid Tlp 2                           |
| 7291         | Medicaid Pos Case Over 21 Years Of Age   |
| 7293         | Medicaid Performance Contracted Over 21  |
| 7296         | Medicaid Tlp/Sbp                         |
| 7298         | Medicaid Tlp 3                           |
| 7767         | Medicaid Preg Parent Teen-Ilv Lic Unrelt |
| 9167         | Pregant Parenting Teen-Ilv Licns Unreltd |
| 9967         | Pregant Parenting Teen-Ilv Licns Related |

- Alternatively, if living arrangement type is coded as either 'ILO,'
  'CIL,' or 'TLP' and there was no type of service code, the the
  placement is defined as an independent living.

## Indicated

- An investigation of suspected child abuse/neglect has revealed
  credible evidence that the abuse/neglect occurred.
  <ref name="IDCFS2017">

Illinois Department of Children and Family Services. (2017). Child
abuse/neglect statistics. Springfield: Author. Retrieved from
<https://www2.illinois.gov/dcfs/aboutus/newsandreports/Documents/CANStat.pdf#search=indicated%20report>

</ref>

- An investigation report is indicated if the finding is coded 3 in the
  CD_INVST_FIND field in SACWIS.investigation.
- An allegation is indicated if the finding is coded 3 in the CD_FIND
  field in SACWIS.invst.allegation.

## Initial placement

- The substitute care that a child first entered within a given fiscal
  year.

## Institution

- All non-family settings, except for group home, are combined into a
  broad category called institutions in *B.H.* report. This category
  includes a variety of congregate care placements such as residential
  treatment centers, detention centers, hospitals, and other health
  facilities. [^11]
- For the initial placement indicators, a child who enters an
  institution and stays in the institution for 8 days or longer is
  counted in the *B.H.* report.
- For the end-of-year placement indicators, a child placed in an
  institution at the end of the fiscal year is counted in the *B.H.*
  report.
- If the type of service arrangement is coded as one of the following
  service payment codes, the placement is defined as an institution.

| cd_type_serv | Description                              |
|--------------|------------------------------------------|
| 201          | Private Institutions                     |
| 202          | Other Institutions                       |
| 206          | DCFS Institution - Allowance             |
| 207          | DHS Institution Allowance                |
| 210          | Crisis Institutional Care                |
| 213          | C-13 Private Institutions                |
| 216          | DMH,DORS,DPH,INST.Allow,CUB/HTN Refugee  |
| 217          | DHS Institution Allowance Other Refugees |
| 231          | Performance Institution                  |
| 240          | Out Of Home - INST/GH - Non-Medicaid     |
| 251          | David B. Consent Order/Board             |
| 293          | Performance Contracted Over 21 Placement |
| 901          | Maternity Home Care                      |
| 7201         | Medicaid/Private Institutions            |
| 7231         | Performance Medicaid Institution         |
| 7240         | Out Of Home - INST/GH - Medicaid         |
| 7251         | Medicaid David B.Consent Order           |

- Alternatively, if living arrangement type is coded as one of the codes
  below and there was no type of service code, the placement is defined
  as an institution.
  - Institution - DCFS (ICF)
  - Institution - Dept of Mental Health (IMH)
  - Institution (INS)
  - Institution Other Public (IOP)
  - Institution Rehabilitation Services (IRS)
  - Nursing Care Facility (NCF)
  - Institution Private Shelter (IPS)

## Intact family case

- An intact family service case can be opened in several
  circumstances: 1) following an indicated investigation when no
  children are removed and the parents voluntarily accept services; 2)
  following an indicated investigation with a court order if the family
  refuses to accept the services; 3) during a pending investigation if
  the family has an identified service need; 4) when a child returns
  home after being in placement less than 30 days (protective custody
  lapse); and 5) following an unfounded investigation per DCFS request
  or court order. The goal of intact family services is to mitigate the
  identified risk factors in 6 to 12 months. <ref name="rb_cerap">
  Fuller, T. L., Chiu, Y., Wakita, S., & Nieto, M. (2018). Understanding
  Safety Assessment in Illinois: CERAP Completion in Intact Family
  Services. Urbana, IL: Children and Family Research Center, University
  of Illinois at Urbana-Champaign.

</ref>

- Any service provided to the family while the child remains in the
  home. Children remains at home while the family receives supportive
  services rather than being placed into substitute care. Services may
  be provided directly in the child's home or a professional setting.
- In some instances, the Department will indicate a family for child
  maltreatment, but decide that it is in the best interest of the child
  and family to receive services at home rather than place the child
  into substitute care.[^12]
- In-home services offered to DCFS-referred families focused on
  providing education and case management in order to prevent children
  from entering foster care. Intact services are most often voluntary
  but may also be court-ordered, and can provide in-home counseling,
  crisis response, and linkage to appropriate treatment programs (e.g.,
  substance abuse) or services (e.g., medical clinics, Section 8 housing
  assistance, childcare) at no cost to the family. [^13]
- The intact family case in our CERAP study is defined as one in which
  all children remained in the home on the case opening date. In other
  words, no children were removed from the home and placed into
  substitute care. Intact family cases that were open for 7 days or less
  were excluded from the intact family case data. Cases where children
  in the family entered substitute care within 30 days of the case open
  date were also excluded from the intact family case data. [^14]

## Kinship foster home

- It involves placement of children with relatives in the relatives'
  homes. Relatives are the preferred placement for Children who must be
  removed from their parents, as this kind of placement maintains the
  children's connections with their families. In Illinois, kinship care
  providers may be licensed or unlicensed.[^15]
- For the initial placement indicators, a child who enters a kinship
  foster home and stays in the kinship foster home for 8 days or longer
  is counted in the *B.H.* report.
- For the end-of-year placement indicators, a child placed in a kinship
  foster home at the end of the fiscal year is counted in the *B.H.*
  report.
- If the type of service arrangement is coded as one of the following
  service payment codes, the placement is defined as a kinship foster
  home.

| cd_type_serv | Description                              |
|--------------|------------------------------------------|
| 106          | Dept Home Of Relative                    |
| 115          | Dept Reduced Rate Relative Home          |
| 136          | Department Delegated Relative Authority  |
| 137          | Agency Delegated Relative Authority      |
| 140          | Agency Relative Foster Care              |
| 141          | Agency Relative F. C. / Adimin. Only     |
| 153          | Dept Hmr - Cuban/Haitian Refugee         |
| 154          | Dept Hmr - Other Refugee                 |
| 160          | Frs - Private Agency Relative Homes      |
| 161          | Frs - Dept. Relative Homes               |
| 176          | Sibling Visitation-Supervision Only      |
| 2140         | Agency Relative F.C./Perf.Based Cont.    |
| 2160         | Frs-Priv.Ag Rel Homes/Perf.Based Cont.   |
| 2640         | Unapp.Private Ag Hmr/Perf.Based Cont.    |
| 2660         | Unap Frs-Priv Ag Rel Hm/Perf.Based Cont. |
| 2840         | App Priv Ag Hmr/Perf.Based Cont.         |
| 2860         | App Frs-Priv Ag Rel Hm/Perf.Based Cont.  |
| 2940         | Hmr In Lic Priv Ag Bd Hm/Perf.Based Cont |
| 2960         | Hmr In Lic Frs-Priv Ag Fc/Perf.Base Cont |
| 3106         | Dept Hmr In Ap Private Agency Home       |
| 3136         | Dept Hmr Del Rel Auth In Unapproved Pa H |
| 3153         | Dept Hmr-Cuban Haitian In Unap Pa Home   |
| 3154         | Dept Hmr Other Refugee In Unap Pa Home   |
| 3161         | Unapproved Dept Hmr Frs In Pa Home       |
| 3640         | Unlic Priv Ag Hmr/Pcs Cont               |
| 4106         | Dept Hmr In Unapproved Private Agy Home  |
| 4136         | Dept Hmr Del Rel Auth In Ap Pa Home      |
| 4140         | Lic Priv Ag Hmr/Pcs Cont                 |
| 4153         | Dept Hmr-Cuban Haitian In Ap Pa Home     |
| 4154         | Dept Hmr-Other Refugee In Ap Pa Home     |
| 4161         | Approved Dept Hmr Frs In Fp Home         |
| 5106         | Dept Hmr In Licensed Pa Home             |
| 5115         | Lic Dept Hmr Reduced Rate In Pa Home     |
| 5136         | Dept Hmr Del Rel Auth In Lic Pa Home     |
| 5153         | Dept Hmr Cuban Haitian In Lic Pa Home    |
| 5154         | Dept Hmr Other Refugee In Lic Pa Home    |
| 5191         | Dept Hmr Intensive In Pa Home            |
| 6106         | Unapproved Dept Hmr                      |
| 6115         | Unapproved Reduced Rate Relative Home    |
| 6136         | Unapproved Dept Delegated Relative Auth  |
| 6137         | Unapproved Agency Delegated Rel Auth     |
| 6140         | Unapproved Private Agency Hmr            |
| 6153         | Unapproved Hmr Cuban Haitian Refugee     |
| 6154         | Unapproved Hmr - Other Refugee           |
| 6160         | Unap Frs - Private Agency Relative Home  |
| 6161         | Unapproved Frs-Department Relative Home  |
| 8106         | Approved Department Hmr                  |
| 8115         | Approved Reduced Rate Relative Home      |
| 8136         | Approved Dept Delegated Relative Auth    |
| 8137         | Approved Agency Delegated Relative Auth  |
| 8140         | Approved Private Agency Hmr              |
| 8153         | Approved Hmr - Cuban Haitian Refugee     |
| 8154         | Approved Hmr - Other Refugee             |
| 8160         | Approved Frs-Private Agency Relative Hm  |
| 8161         | Approved Frs-Department Relative Home    |
| 9106         | Hmr In Lic Department Boarding Home      |
| 9115         | Hmr In Lic Dept Reduced Rate Foster Care |
| 9136         | Hmr In Lic Dept Delegated Relative Auth  |
| 9137         | Hmr In Lic Agncy Delegated Relative Auth |
| 9140         | Hmr In Lic Private Agency Boarding Home  |
| 9153         | Hmr In Lic Dept Home - Cuban Haitian Ref |
| 9154         | Hmr In Lic Dept Home - Other Refugee     |
| 9160         | Hmr In Lic Frs-Private Agency Fc         |
| 9161         | Hmr In Lic Frs-Dept Regular Foster Care  |

- Alternatively, if living arrangement type is coded as a) either
  'DRA'(Delegated Relative Author), 'HMR'(Home of Relative), 'HRA'(Home
  of Relative Applicant), 'HRL'(Home of Relative Licensed), or
  'HFK'(Home of Fictive Kin) and b) there was no type of service code,
  then the placement is defined as kinship foster home.

## Legal permanence

- The term legal permanence implies a desired permanence, and that is
  what we focused on the *B.H.* report. For instance, “aged out” is not
  a desired permanency outcome. We also began using children’s legal
  status by using the master_spell_lgl. Reunification is achieved when
  the child is returned home and (a) the legal custody is transferred
  back to parent(s) or (b) the placement case is closed. If the child is
  returned home, his/her legal custody is not transferred and the
  placement case is open (i.e., not legally permanent), it is considered
  as “still in care.”

## Living arrangement code (livarcd)

- Refers to a child's living arrangement type code.

| Code | Description                                                                                                                                                                                                                                                                                        | Added |
|------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------|
| ABD  | Abducted - the child's whereabouts are unknown and the child is known or believed concealed detained or removed from the jurisdiction of the court.                                                                                                                                                |       |
| ASD  | Armed Service Duty                                                                                                                                                                                                                                                                                 |       |
| CIL  | Community Integrated Living Arrangement - This code is to be used for developmental disabled youth 18 years of age or older that have been placed in a CIL approved by the Dept and the IL Dept of Human Services. The Central Office Payment Unit may only enter the CIL living arrangement code. |       |
| CUS  | College/University Scholarship-DCFS Scholarship Only - This living arrangement code may only be entered by the Central Office Payment Unit                                                                                                                                                         |       |
| DEC  | Deceased - This code is used to report the death of a child when the Dept has an open case and legal responsibility for the child.                                                                                                                                                                 |       |
| DET  | Detention Facility/Jail                                                                                                                                                                                                                                                                            |       |
| DRA  | Delegated Relative Authority                                                                                                                                                                                                                                                                       |       |
| EFC  | Emergency Foster Home                                                                                                                                                                                                                                                                              | 2017  |
| FHA  | Foster Home Adoptive                                                                                                                                                                                                                                                                               |       |
| FHB  | Foster Home Boarding - DCFS                                                                                                                                                                                                                                                                        |       |
| FHG  | Foster Home Guardianship                                                                                                                                                                                                                                                                           | 2017  |
| FHI  | Foster Home Indian - Licensed Specified or approved by an Indian child's tribe                                                                                                                                                                                                                     |       |
| FHP  | Foster Home Boarding - Private Agency                                                                                                                                                                                                                                                              |       |
| FHS  | Foster Home Specialized                                                                                                                                                                                                                                                                            |       |
| FOS  | Foster Home                                                                                                                                                                                                                                                                                        |       |
| GDN  | Guardian (Successor) - This program is only offered if they are in a cost-neutrality area described in Rules 302 Section 302.405.                                                                                                                                                                  |       |
| GRH  | Group Home                                                                                                                                                                                                                                                                                         |       |
| HAP  | Home Adoptive Parents - This code is used to report the final living arrangement after adoption is completed. When using this code do not make an entry for name and address.                                                                                                                      |       |
| HFK  | Home of Fictive Kin                                                                                                                                                                                                                                                                                |       |
| HFM  | Hospital Facility Medical                                                                                                                                                                                                                                                                          | 2017  |
| HFP  | Hospital Facility Psychiatric                                                                                                                                                                                                                                                                      | 2017  |
| HHF  | Hospital/Health Facility                                                                                                                                                                                                                                                                           |       |
| HMR  | Home of Relative                                                                                                                                                                                                                                                                                   |       |
| HMP  | Home of Parent - Used also for Adoption Assistance cases                                                                                                                                                                                                                                           |       |
| HRA  | Home of Relative Applicant                                                                                                                                                                                                                                                                         |       |
| HRL  | Home of Relative Licensed                                                                                                                                                                                                                                                                          |       |
| ICF  | Institution - DCFS                                                                                                                                                                                                                                                                                 |       |
| IDC  | Institution - Committed to the Department of Corrections                                                                                                                                                                                                                                           |       |
| ILO  | Independent Living Only                                                                                                                                                                                                                                                                            |       |
| IMH  | Institution - Department of Mental Health                                                                                                                                                                                                                                                          |       |
| IND  | Independent Living                                                                                                                                                                                                                                                                                 |       |
| INS  | Institution                                                                                                                                                                                                                                                                                        |       |
| IOP  | Institution Other Public                                                                                                                                                                                                                                                                           |       |
| IPA  | Institution Private                                                                                                                                                                                                                                                                                |       |
| IPH  | Institution - Private Child Care Facility                                                                                                                                                                                                                                                          |       |
| IPS  | Institute Private Shelter                                                                                                                                                                                                                                                                          | 2017  |
| IRS  | Institution Rehabilitation Services                                                                                                                                                                                                                                                                |       |
| JTP  | Job Training Program - The child is participating in a recognized job-training program                                                                                                                                                                                                             |       |
| MIS  | Missing Living Arrangement                                                                                                                                                                                                                                                                         |       |
| NCF  | Nursing Care Facility                                                                                                                                                                                                                                                                              |       |
| OTH  | Other                                                                                                                                                                                                                                                                                              |       |
| PGH  | Private Guardianship Home                                                                                                                                                                                                                                                                          |       |
| QRT  | Qualified Residential Treatment                                                                                                                                                                                                                                                                    |       |
| RNY  | Runaway                                                                                                                                                                                                                                                                                            |       |
| SGH  | Subsidized Guardian Home                                                                                                                                                                                                                                                                           |       |
| SHL  | Shelter                                                                                                                                                                                                                                                                                            |       |
| TFH  | Therapeutic Foster Home                                                                                                                                                                                                                                                                            | 2017  |
| TLP  | Transitional Living Program - Placement approved by a Regional Clinical Services Manager                                                                                                                                                                                                           |       |
| UAH  | Unauthorized Home of Parent                                                                                                                                                                                                                                                                        |       |
| UAP  | Unauthorized Placement - The child's whereabouts are known but the child is living in a unauthorized/unapproved placement.                                                                                                                                                                         |       |
| UNK  | Unknown                                                                                                                                                                                                                                                                                            |       |
| WCC  | Whereabouts Unknown Periodic Contact with Caseworker - The child's whereabouts is unknown but the child periodically initiates contacts his or her assigned caseworker.                                                                                                                            |       |
| WUK  | Whereabout Unknown - The child's whereabouts are unknown and the child is not known or believed abducted.                                                                                                                                                                                          |       |
| YES  | Youth Emergency Shelters                                                                                                                                                                                                                                                                           |       |
| YIC  | Youth in College - Placement approved by the Deputy Director of the Division of Educational and Transition Services (This living arrangement code may only be entered by the Central Office Payment Unit.)                                                                                         |       |
| YIE  | Youth in Employment - Placement approved by the Deputy Director of the Division of Eeucational and Transition Services (This living arrangement code may only be entered by the Central Office Payment Unit.)                                                                                      |       |
| QRT  | Qualified Residential Treatment                                                                                                                                                                                                                                                                    | 2021  |

## Median length of stay in substitute care

- The median number of months children stay in substitute care. Length
  of stay is presented in months.
- The median represents the amount of time that it took half of children
  who entered substitute care in a fiscal year to exit care.
- In the BH measure the length of stay in substitute care is calculated
  using the first [spell](BH_Data#Spell) after a child was
  placed in a substitute care. See [Indicator: median length of stay in
  substitute care](BH_Data#ind2g_lengthofstay).
- If the child has more than one spell during the fiscal year, the first
  [spell](BH_Data#Spell) is selected.

## Non-permanency exit

- includes incarceration, aging out, and running away.

## Northern region

- A value of Northern region was defined as regions *1A* (Rockford) and
  *2A* (Aurora).

## Otherwise exit

- A child does not achieve legal permanence and exits the substitute
  care due to the following reasons:
  - child deceased
  - court order release
  - court jurisdiction not taken
  - reached majority
  - service completed
  - other reason

## Permanence (or permanency)

- Every child is entitled to a guardian of the person, either a natural
  guardian by birth or adoption or a legal guardian appointed by the
  court.[^16]
- In the BH measure, children achieve permanency through reunification,
  adoption or guardianship.
- In the CFSR measure, permanency includes discharges from foster care
  to reunification with the child’s parents or primary caregivers,
  living with a relative, guardianship, or adoption. Youth entering at
  age 17 who turn 18 while in care or discharge at age 18 are not
  counted as achieving permanency.

## Permanency exit

- It includes exiting from substitute care due to
  [reunification](BH_Data#Reunification), adoption,
  guardianship, living with relatives, and [otherwise
  exited](BH_Data#Otherwise_exit). A relative assumes legal
  guardianship of a child without receiving a subsidy or becoming
  licensed foster parents.

## Permanency stability

The stability of the permanent placements should be monitored to ensure
that the children who exit substitute care do not re-enter care. The
stability of each type of permanence is monitored by examining the
percentage of reunifications, adoptions, and guardianships that remain
intact (i.e., the children do not re-enter substitute care) within one
year (reunification only), two years, five years, and ten years
post-discharge.

## Perpetrator

- Means a person who, as a result of investigation, has been determined
  by the Department to have caused child abuse or neglect. \[325 ILCS
  5/3\] [^17]

## Placement

- Placement is defined on the bases of two fields from the IDCFS's
  Legacy Golden Copy database: type of service categorization and child
  living arrangement type. In constructing each placement type, type of
  service categorization was given priority over child living
  arrangement type.

## Placement stability

- Of all children who entered substitute care during the fiscal year,
  the rate of placement moves per 1,000 days of care.

## Placement type

There are seven placement types in the *B.H.* report:

- [Home of parent(s)](BH_Data#Home_of_parent)
- [Kinship foster home](BH_Data#Kinship_foster_home)
- [Traditional foster home](BH_Data#Traditional_foster_home)
- [Specialized or treatment foster
  home](BH_Data#Specialized_or_treatment_foster_home)
- [Emergency shelter](BH_Data#Emergency_shelter) or
  [emergency foster
  home](BH_Data#Emergency_foster_home_(EFH))
- [Group home](BH_Data#Group_home)
- [Institution](BH_Data#Institution)

## Protective custody

- Once a determination has been made by child protective services that
  intervention is necessary to safeguard the welfare of a child, the
  next choice that child welfare workers must make is whether the child
  can be safely served in the home or should be taken into protective
  custody and placed in foster care.[^18]

## Race

- There are originally nine race categories. See the SACWIS.code_desc
  table for more details (id_grp=RACECODE).
  - 'NA' for Native American/Alaska Native
  - 'BL' for Black
  - 'AO' for Asian
  - 'PI' for Native Hawaiian/Other Pacific Islander'
  - 'WH' for White; 'DI' for declined to identify
  - 'CV' for could not be verified
  - 'UN' for unknown
  - 'NR' for not reported (note that 'NR' is not currently in use)

<!-- -->

- We look at the primary race category only. Combining with the
  ethnicity information, we recode four race/ethnicity categories. They
  are: Non-Hispanic Black; Non-Hispanic White; Hispanic; and Other.
- "Other" race/ethnicity includes Native American/Alaska Native, Asian,
  and Native Hawaiian/Other Pacific Islanders. If the value of
  race/ethnicity is 'CV', 'UN' , 'DI' or missing (null), it is recoded
  as *missing*.
- For more information about how to code Hispanic, see
  [Ethnicity](BH_Data#Ethnicity).
- For more information about the operational definition of
  race/ethnicity, see
  [Race/Ethnicity](BH_Data#Race/Ethnicity).

## Race/Ethnicity

- The race/ethnicity variable used in the B.H. report was created from
  two variables in the Statewide Automated Child Welfare Information
  System (SACWIS) and the Child and Youth Centered Information System
  (CYCIS): primary race and ethnicity.
- The ethnicity variable includes several codes designating Hispanic
  origin, including Hispanic South American, Hispanic Cuban, Hispanic
  Mexican, Hispanic Puerto Rican, Hispanic Spanish Descent, Hispanic
  Dominican, Hispanic Central American, and Hispanic Other. If the
  individual’s ethnicity was coded as any of these, their race/ethnicity
  in this report was coded as “Hispanic” regardless of the primary race
  code. If the individual’s ethnicity was not of Hispanic origin, their
  race/ethnicity in this report was determined using the code in the
  primary race variable contained in SACWIS and CYCIS.
- Values on the primary race variable include: White, Black, Native
  American/Alaska Native, Asian, and Native Hawaiian/Other Pacific
  Islanders.
- Because the numbers in categories other than White and Black are
  small, they are combined into one category labeled as “other
  race/ethnicity.”
- Note that if the value of primary race was “could not be verified,”
  “unknown,” “declined to identify,” or missing (null), it was treated
  as missing and excluded when indicators are reported by
  race/ethnicity.
- For more information about the original race code, see
  [Race](BH_Data#Race).

## Recurrence

- The most common definition of recurrence is a substantiated report
  following a prior substantiation that involves the same child or
  family. [^19]
- In B.H. report, recurrence is defined as an indicated allegation
  followed by another indicated allegation within a 12 month period at
  the child level. Technically, we choose the first indicated allegation
  for the fiscal year. Note that the first occurred indicated allegation
  during the fiscal year is selected if there are more than one
  indicated allegation for the child victim in order to avoid the
  duplication. The unit of analysis is a child with an indicated
  allegation in the report.

## Re-entry to substitute care

- This is one of the outcomes to measure the permanence stability.

## Region

- There are four regions: [Cook](BH_Data#Cook_region);
  [Northern](BH_Data#Northern_region);
  [Central](BH_Data#Central_region); and
  [Southern](BH_Data#Southern_region). The region refers to
  the DCFS administrative region.
- To understand the relationships among region code, subregion, and
  region, see the DATAREF.region_xref table.
- In *B.H.* reports, prior to FY2018, the region information was a
  combination of case open region and region at case closing. In other
  words, if the case is closed, use the region at the case closing.
- For the B.H. indicators related to substitute care, we generally use
  the DCFS administrative region at the case opening the outcome
  indicators are related to the initial placements and the source of the
  region comes from the LGC table.
- For the outcome indicators related to the end-of-year placements and
  the source of the region comes from the LGC table, we use the closest
  effective date to the end of the year within the FY.
- Table 1 shows decision rules for the region for each BH/CFSR
  indicator.

### Table 1: Decision Rules for BH/CFSR indicators

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

<hr>

## Report

- If the Hotline worker concludes that the allegation is one the
  department is legally empowered to investigate and that there is
  sufficient information to warrant investigation, a report will be
  taken. This means that DCFS will initiate an investigation of the
  allegations. Every call to the Hotline does not necessarily result in
  a report.<ref name="DCFSmanual">Illinois Department of Children and
  Family Services. (2019). Manual for Mandated Reporters. Springfield:
  Author. Retrieved from
  <https://mr.dcfstraining.org/public/pdf/en/Mandated-Reporter-Manual.pdf>

</ref>

## Reunification

- Refers to the process of returning children in temporary out-of-home
  care to their families of origin. Reunification is both the primary
  goal for children in out-of-home care as well as the most common
  outcome. ([Children's Bureau](https://www.childwelfare.gov/))
  Reunification with parents is the preferred method for achieving
  permanence for children in substitute care.
- In the *B.H.* measure, a reunification is achieved when the child is
  returned home and (a) the legal custody is transferred back to
  parent(s) or (b) the placement case is closed. If the child is
  returned home, his/her legal custody is not transferred and the
  placement case is open (i.e., not legally permanent), it is considered
  as “still in care.”

## Runaway

- If the type of service arrangement is coded as a) either runaway
  (RNY), auducted (ABD), whereabouts unknown periodic contact with
  caseworker (WCC), or whereabout unknown (WUK) and b) there was no any
  service type coded, the placement is defined as a runaway.

## Safe (in Child Endangerment Risk Assessment)

- Means that, after considering all reasonably available
  information/evidence concerning the presence of each of the 16
  potential safety threats, and taking into account the vulnerability of
  the child, and considering the caregiver(s)’s displayed ability/action
  to mitigate any identified threats, it is determined that a child in a
  household or in custodial care is not likely to be moderately or
  severely harmed immediately or in the near future.
  <ref name="procedures315A">Illinois Department of Children and Family
  Services. (2018). Procedures 315, Appendix A: Child Endangerment Risk
  Assessment (CERAP). Springfield: Author. Retrieved from
  <https://www2.illinois.gov/dcfs/aboutus/notices/Documents/Procedures_315.pdf>

</ref>

## Safety

- The absence of an imminent or immediate threat of moderate-to-serious
  harm to a child. ([Children's Bureau](https://www.childwelfare.gov/))
- Children’s safety is the primary concern of all child welfare
  services, particularly the safety of children who have been identified
  as maltreatment victims. [^20]
- After considering all reasonably available information/evidence
  concerning the presence of each of the 16 safety threats, taking into
  account the vulnerability of the child and considering the
  caregiver(s)’s displayed ability/action to mitigate any identified
  threats, it is then determined that a child in a household or in
  custodial care is not likely to be moderately or severely harmed
  immediately or in the near future. [^21]
- Absence of the child maltreatment re-recurrence is a type of safety
  measurement. There are four outcomes used to measure the safety in
  *B.H.* report: (a) maltreatment recurrence (CFSR indicator); (b)
  maltreatment among children in intact family cases; (c) maltreatment
  recurrence among children receiving no services; and (d) maltreatment
  in substitute care (CFSR indicator).

## Safety plan

- A temporary, short-term plan designed to control serious and immediate
  threats to children’s safety. The safety plan will indicate which
  threat or threats have led to the need for a safety plan as the result
  of the CERAP. Safety Plans must be adequate to ensure the child’s
  safety and be as minimally disruptive to the child and family as is
  reasonably possible. Safety plans can take a variety of forms and are
  developed with the input and voluntary consent of the children’s
  parent(s)/guardian(s), caregivers and other family members. [^22]

## Safety threats

- Safety threats are behaviors or conditions that may be associated with
  a child or children being in danger of moderate to severe harm
  immediately or in the near future.[^23]

## Service

- DCFS has a statutory mandate to make a special effort to stabilize and
  preserve families that are involved in child abuse or neglect
  allegations. The Department uses its own child welfare staff and
  private agencies to provide a variety of services to help the family
  survive and to change patterns of abusive or neglectful behavior.
  These efforts are based on experience that shows that some children
  may do better when kept with their families than when they are placed
  in foster care. The services provided include such things as:
  - service referrals and linkages
  - housing assistance
  - substance abuse assessment and treatment
  - homemaking assistance and training
  - parenting education and support
  - limited financial assistance
  - mental health and family counseling
  - day care of respite care [^24]

## Service type

- Each service type represents a board payment code. To see the
  classification of service types, see DATAREF.servicecd_xref. To view
  the complete list of service types, visit SACWIS.livar_type_service.

## SOR report

- SOR denotes a Subsequent Oral Family Report of suspected
  abuse/neglect, i.e. the family has previously been "indicated" for
  abuse/neglect or there is a previous "pending" report of suspected
  abuse/neglect on file in the SACWIS system.<ref name="IDCFS2017">

Illinois Department of Children and Family Services. (2017). Child
abuse/neglect statistics. Springfield: Author. Retrieved from
<https://www2.illinois.gov/dcfs/aboutus/newsandreports/Documents/CANStat.pdf#search=indicated%20report>

</ref>

## Southern region

- A value of Southern region was defined as regions *4A* (East St.
  Louis) and *5A* (Marion).

## Specialized or treatment foster home

- It involves placement of children with foster families who have been
  specially trained to care for children with certain medical or
  behavioral needs. Examples include medically fragile children,
  children with emotional or behavioral disorders, and children with
  HIV/AIDS. Treatment foster parents are required to obtain addition
  training to become licensed, provide more support for children than
  regular family foster care, and have lower limits on the number of
  children that can be cared for in their home.[^25]
- For the initial placement indicators, a child who enters a
  specialized/treatment foster home and stays in the
  specialized/treatment foster home for 8 days or longer is counted in
  the *B.H.* report.
- For the end-of-year placement indicators, a child placed in a
  specialized/treatment foster home at the end of the fiscal year is
  counted in the *B.H.* report.
- If the type of service arrangement is coded as one of the following
  service payment codes, the placement is defined as specialized or
  treatment foster care.

| cd_type_serv | Description                              |
|--------------|------------------------------------------|
| 103          | Dept Intensive Foster Care               |
| 105          | Dept Deaf Foster Care                    |
| 109          | Agency Specialized Foster Care           |
| 143          | Agency Specialized FC Level II           |
| 144          | Dept Individual Specialized FC Level II  |
| 158          | Frs - Private Agency Spec Foster Homes   |
| 159          | Frs - Dept. Specialized Foster Homes     |
| 169          | HMR - Agency Specialized Foster Care HIV |
| 179          | HMR - Dept Specialized Foster Care HIV   |
| 909          | Foster Care Exempt-Entry Rate            |
| 3179         | Unapproved Dept Hmr Spec-Hiv In Pa Home  |
| 4179         | Approved Dept Hmr Spec-Hiv In Pa Home    |
| 5103         | Lic Dept Non-Hmr Intensive In Pa Home    |
| 5105         | Lic Dept Non-Hmr Deaf In Pa Home         |
| 5114         | Lic Dept Non-Hmr Individual Spec In Pa H |
| 5144         | Lic Dept Non-Hmr Indiv Spec Fcii In Pa H |
| 5159         | Lic Dept Non-Hmr Frs Specialized In Pa H |
| 5179         | Lic Dept HMR Spec-HIV In Pa Home         |
| 5193         | Lic Dept Hmr Deaf In Pa Home             |
| 5194         | Lic Dept Hmr Specialized In Pa Home      |
| 5195         | Lic Dept Hmr Spec Fcii In Pa Home        |
| 5196         | Lic Dept Hmr Frs Specialized In Pa Home  |
| 6099         | Foster Care Exempt-Unlicensed Related    |
| 6103         | Unlicensed Non-Related Dept Intensive    |
| 6105         | Unlicensed Non-Related Dept Deaf Fc      |
| 6109         | Unlicensed Non-Related Pa Specialized    |
| 6114         | Unlicensed Non-Related Dept Specialized  |
| 6143         | Unlicensed Non-Related Pa Spec Fcii      |
| 6144         | Unlicensed Non-Related Dept Spec Fcii    |
| 6158         | Unlicensed Non-Related Frs Pa Specialize |
| 6159         | Unlicensed Non-Related Frs Dept Speciali |
| 6169         | Unapproved Hmr Agency Specialized - Hiv  |
| 6179         | Unapproved Hmr Dept Specialized - Hiv    |
| 6903         | Hmr Child In Unlicensed Intensive Fc     |
| 6905         | Hmr Child In Unlicensed Deaf Fc          |
| 6909         | Hmr Child In Unlicensed Agency Spec Fc   |
| 6914         | Hmr Child In Unlicensed Dept Spec Fc     |
| 6943         | Hmr Child In Unlicensed Agency Treat Fc  |
| 6944         | Hmr Child In Unlicensed Dept Treat Fc    |
| 6958         | Hmr Child In Unlicensed Frs Agcy Spec Fc |
| 6959         | Hmr Child In Unlicensed Frs Dept Spec Fc |
| 7109         | Medicaid/Agency Specialized Foster Care  |
| 7110         | Med Foster Comprehensive                 |
| 7143         | Med/Agency Spec FC Level II              |
| 7309         | Unlicensed Non-Relat Medica Agcy Spec Fc |
| 7343         | Unlicensed Non-Relat Medica Agcy Trea Fc |
| 7409         | Appealed Non-Related Medica Agcy Spec Fc |
| 7443         | Appealed Non-Related Medica Agcy Trea Fc |
| 7543         | Licensed Non-Related Medica Agcy Trea Fc |
| 7609         | Hmr Child In Unlic Medicaid Agcy Spec Fc |
| 7643         | Hmr Child In Unlic Medicaid Agcy Trea Fc |
| 7709         | Licensed Non-Relt Medicaid Agcy Spec Fc  |
| 7710         | Medicaid Foster Comprehen Lics Unrelativ |
| 7743         | Licensed Non-Relt Medicaid Agcy Treat Fc |
| 7809         | Hmr Child In Appea Medicaid Agcy Spec Fc |
| 7843         | Hmr Child In Appea Medicaid Agcy Trea Fc |
| 8103         | Appealed Non-Related Dept Intensive      |
| 8105         | Appealed Non-Related Dept Deaf Fc        |
| 8109         | Appealed Non-Related Pa Specialized      |
| 8114         | Appealed Non-Related Dept Specialized    |
| 8143         | Appealed Non-Related Pa Spec Fcii        |
| 8144         | Appealed Non-Related Dept Spec Fcii      |
| 8158         | Appealed Non-Related Frs Pa Specialized  |
| 8159         | Appealed Non-Related Frs Dept Specialize |
| 8169         | Approved Hmr-Agency Specialized - Hiv    |
| 8179         | Approved HMR Dept - HIV                  |
| 8903         | Hmr Child In Appealed Intensive Fc       |
| 8905         | Hmr Child In Appealed Deaf Fc            |
| 8909         | Hmr Child In Appealed Agency Spec Fc     |
| 8914         | Hmr Child In Appealed Spec Fc            |
| 8943         | Hmr Child In Appealed Agency Treat Fc    |
| 8958         | Hmr Child In Appealed Agency Spec Fc     |
| 8959         | Hmr Child In Appealed Dept Spec Fc       |
| 9009         | Foster Care Exempt-Licensed Unrelated    |
| 9099         | Foster Care Exempt-Licensed Related      |
| 9103         | Licensed Non-Related Intensive Fc        |
| 9105         | Licensed Non-Related Deaf Fc             |
| 9109         | Licensed Non-Related Agency Spec Fc      |
| 9114         | Licensed Non-Related Dept Spec Fc        |
| 9143         | Licensed Non-Related Agency Spec Fcii Fc |
| 9144         | Licensed Non-Related Dept Spec Fcii Fc   |
| 9158         | Licensed Non-Related Frs Agency Spec Fc  |
| 9159         | Licensed Non-Related Frs Dept Spec Fc    |
| 9169         | HMR in LIC Priv AG Specialized - HIV     |
| 9179         | HMR in LIC Dept AG Specialized - HIV     |
| 9903         | Hmr Child In Licensed Intensive Fc       |
| 9905         | Hmr Child In Licensed Deaf Fc            |
| 9909         | Hmr Child In Licensed Agency Spec Fc     |
| 9914         | Hmr Child In Licensed Dept Spec Fc       |
| 9943         | Hmr Child In Licensed Agency Treat Fc    |
| 9944         | Hmr Child In Licensed Dept Spec Fcii Fc  |
| 9958         | Hmr Child In Licensed Frs Agency Spec Fc |
| 9959         | Hmr Child In Licensed Frs Dept Spec Fc   |

- Alternatively, if living arrangement type is coded as a) either Foster
  Home Specialized (FHS), Therapeutic Foster Home (TFH), or FHT and b)
  there was no type of service code, then the placement is defined as
  specialized or treatment foster care.

## Spell

- A (Legal) spell is defined as a period for a child in a DCFS legal
  custody during an open child case. A (legal) spell ends with either
  reunification, adoption, guardianship, living with relatives, or
  otherwise exited (see the *censor* column in the *master_spell_legal*
  table). If the case is still open and the child is still under a DCFS
  legal custody, the censor of the spell is "Still in care."
- One of the BH measures, length of stay is calculated for the first
  spell after a child was placed in a substitute care. See [Indicator:
  median length of stay in substitute
  care](BH_Data#ind2g_lengthofstay).

## Stability

- Children are entitled to a stable and lasting family life and should
  not be deprived of it except for urgent and compelling reasons.[^26]

## Substantiated

- An investigation disposition concluding that the allegation of child
  maltreatment or risk of maltreatment was supported by State law or
  policy, i.e., that credible evidence exists that child abuse or
  neglect has occurred.([Children's
  Bureau](https://www.childwelfare.gov/))
- See
  [Indicated](https://wiki.cfrc.illinois.edu/index.php/BH_Data#Indicated).

## Subregion

- The state of Illinois is divided into 10 subregions: Rockford (1A);
  Peoria (1B); Aurora (2A); Springfield (3A); Champaign (3B); East St.
  Louis (4A); Marion (5A); Cook North (6B); Cook Central (2B, 6A, 6C,
  6J); and Cook South (6D). See SACWIS.code_desc_ch for more details
  (id_grp=SUBRGNCD).
- To understand the relationships among region code, subregion, and
  region, see the DATAREF.region_xref table.

## Substitute care

- Children should only be removed from their parents and placed in
  substitute care when it is necessary to ensure their safety and
  well-being. Once removed from their homes, the public child welfare
  system and its private agency partners have a responsibility to
  provide children with living arrangements that ensure that they are
  safe from additional harm, maintain connections with their family
  members and community, and provide stability. In addition, substitute
  care should be a temporary solution and children should live in
  substitute care settings for the shortest period necessary.[^27]
- At the simplest level of distinction, substitute care placement types
  can be divided into two categories: foster homes and congregate care.
  The first category includes placements where a child lives with a
  foster parent in their home, and includes kinship foster homes,
  traditional foster homes, and specialized or treatment foster homes
  (i.e., non-congregate care). While it is preferred that children in
  substitute care live in family settings, some children have physical
  or behavioral needs that require placement in congregate care, a
  non-family setting where a group of children receive specialized care
  and treatment (e.g., group home, shelter, residential treatment
  facility). [^28]

### Table 1: Event Excluded from Substitute Care: Indicators 2A - 2G

Table 1 shows which event is excluded from the definition of substitute
care in each indicator (Indicators 2A through 2G).

|    |                                                                                                                     | Initial Placement | End-of-Year Placement | Placement stability (CFSR) | Children Who Run Away from SC | Median Length of Stay in SC |
|----|---------------------------------------------------------------------------------------------------------------------|-------------------|-----------------------|----------------------------|-------------------------------|-----------------------------|
|    |                                                                                                                     | 2A & 2C           | 2B & 2D               | 2E                         | 2F                            | 2G                          |
| 01 | Home of parent (HMP)                                                                                                |                   |                       | x                          |                               |                             |
| 02 | Kinship foster home                                                                                                 |                   |                       |                            |                               |                             |
| 03 | Adoptive placement                                                                                                  | x                 | x                     |                            | x                             | x                           |
| 04 | Traditional foster home                                                                                             |                   |                       |                            |                               |                             |
| 05 | Specialized foster home                                                                                             |                   |                       |                            |                               |                             |
| 06 | Group home                                                                                                          |                   |                       |                            |                               |                             |
| 07 | Institution                                                                                                         |                   |                       |                            |                               |                             |
| 08 | Adoption subsidy                                                                                                    |                   |                       | x                          |                               |                             |
| 09 | Independent living                                                                                                  | x                 | x                     |                            | x                             | x                           |
| 10 | Subsidized guardianship                                                                                             | x                 | x                     | x                          | x                             | x                           |
| 11 | Emergency shelter                                                                                                   |                   |                       |                            |                               |                             |
| 12 | Emergency foster care                                                                                               |                   |                       |                            |                               |                             |
| 13 | Runaway (RNY), Abducted (ABD), Unknown contact (WCC), Whereabouts unknown (WUK)                                     | x                 | x                     |                            | x                             | x                           |
| 14 | Detention/institution (DET, IDC)                                                                                    |                   |                       |                            |                               |                             |
| 15 | Unauthorized home of parent (UAH), Unauthorized placement (UAP)                                                     | x                 | x                     |                            | x                             | x                           |
| 16 | Deceased (DEC)                                                                                                      | x                 | x                     | x                          | x                             | x                           |
| 17 | Hospital/healthcare facility (HHF)                                                                                  | x                 | x                     |                            | x                             | x                           |
| 18 | College university scholarship (CUS), Job training program (JTP), Youth in college (YIC), Youth in employment (YIE) | x                 | x                     | x                          | x                             | x                           |
| 19 | Armed service duty (ASD), Other (OTH), Unknown (UNK)                                                                | x                 | x                     | x                          | x                             | x                           |
| 20 | Hospital facility medical (HFM)                                                                                     | x                 | x                     |                            | x                             | x                           |
| 21 | Hospital facility psychiatric (HFP)                                                                                 | x                 | x                     |                            | x                             | x                           |
| 22 | Private guardianship home (PGH)                                                                                     |                   |                       | x                          |                               |                             |

### Table 2: Event Excluded from Substitute Care: Indicators 3A/C/E, 3B, and 3DF

Table 2 shows which event is excluded from the definition of substitute
care in Indicators 3A/C/E, 3B and 3DF.

|    |                                                                                                                     | Permanency (Reunification/Adoption/Guardianship) | Stability (Reunification) | Stability (Adoption/Guardianship) |
|----|---------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|---------------------------|-----------------------------------|
|    |                                                                                                                     | 3ACE                                             | 3B                        | 3DF                               |
| 01 | Home of parent (HMP)                                                                                                |                                                  | x                         |                                   |
| 02 | Kinship foster home                                                                                                 |                                                  |                           |                                   |
| 03 | Adoptive placement                                                                                                  | x                                                | x                         |                                   |
| 04 | Traditional foster home                                                                                             |                                                  |                           |                                   |
| 05 | Specialized foster home                                                                                             |                                                  |                           |                                   |
| 06 | Group home                                                                                                          |                                                  |                           |                                   |
| 07 | Institution                                                                                                         |                                                  |                           |                                   |
| 08 | Adoption subsidy                                                                                                    |                                                  | x                         |                                   |
| 09 | Independent living                                                                                                  | x                                                | x                         | x                                 |
| 10 | Subsidized guardianship                                                                                             | x                                                | x                         |                                   |
| 11 | Emergency shelter                                                                                                   |                                                  |                           |                                   |
| 12 | Emergency foster care                                                                                               |                                                  |                           |                                   |
| 13 | Runaway (RNY), Abducted (ABD), Unknown contact (WCC), Whereabouts unknown (WUK)                                     | x                                                | x                         | x                                 |
| 14 | Detention/institution (DET, IDC)                                                                                    |                                                  |                           |                                   |
| 15 | Unauthorized home of parent (UAH), Unauthorized placement (UAP)                                                     | x                                                |                           | x                                 |
| 16 | Deceased (DEC)                                                                                                      | x                                                | x                         | x                                 |
| 17 | Hospital/healthcare facility (HHF)                                                                                  | x                                                |                           | x                                 |
| 18 | College university scholarship (CUS), Job training program (JTP), Youth in college (YIC), Youth in employment (YIE) | x                                                | x                         | x                                 |
| 19 | Armed service duty (ASD), Other (OTH), Unknown (UNK)                                                                | x                                                | x                         | x                                 |
| 20 | Hospital facility medical (HFM)                                                                                     | x                                                |                           | x                                 |
| 21 | Hospital facility psychiatric (HFP)                                                                                 | x                                                |                           | x                                 |
| 22 | Private guardianship home (PGH)                                                                                     | x                                                | x                         |                                   |

## Traditional foster home (TFH)

- It involves placement of children with non-relatives in the
  non-relatives' homes. These traditional foster parents have been
  trained, assessed, and licensed to provide shelter and care.[^29]
- For the initial placement indicators, a child who enters a traditional
  foster home and stays in (TFH) for 8 days or longer is counted in the
  *B.H.* report.
- For the end-of-year placement indicators, a child placed in TFH at the
  end of the fiscal year is counted in the *B.H.* report.
- If the type of service arrangement is coded as one of the following
  service payment codes, the placement is defined as TFH.

| cd_type_serv | Description                              |
|--------------|------------------------------------------|
| 101          | Department Boarding Homes                |
| 102          | Private Agency Boarding Homes            |
| 107          | Dept Reduced Rate Boarding Home          |
| 120          | Intermittent Non-Contracted Foster Care  |
| 146          | Sibling Assistance - Special Service Fee |
| 151          | Dept Board Home - Cuban/Haitian Refugee  |
| 152          | Dept Board Home - Other Refugee          |
| 155          | Frs - Private Agency Foster Care         |
| 156          | Frs - Department Regular Foster Care     |
| 162          | Pregnant Parenting Teen - F.C.           |
| 211          | Placement Prevention And Reduction       |
| 2102         | Priv Ag Bd.Home/Perf.Based Cont.         |
| 2602         | Unlic Non-Rel Pa Bd Hm/Perf.Based Cont.  |
| 2902         | Lic Non-Rel Ag Bd Hom/Perf.Based Cont.   |
| 3602         | Unlic Non-Rel Pa Bd Hm/Pcs Cont          |
| 4102         | Lic Non-Rel Pa Bd Hm/Pcs Cont            |
| 4901         | Interim Payment - Prospective Placement  |
| 4902         | Out Of Home-Pos F.C. Placement           |
| 4999         | Interim Payment Before Signed Agreement  |
| 5101         | Dept Non-Hmr In Licensed Pa Home         |
| 5107         | Dept Non-Hmr Reduced Rate In Lic Pa Home |
| 5126         | Dept Non-Hmr Successor Guard In Lic Pa H |
| 5151         | Dept Non-Hmr Cuban Haitian In Lic Pa Hom |
| 5152         | Dept Hmr Other Refugee In Lic Pa Home    |
| 5161         | Lic Dept Hmr Frs In Pa Home              |
| 6009         | Foster Care Exempt-Unlicensed Unrelated  |
| 6101         | Unlicensed Non-Related Dept Boarding Hom |
| 6102         | Unlicensed Non-Related Pa Boarding Home  |
| 6107         | Unlicensed Non-Related Dept Reduced Rate |
| 6126         | Unlicensed Non-Related Guardian Successo |
| 6151         | Unlicensed Non-Relate Dept Cuban Haitian |
| 6152         | Unlicensed Non-Related Dept Other Refuge |
| 6155         | Unlicensed Non-Related Frs Pa Regular    |
| 6156         | Unlicensed Non-Related Frs Dept Regular  |
| 8102         | Appealed Non-Related Pa Boarding Home    |
| 8107         | Appealed Non-Related Dept Reduced Rate   |
| 8126         | Appealed Non-Related Guardian Successor  |
| 8151         | Appealed Non-Related Dept Cuban Haitian  |
| 8152         | Appealed Non-Related Dept Other Refugee  |
| 8156         | Appealed Non-Related Frs Dept Regular    |
| 9101         | Licensed Non-Related Dept Boarding Home  |
| 9102         | Licensed Non-Related Agency Boarding Hom |
| 9107         | Licensed Non-Related Reduc Rate Board Ho |
| 9126         | Licensed Non-Relate Guard Succes-Non Hmr |
| 9151         | Licensed Non-Related Dept Cuban/Haitian  |
| 9152         | Licensed Non-Related Dept Other Refugee  |
| 9155         | Licensed Non-Related Frs Agency Fc       |
| 9156         | Licensed Non-Related Frs Dept Fc         |

- Alternatively, if living arrangement type is coded as a) either Foster
  Home Boarding - DCFS (FHB), Foster Home Indian - Licensed Specified or
  Approved by an Indian Child's Tribe (FHI), Foster Home Boarding -
  Private Agency(FHP), Foster Home (FOS) or Foster Home Adoptive (FHA)
  and b) there was no type of service code, then the placement is
  defined as traditional foster home.

## Unfounded

- An investigation of suspected child abuse/neglect has revealed no
  credible evidence that the abuse/neglect occurred.[^30]
- Cases are called "unfounded" when an investigation has determined that
  credible evidence of the alleged abuse or neglect cannot be
  documented. All unfounded reports are kept by the State Central
  Register (SCR) for a period of no less than five years. In addition,
  mandated reporters may request a review of an unfounded report within
  10 days of notification if they have concerns about the adequacy of
  the investigation or if they feel that specific information has been
  overlooked.[^31]
- An investigation report is unfounded if the finding is coded 2 in the
  CD_INVST_FIND field in SACWIS.investigation.
- An allegation is unfounded if the finding is coded 2 in the CD_FIND
  field in SACWIS.invst.allegation.

## Unsafe

- After considering all reasonably available information/evidence
  concerning the presence of each of the 16 potential safety threats,
  taking into account the vulnerability of the child and considering the
  caregiver(s)’s displayed ability/action to mitigate any identified
  threats, it is determined that a child in a household or in custodial
  care is likely to be moderately or severely harmed immediately or in
  the near future. In the event a child is considered Unsafe, a safety
  plan or protective custody must be implemented by the worker
  completing the CERAP and approved by the supervisor. [^32]

## Well-Being

- Children should receive adequate services to meet their educational,
  physical and mental health needs.<ref name="HHS2003">U.S. Department
  of Health and Human Services. (2003). Child and Family

`Services Reviews Onsite Review, Instrument and Instructions. `

</ref>
<h1>

Acronyms

</h1>

## AFCARS

Adoption and Foster Care Analysis and Reporting System

## AODA

Alcohol & Other Drug Abuse

## CANTS

Child Abuse and Neglect Tracking System

## CERAP

Child Endangerment Risk Assessment Protocol

## CFSR

Child and Family Services Review

## CFTM

Child and Family Team Meeting

## CPS

Child Protection Services

## CPTA

Child Protection Training Academy

## CYCIS

Child and Youth Centered Information System

## DR

Differential Response

## EOY

End of Year

## FCURP

Foster Care Utilization Review Program

## HMP

Home of Parent

## IA

Integrated Assessment

## IGH

Institution/Group Home

## LGC

Legacy Golden Copy

## ILO

Independent Living Only

## NCANDS

National Child Abuse and Neglect Data System

## PIP

Program Improvement Plan

## QRTP

Qualified Residential Treatment Program

## RCT

Randomized Control Trials

## SACWIS

Statewide Automated Child Welfare Information System

## SCR

State Central Registry

## SGH

Subsidized Guardian Home

## SOC

System of Care

<h1>

References

</h1>
<references />

[^1]: Memo sent by Illinois Department of Children and Family Services
    on April 14, 2014.

[^2]: Illinois Department of Children and Family Services. (2017). Child
    abuse/neglect statistics. Springfield: Author. Retrieved from
    <https://www2.illinois.gov/dcfs/aboutus/newsandreports/Documents/CANStat.pdf#search=indicated%20report>

[^3]: Illinois Department of Children and Family Services. (2015).
    Procedures 315, Permanency Planning. Springfield: Author. Retrieved
    from
    <https://www2.illinois.gov/dcfs/aboutus/notices/Documents/Procedures_315.pdf>

[^4]: Illinois Department of Children and Family Services. (1987).
    Procedures 304: Access to and Eligibility for Child Welfare
    Services. Springfield, IL: Author. Retrieved from
    <https://www2.illinois.gov/dcfs/aboutus/notices/Documents/procedures_304.pdf>

[^5]: U.S. Social Security Act, Sec. 475. \[42 U.S.C. 675\].

[^6]: Child Welfare Information Gateway. (2016). Racial
    disproportionality and disparity in child welfare. Washington, DC:
    U.S. Department of Health and Human Services, Children's Bureau.

[^7]: Children and Family Research Center. (2019). Conditions of
    children in or at risk of foster care in Illinois: FY2019 monitoring
    report of the B.H. Consent Decree. Urbana, IL: Children and Family
    Research Center, University of Illinois at Urbana-Champaign.
    Retrieved from
    <https://www.cfrc.illinois.edu/pubs/rp_20191008_ConditionsofChildreninoratRiskofFosterCareinIllinoisFY2019MonitoringReportoftheBHConsentDecree.pdf>

[^8]:

[^9]:

[^10]:

[^11]:

[^12]: Children and Family Research Center (2005). Conditions of
    children in or at risk of foster care in Illinois: An assessment of
    their safety, stability, continuity, permanence, and well-being.
    Urbana, IL: Children and Family Research Center, University of
    Illinois at Urbana-Champaign. Retrieved from
    <https://www.cfrc.illinois.edu/pubs/rp_20060901_ConditionsOfChildrenBH2005.pdf>.

[^13]: Weiner, D. and Cull, M. (2019). Systemic review of critical
    incidents in intact family services. Chicago, IL: Chapin Hall at the
    University of Chicago. Retrieved from
    <https://www.chapinhall.org/wp-content/uploads/Systemic-Review-Critical-Incidents.pdf>.

[^14]: Fuller, T., Wakita, S. Nieto, M., and Chiu, Y. (2018). Illinois
    child endangerment risk assessment protocol FY2018 annual
    evaluation. Urbana, IL: Children and Family Research Center at the
    University of Illinois at Urbana-Champaign. Retrieved from
    <https://www.cfrc.illinois.edu/pubs/rp_20180802_IllinoisChildEndangermentRiskAssessmentProtocol:FY2018AnnualEvaluation.pdf>

[^15]:

[^16]: U.S. Children’s Bureau (1961). Legislative guides for the
    termination of parental rights and responsibilities and the adoption
    of children, No. 394, Washington, DC: U.S. Department of Health,
    Education, and Welfare.

[^17]:

[^18]:

[^19]: Fluke, J.D., & Hollinshead, D.M. (2003). Child maltreatment
    recurrence. Duluth, GA: National Resource Center on Child
    Maltreatment.

[^20]: U.S. Department of Health and Human Services. (2004). Child
    Welfare Outcomes 2001: Annual Report. Safety, Permanency,
    Well-being. Washington, DC: U.S. Government Printing Office.

[^21]: Illinois Department of Children and Family Services. (2016).
    Procedures 302.388 Intact Family Services. Springfield, IL: Author.
    Retrieved from
    <https://www2.illinois.gov/dcfs/aboutus/notices/Documents/Procedures_302_Subpart_C.pdf#search=302%2E388>

[^22]:

[^23]:

[^24]:

[^25]:

[^26]: First White House Conference on the Care of Dependent Children,
    January 25, 1909.

[^27]: Children and Family Research Center. (2016). Conditions of
    children in or at risk of foster care in Illinois: The 2015
    monitoring report of the B.H. consent decree. Urbana, IL: Children
    and Family Research Center, University of Illinois at
    Urbana-Champaign. Retrieved from
    <https://www.cfrc.illinois.edu/pubs/rp_20170101_ConditionsOfChildrenInOrAtRiskOfFosterCareInIllinois2015MonitoringReportOfTheB.H.ConsentDecree.pdf>.

[^28]:

[^29]:

[^30]: Illinois Department of Children and Family Services. (2017).
    Child abuse/neglect statistics. Springfield: Author. Retrieved from
    <https://www2.illinois.gov/dcfs/aboutus/newsandreports/Documents/CANStat.pdf#search=indicated%20report>

[^31]:

[^32]:
