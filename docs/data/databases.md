---
layout: default
title: Database Server Addressing
parent: Data & Data Access
nav_order: 2
---

# Database Server Addressing

This section lists Fully Qualified Domain Names for database servers.

**Research Databases**  
db0.cfrc.illinois.edu db1.cfrc.illinois.edu

**Web Database**  
db6.cfrc.illinois.edu

**Archive Database (archived projects)**  
db2.cfrc.illinois.edu

**Faculty Database**  
db3.cfrc.illinois.edu

# DCFS Databases

Current statuses of DCFS databases:

<strong>DCFS_PROD:</strong> June 30, 2023 <br>
<strong>DCFS_DEV:</strong> September 30, 2023 <br>
<strong>DCFS_ANNUAL:</strong> BH2023 (Extraction: December 31, 2022) <br>
<strong>DCFS_STABLE:</strong> Mystery. <br>

## \# Changelog

This changelog only documents changes to the SACWIS and LegacyGoldenCopy
databases. This is not intended to be a comprehensive changelog for DCFS
projects. Changelog versioning refers to the data extraction date.
Reporting for BH will cover a period of the extraction date minus one
quarter (i.e., The Q3 report will use Q4 data).

\## **\[2023<sub>October</sub>\]** - 2023-10-01 Extraction -
[3301a4a](https://github.com/cfrc-uiuc/SysOps/commit/2696b29f2fdd1659fadc4854cd20e7de13301a4a)

\### Added - DCFS<sub>DEV</sub>

- sacwis.intake<sub>eventpartibirthinfo</sub>
- sacwis.invst<sub>subjbirthinfo</sub>

\### Added - LGC

- lgc.cftvbc9200
- lgc.cftvcm9c00

\## **\[2022<sub>April</sub>\]** - 2023-04-02 Extraction -
[a5bff54](https://github.com/cfrc-uiuc/devops/commit/95bbabf438ecd667ef39e5646c747dfa1a5bff54)

\### Added - DCFS<sub>DEV</sub>

- sacwis.leads<sub>check</sub>
- sacwis.leads<sub>checkoffn</sub>
- lgc.cftvnm9400

\### Changed - DCFS<sub>DEV</sub>

- lgc.dwh<sub>vourcherdetail</sub>
  - changes dtl<sub>unitqntycnt</sub> from decimal(5,2) to decimal(18,2)

\## **\[2022<sub>January</sub>\]** - 2023-01-01 Extraction -
[e5818ea](https://github.com/cfrc-uiuc/devops/commit/4a51dfbf58dce5a585baed85925c3f471e5818ea)

\### Added - DCFS<sub>DEV</sub>

- sacwis.sogie<sub>factorresp</sub>

- sacwis.sogie<sub>factortmpl</sub>

- sacwis.sogie<sub>infoe</sub>

- lgc.cftvvp1700

- lgc.cftvvp1900

- lgc.cftvvp2000

\### Removed - DCFS<sub>DEV</sub>

- sacwis.old<sub>casetype</sub>
- sacwis.old<sub>casetypemember</sub>
- sacwis.old<sub>investigation</sub>
- sacwis.old<sub>language</sub>

\### Changed - DCFS<sub>DEV</sub>

- lgc.cftvcm1100
  - Adds "adptmothersex"
  - Adds "adptfathersex"
  - Adds "mothertribalmemberind"
  - Adds "fathertribalmemberind"
- lgc.cftvcm4900
  - Adds "tpr<sub>datemoth</sub>"
  - Adds "tpr<sub>datefath</sub>"

\## **\[2022<sub>January</sub>\]** - 2022-01-06 Extraction -
[2a6932b](https://gitlab.com/CFRC/devops/-/commit/2a6932ba585facbe7efaf5532ba2bc71b46ae553)

\### Added - DCFS<sub>DEV</sub>

- "sacwis"."contact<sub>galinfo</sub>"

- "sacwis"."mi<sub>technique</sub>"

- "sacwis"."prevention<sub>plan</sub>"

- "sacwis"."prevention<sub>service</sub>"

- "sacwis"."professional<sub>collateral</sub>"

- "sacwis"."service<sub>request</sub>"

- "sacwis"."service<sub>reqmember</sub>"

- "lgc"."boardmaster"

\### Removed - DCFS<sub>DEV</sub>

- "sacwis"."old<sub>investigation</sub>"

- "lgc"."unpackedboardmaster"

\### Changed - DCFS<sub>DEV</sub>

- "sacwis"."ncands<sub>report</sub>"stat

- \- Adds "cd<sub>miapply</sub>"

- "sacwis"."prevention<sub>rcmnd</sub>"

  - Adds "id<sub>servreq</sub>"
  - Adds "id<sub>updt</sub>"
  - Adds "id<sub>dsgnupdt</sub>"
  - Adds "ts<sub>updt</sub>"

- "sacwis"."worker"

  - Adds "cd<sub>mitrain</sub>"
  - Adds "dt<sub>mitrain</sub>"
  - Removes index

- "lgc"."cftvcm9100

- Adds "case<sub>id</sub>" to index

\## **\[2021<sub>September</sub>\]** - 2021-10-01 Extraction -
[0145f1dc](https://gitlab.com/CFRC/devops/-/commit/0145f1dc76062cc38c88151dbc4bac5332c42533)

\### Added - DCFS<sub>DEV</sub>

- "sacwis"."old<sub>investigation</sub>"

- "sacwis"."prevention<sub>rcmnd</sub>"

- "sacwis"."prevention<sub>rcmndfctr</sub>"

\### Removed - DCFS<sub>DEV</sub>

- "sacwis"."old<sub>cansfactorrule</sub>"

- "sacwis"."old<sub>cansia</sub>"

- "sacwis"."old<sub>icasummary</sub>"

- "sacwis"."old<sub>icasummaryfactor</sub>"

- "sacwis"."old<sub>qrtepisode</sub>"

\### Changed - DCFS<sub>DEV</sub>

- Primary key constraints now preserved in tables wherever possible

- "sacwis"."investigation"

  - Add "cd<sub>scrnforjuvcourt</sub>"

- "sacwis"."qrt<sub>episode</sub>"

  - Remove "cd<sub>epsddist</sub>"
  - Add "cd<sub>stat</sub>"

\## **\[2021<sub>June</sub>\]** - 2021-07-01 Extraction -
[8c7a3b2](https://gitlab.com/CFRC/devops/-/commit/8c7a3b2eb922c3cbb5f7f168db320694cd3ff5ef)

\### Added - DCFS<sub>DEV</sub>

- "sacwis.old<sub>icasummary</sub>"

- "sacwis.old<sub>icasummaryfactor</sub>"

- "sacwis.old<sub>qrtepisode</sub>"

- "sacwis.qrt<sub>statushistory</sub>"

- lgc.ContractServiceArea

- lgc.PaidProviders

\### Changed - DCFS<sub>DEV</sub>

- "sacwis.ica<sub>summary</sub>"

- \- Remove "fl<sub>icawkrdec</sub>"

  - Remove "fl<sub>extdec</sub>"
  - Remove "dt<sub>extdec</sub>"
  - Remove "tx<sub>decdesc</sub>"

- "sacwis.qrt<sub>episode</sub>

  - Remove "tx<sub>decdesc</sub>"

- "sacwis.ica<sub>summaryfactor</sub>"

  - Add "fl<sub>resp</sub>"

- "lgc.livarhist"

  - Add "casemanageragency"

\## **\[2021<sub>March</sub>\]** - 2021-04-02 Extraction -
[9d321b4a](https://gitlab.com/CFRC/devops/-/commit/9d321b4ab4eeab61d50e144998b70f7f1fd7102e)
[7f97ff5b](https://gitlab.com/CFRC/devops/-/commit/7f97ff5bfb03cd5d5de072526e033ed127f30919)

\### Added - DCFS<sub>DEV</sub>

- "sacwis.county<sub>regionxrf</sub>"
- "sacwis.ica<sub>summary</sub>"
- "sacwis.ica<sub>summaryfactor</sub>"
- "sacwis.ica<sub>summarytmpl</sub>"
- "sacwis.old<sub>cansfactorrule</sub>"
- "sacwis.qrt<sub>episode</sub>"
- "lgc.cftvcc1200"

\### Changed - DCFS<sub>DEV</sub>

- "lgc.cftvco9600
  - Changes "oblg<sub>fy</sub>" from varchar(4) to int

\## **\[2020<sub>December</sub>\]** - 2021-01-03 Extraction -
[ab24211](https://gitlab.com/CFRC/devops/-/commit/e09ae464a355cc75e24736d04e54480a4ab24211)

\### Added - DCFS<sub>DEV</sub>

- "sacwis.old<sub>cansia</sub>"

- "lgc.adm"

- Constraints (primary and foreign keys (and table relationships)) have
  been restored

\### Changed - DCFS<sub>DEV</sub>

- Table "sacwis.cans<sub>ia</sub>"
  - adds field "cd<sub>cansiatype</sub>"

\### Removed - DCFS<sub>DEV</sub>

- "sacwis.old<sub>referral</sub>"
- "sacwis.old<sub>referralservice</sub>"
- "sacwis.old<sub>referralservcatg</sub>"

\## **\[2020<sub>September</sub>\]** - 2020-10-06 Extraction -
[123e3de](https://gitlab.com/CFRC/devops/-/commit/123e4de27895c435120f73a596536cf1d87fe46b)

\### Added - DCFS<sub>DEV</sub>

- "sacwis.intake<sub>contributor</sub>"
- "sacwis.intake<sub>elementhistory</sub>"
- "sacwis.invst<sub>review</sub>"
- "sacwis.invst<sub>reviewques</sub>"
- "sacwis.invst<sub>reviewrest</sub>"
- "sacwis.isbe<sub>studentxref</sub>"

\### Changed - DCFS<sub>DEV</sub>

- Table "lgc.cftvco9600"
  - Changed "oblg<sub>fy</sub>" from "int" to "varchar(4)"
- Table "lgc.livarhist"
  - Added filed "caselanguage"

\## **\[2020<sub>June</sub>\]** - 2020-07-02 Extraction -
[0c0fac81](https://gitlab.com/CFRC/CFRC/-/commit/0c0fac8121fb36fae8784ebc45fa2c03b580ac54)
[977d8fbf](https://gitlab.com/CFRC/CFRC/-/commit/977d8fbffd5d4925ccabc85686ea4fca55f30627)

\### Added - DCFS<sub>DEV</sub>

- "sacwis.isbe<sub>studentxref</sub>"

\## **\[2020<sub>March</sub>\]** - 2020-04-01 Extraction -
[2179b57c](https://gitlab.com/CFRC/CFRC/-/commit/2179b57cd8443aecf6d8de947bd2c16c17b23bc5)
[4e6ccb08](https://gitlab.com/CFRC/CFRC/-/commit/4e6ccb08be8264588088a68e997516df05668aba)
[525ba67b](https://gitlab.com/CFRC/CFRC/-/commit/525ba67bb3a27f8b93cead8cb0bf7a26829a39c3)

\### Added - DCFS<sub>DEV</sub>

- "sacwis.old<sub>referralservice</sub>"
- "saciws.old<sub>referral</sub>"
- "sacwis.old<sub>referralservcatg</sub>"
- "sacwis.referral<sub>servdetl</sub>"
- "sacwis.referral<sub>swab</sub>"
- "sacwis.text<sub>extender</sub>"
- "lgc.cftvcm8000"

\### Removed - DCFS<sub>DEV</sub>

- "sacwis.old<sub>personphoto</sub>"
- "sacwis.old<sub>safetyassesparti</sub>"
- "sacwis\>old<sub>safetyplanparti</sub>"
- "sacwis.old<sub>safetyplanthreat</sub>"
- "sacwis.old<sub>safetystrhparti</sub>"
- "sacwis.prod<sub>noteparticipant</sub>"

\### Changed - DCFS<sub>DEV</sub>

- Table "sacwis.referral"

- \- Removed field "fl<sub>courtreq</sub>"

  - Added field "cd<sub>refrrsn</sub>"
  - Added field "fl<sub>admt</sub>"
  - Added field "tm<sub>servsmplcoll</sub>"

- Table "sacwis.referral<sub>servcatg</sub>"

  - Changed field "id<sub>chaincust</sub>" from bigint to char(20)

- Table "lgc.cftvco9100"

  - Changed field "oblg<sub>fy</sub>" from varchar(4) to int

- Table "lgc.cftvco9200"

  - Changed field "oblg<sub>fy</sub>" from varchar(4) to int

- Table "lgc.cftvco9300"

  - Changed field "oblg<sub>fy</sub>" from varchar(4) to int

- Table "lgc.cftvco9400"

  - Changed field "oblg<sub>fy</sub>" from varchar(4) to int

- Table "lgc.cftvco9500"

  - Changed field "oblg<sub>fy</sub>" from varchar(4) to int

- Table "lgc.cftvco9600"

  - Changed field "oblg<sub>fy</sub>" from varchar(4) to int

\## **\[2020<sub>December</sub>\]** - 2020-01-13 Extraction -
[0451f2b7](https://gitlab.com/CFRC/CFRC/commit/0451f2b7814ac6fba2f3df3dd44b07c9f85b8b68)
[3e522ef4](https://gitlab.com/CFRC/CFRC/commit/3e522ef416f6cc26f3ef28c1fb975ba3ba7031b5)

\### Added - DCFS<sub>DEV</sub>

- "sacwis.case<sub>photo</sub>"
- "sacwis.illini<sub>care</sub>"
- "sacwis.language<sub>deter</sub>"
- "sacwis.old<sub>personphoto</sub>"
- "sacwis.worker<sub>orgrolesec</sub>"
- "lgc.cftvcm8000"
- "health" schema
- "person" schema

\### Removed

- "sacwis.old<sub>safetyplan</sub>"
- "sacwis.person<sub>photo</sub>"
- 

\## **\[2020<sub>September</sub>\]** - 2019-10-01 Extraction

\### Added – DCFS<sub>DEV</sub>

- New table "sacwis.intake<sub>eventnrt</sub>". See:

[a411ca4b](https://gitlab.com/CFRC/CFRC/commit/a411ca4b540e58fefff12e457b8733a466a91700)

- Time fields with a "tm\_-" prefix (sacwis schema). See:

[<https://gitlab.com/CFRC/CFRC/issues/12>](https://gitlab.com/CFRC/CFRC/issues/12),  
[246a1030](https://gitlab.com/CFRC/CFRC/commit/246a10306d4a2500e80ac3836a758269541a2df7)

\### Added – DCFS<sub>STABLE</sub>

- The following "old\_" tables were added to the SACWIS schema:
- old<sub>callbackattemptmar2019</sub>
- old<sub>callmar2019</sub>
- old<sub>safetyassespartimar2019</sub>
- old<sub>safetyassessmentmar2019</sub>
- old<sub>safetyplanjun2019</sub>
- old<sub>safetyplanmar2019</sub>
- old<sub>safetyplanpartimar2019</sub>
- old<sub>safetyplanthreatmar2019</sub>
- old<sub>safetystrhpartimar2019</sub>\>

\### Changed

- Removed NOT NULL constraints from lgc schema tables. See:
  [7afd9ffa](https://gitlab.com/CFRC/CFRC/commit/7afd9ffa2effdf70e5ea7c2d0e52789d8b9f05a1)

\## **\[2019<sub>June</sub>\]** - 2019-07-01 - d85e263e, cf00e9ea

\### Added

- Text fields in sacwis.case.contact.cmply
- 

\### Changed

- Additional fields in sacwis.old<sub>safetyplan</sub>
- New indexes for sacwis.old<sub>safetyplan</sub>

# Database Descriptions

## DCFS<sub>DEV</sub>

This database will contain current development data.

January - March: Data will be the most current DCFS data as of January 1
(through December 31). April - June: Data through March July -
September: Data through June October - December: Data through September
Once completed, this database will be transferred to
DCFS<sub>PROD</sub>.

## DCFS<sub>ANNUAL</sub>

This will hold the development data for the current annual BH report
once completed, assuming that data has been collected from DCFS.

## DCFS<sub>PROD</sub>

This database will contain data from most recent completed quarterly
report. It will always correspond with the live Outcomes website.

## DCFS<sub>STABLE</sub>

This database will contain static data for the purposes of code testing.

# Geocoding

## Geocoding Process

…\[to be added\]…

## Outputs

Currently, three DCFS tables are geocoded using Census data:

- sacwis.address
- sacwis.provider
- lgc."ProviderVerifiedAddress"

Finalized and de-identified versions of the above tables are loaded in
the geo schema.

## Rating

The PostGIS geocode function produces a rating that has been added to
the records of geocoded tables. These ratings could be thought of as a
confidence score. Simplistically, the lower the score, the greater the
accuracy of the address match between the source data and the geocoder.
A rating of **0** indicates an exact match. Generally speaking, a rating
of 100 or more indicates that the address could not be determined, and
added geographical data refers to the city center.

For everything in between, the data may or may not be accurate. It does
seem that in general, the higher the score the less accurate the data,
making a score of **20** more reliable than a score of **80**, but this
may not always be the case. A safe margin of error, until further
testing has been done to determine a safe cut off, may be to trust only
very low ratings, such as **5** or **10** and below. Naturally, the
geographic region you are studying may impact what a safe margin of
error is for you.
