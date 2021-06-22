###### tags: `meeting notes` `rgi`

# RGI Meeting notes

## June 22 17H 

- Update Stephan / Fabien about scripted GLIMS data scraping
    - regions 1, 13, 14, 15 ready. Minor problems in GLIMS, now reported [here](https://github.com/GLIMS-RGI/glims_issue_tracker)
    - short presentation of workflow and where to fetch the data
    - discussion with Bruce about ways forward: we basically scraped the entire GLIMS database and made conversions that should happen in GLIMS. Bruce agreed to bring this up to the next budget meeting.
    - Add-on from Bruce: `submission_id` as another way to select glaciers as a batch in one submission
- Update Frank / Philipp about outlines generation
    - Elsemere Island next step for Philipp
    - Agreed on ways forward
- Update Bruce about GLIMS
    - 10 months ago GLIMS became a DAAC product (budget is more secured but more requirements) https://lpdaac.usgs.gov/ -> this came with background work not visible to the community
    - Data ingest happened recently: some LIA stuff and Norway things from Liss
    - Issues MultiPolygon to Polygon (about done)
    - Working on the outcrops to interiors as well
    - Fiscal year Oct 1 to Sept 30 -> can plan for higher funding? Currently half a person.
- Attributes discussion
    - Based on Frank's table
    - Rename "Classification" to "GlacierType"
    - TermType stays? **TerminusType** is the consensus
    - "Surging" becomes **SurgeType**
    - Keep "Shelf" in TerminusType
    - No "Shelf" in glacier type
    - no "Rock Glacier" and "Ice shelf" as glacier type
    - keep "Shelf" as "TerminusType"
    - retire "Regenerated"
- TODOs for near future:
    - Fixing the attributes
    - Send an email to RGI community explaining the workflow and asking for contributions
    - RAGMAC talk
    - ?


## June 01 17H 


- Update Stephan / Fabien about scripted GLIMS data scraping
    - scripting is advancing - looks promising, close to point of no return
    - RGI 01 already existing (1 glacier difference)
    - Iceland needs to be fed to GLIMS as divides 
- Update Frank / Philipp about outlines generation
    - Philipp: Northern Greenland almost done
    - Frank: Baffin Island dataset ready, some divides still not good
- Timeline 
- Update region files. See my first draft for the new region files here: https://cluster.klima.uni-bremen.de/~fmaussion/misc/rgi7a_v1/l0_regions/ . The code and some info about what changed (almost nothing) is found here: https://github.com/GLIMS-RGI/rgitools/blob/master/notebooks/rgi_60_corrections/01_modify_rgi_reg_files.ipynb . Comments welcome.
- Discussion: RGI05 sub-regions. Do we leave it as is for RGI7, or do we want to do the effort now? 
    - RGI 7.1
- Attributes discussion (continued)
    - Nice examples from Frank
    - GLIMS is the reference - we need a subdiscussion

**Notes send by mail:**

Thank you for the nice discussions yesterday. I would like to summarize the most important points here:
- the scripting of "GLIMS to RGI" is moving forward. There are some small bugs to overcome (related to the nunataks -> interior polygon conversion) but this seems manageable, and Stephan was already able to generate the RGI region 01 (our first RGI7 file!). We will continue to work on this and share the scripts and the data soon.
- the mapping from Philipp and Frank is also going forward, they've agreed on a deadline at the end of June for submission to GLIMS. Philipp will continue to work at 80% for geoville and would be keen to continue to work on RGI with us after that.
- we expect no bottleneck from GLIMS because Frank and Pilipp know how to prepare the files nicely
- Bruce will need to ingest Iceland (Region 6) RGI outlines into GLIMS because the current outlines there are not divided
- Bruce and Fabien will discuss a way to unambiguously identify a specific outline in GLIMS after download. This is currently not possible.
- For the region files: we agreed on my correction of Region 12 (Caucasus) and that no other changes will be made for RGI7. The next most urgent thing to address will be subregions in Greenland, to be tackled after RGI7.0
- Note that Alaska's region box in the eastern hemisphere is useless. We decided to keep it, but I think it should be removed some day.
- We continued the geomorphological attributes discussion. Nice examples from the complexity of the situations from Frank. I am going to try to summarize the general agreement here, even if Frank might have slightly different opinions:
    1. Any attribute in RGI should be strictly consistent with GLIMS and also available in GLIMS (even if not populated)
     2. Most attributes might be unpopulated for RGI7.0. If they become populated by the community, we will need to have a simple way to feed them back to GLIMS
     3. Many of the problems listed by Frank are real issues, but from my point of view they are "pre GLIMS" problems, i.e. inventory problems, not RGI problems. RGI will not be able to decide how ice aprons need to be linked to glaciers or not, for example. This should happen before submission to GLIMS
      4. Therefore, the decision to be taken now is: what do the glacier attributes we'd like to see in GLIMS (and by extension, in RGI) should look like. This decision is left for the next meeting.


## May 17 17H 

- Stephan
- Update Philipp / Frank:
    - list of regions which are already in GLIMS
    - list of regions which are not in GLIMS (3,4,5,7,11,16,17,18) - example region 11 need update
    - Regions 4 5 ready by the outlines and close to ready by divides
    - Other regions still in the making
    - Quality assessments on other regions with big errors
- Update Stephan
    - GLIMS - GAMDAM comparison
- Discussion attribute on the table
- Apple contacted Philipp for OSM 
- Idea GGE or Microsoft for generation of RGI?????? 
- Michael:
    - RAGMAC mini conference with outlook RGI7
    - Which are the largest glaciers of the world? NSIDC technical report + paper : RGI as co-authors maybe?






## May 04 17H 

First meeting altogether. 

Updates
- Welcome Stephan! IACS approved, the current bottleneck is account creation in Innsbruck 
- Update Philip / Frank regarding glacier outlines
    - RGI regions 1 2 3 4
    - Philipp 5 6 7 8
    - Bottlenecks Elsemere Baffin go through outlines again (Baffin outlines very bad) both near ready now. Should be accomplished this week.
    - Northern Greenland by Philipp (was also awful)
    - According to Frank only region 3 may need outline refining
    - What about drainage basins?
- First tests on RGI7 beta generation in HMA (Fabien Stephan)
    - Current workflow:
        - Download all GLIMS outlines 
        - Select by analyst (here Sakai for GAMDAM)
        - Write out 
        - Update attributes and visual checks
    - Open questions:
        - Antoine Rabatel feedback
        - Why can there be more than one glacier with same GLIMS ID?
        - Centroid of glaciers: is lon-lat enough?
        - GLIMS workflow
    - Advantage of GLIMS based workflow are clear
    - Disadvantage:
        - You have bottleneck from GLIMS ingest
        - Will it work to select the correct dataset?
    - Feedback from community for 7.1

- Attributes

- very good suggestion from Michael: RGI7 should be empty from attributes that can't be done from GLIMS our automated.

- More money 

## Jan 21 21 Get-back-to-work meeting

- round of updates:
    - Fabien could run Bruce's script
    - Frank and Phil making progress with inventory work 
    - Phil is in Innsbruck 80% Geoville, 20% with Frank. Masterplan is missing
    - Bruce: RGI-on-demand having knock-on effects on ingesting, but still fixing some issues necessary. NSIDC is now DAAC, less autonomy for Bruce.
- start already
    - Region 1 to 4: 
    - Project management: 
    - 


## October23rd 2020 "Road to RGI" group wide meeting.

Notes are on [google docs](https://docs.google.com/document/d/1nxbCDiMGz04B8yN_gHR49w1rptSk7ye5YUipUQMpPh8/edit?usp=sharing)

## October 9th 2020 WG meeting preparation (telecon)

### Participants

Steering committee 

### Agenda

- Lay out a "roadmap to RGI7"
- Agree on responsibilities: 
    - Frank and Philipp will "create the RGI", based on GLIMS/Bruce "RGI on demand". Then the datasets as decided in the Table and WG wide meeting will be copy pasted in it 
    - Fabien will generate the "RGI on demand" using GLIMS API
    - Fabien will do the first quality checks and add attributes (e.g. DEMs)
    - Beta version will be checked by community
- More infos on the mail drafted to community


## August 18th 2020 New outlines submission meeting (telecon)

### Participants

Steering committee 

### 1. Subregion + Region discussion

- Bruce’s notes about the topic is on google docs 
- Changing the files online is some work (DOIs, more than one repository to update, documentation, etc.), but OK. The implementation is more complex.
- Long discussion about the current regions / subregions. Decisions: 
    - we make the smallest changes that are needed but don’t touch the “problem” regions like HMA.
    - Caucasus will be changed to incorporate missing glaciers in the South
    - Greenland will get new SUBregions with published outlines. Ask to Greenland research community if OK 
    - A border in South America will be moved a tiny bit in order not to cross a glacier complex. 
    - Have a note on the technical document about the changes and how to determine membership to a region (with centroid) 
    - Zürich will produce the final shapefile in iteration with Bruce and Fabien 
    - For the future: can we have an idea about how many subregions / regions are NOT following valley bottoms?

### 2. RGI Outlines discussion

- Frank & Philipp prepared a table + presentation about the current situation and a suggestion about the changes to make. Looking very good, but possibly some elements are still missing because the “RGI-on-demand” button might uncover other potential datasets. Decision: 
    - Bruce uses the RGI-on-demand feature and provides the results to Frank & Philipp for assessment. 
    - Frank & Philipp prepare a slightly updated document with more text explaining what this is about. 
    - The steering committee shortly assesses if this is ready to go
    - We organize an RGI-wide meeting first half of September to discuss and accept the working document

### 3. Other infos

- Michael:
    - NSIDC project with Ann Windnagel: find the biggest complexes for each region: found some errors in GLIMS/RGI which will be reported.
    - Romain Huguonnet’s global geodetic dataset is in review: discussions about how to share the data: aggregated series will be in Pangea, the Geodetic MBs at WGMS, but the full DEMs still in discussion.
    - Goal: mass-change time-series based on that dataset are in preparation
- Frank:
    - EU project: start working on a “LIA RGI”.


## July 27th 2020 RGI meeting (telecon)

### Participants

Steering committee 

### Agenda draft

- Regions file need update:
    - Caucasus glaciers not fully in a region boundary
    - Some glacier outlines across boundaries -> little tweaks but no big change for political reasons
    - Add level 2 regions for some regions, mostly Greenland
    - Obstacle: GTN-G regions have to agree
- Bruce:
    - All dev work has been moved from test to production (almost there at time of call)
    - Caveats: 
        - because of boundary issues not all glaciers are selected 
        - Format of RGI-on-demand data still not 1-to-1 with normal GLIMS downloads
- Frank:
    - Still working on getting data from various groups 
    - 9 datasets needed from Bruce, only two available atm
    - Alps: 2000 to 2003 diffs are small - sometimes the quality is less than 2003 because of bad scenes. Frank: not replace existing data (main argument: metadata with 60 scenes against 6 scenes for the 2003 data). Debate if these arguments are strong enough. Define and use the “decision matrix” with factors.
    - Northern Ellesmere Islands: outlines similar but ice divides very different - RGI seems more reasonable though and outlines same year, but very strange artifacts in the new data.
    - Next steps:
        - More datasets needed from Bruce to Frank
        - Philipp volunteers for the (confusion) decision matrix
        - New data submissions:  N. Ellesmere Island data have been ingested into GLIMS (for 1999, 2005, and 2015).



## July 6th 2020 "GLIMS freeze" RGI meeting (telecon)

### Participants

Steering committee 

### Notes 

- Outlines list Bruce are not in GLIMS yet (Alps, Prince William Sound glaciers, Argentina inventory are ingested recently)
- Availabilities over the summer:
    - Bruce is around 
    - Frank is around
    - Philipp is around - mid-september baby coming 
    - Regine is around (Oslo from 1 September on)
    - Fabien: one week afk August
- RGI on demand feature: alpha version was on server since a couple of months ago. Number of reported issues fixed. Current version on test server -> to be moved on the production server. Ingesting new outlines can be pretty quick. 
- Frank:
    - Plan A: use the RGI on demand feature - testing is going to decide how this works
    - Plan B: “Data integration” below. RGI6 as baseline, and replace the RGI6 outlines as submitted by the various groups (cut and paste). Caveat: attributes will be different. Advantage: easier maybe, given the number of datasets that need replaced.
    - Plan C: “RGI extraction tool” based on year + submission ID
    - No matter how we do: the datasets need to be in GLIMS for copyright issues. Once the decision is more or less done, the list of criteria can be decided upon
- Bruce:
    - Button is in good shape - where it does not work nicely probably a human will have issues as well (e.g. Patagonia and ice divides)
    - “Outlines working group” will meet again and discuss the details. 
- More discussions
    - Naming of RGI7 -> how to do with multitemporal versions. RGI2000 v7?
    - Sam Herreid data -> Frank writes to him


## May 5th 2020 Kick-off meeting (EGU telecon)

### Participants

Steering committee + Members + Contributors + Visitors (60+)

### Video recording

On youtube: https://youtu.be/q0Y26-X9z_o

### Notes

The slides are available [here](https://github.com/GLIMS-RGI/rgidocs/blob/master/presentations/RGI_KickOffMeeting_slides.pdf).

The notes are available on [google docs](https://docs.google.com/document/d/1m0qg_RCbxbNDT31IA-dNX3zESSylqwPg4cqCoMeZmAk/edit?usp=sharing) - feel free to comment on them!

[![](https://i.imgur.com/OkS1kGL.jpg)](https://youtu.be/q0Y26-X9z_o)

## April 14th 2020 (telecon)

### Participants

RGI Steering committee 

### Agenda draft

- RGI on demand alpha-release: 
    - first reviews are coming in
    - 5th of May call
    - revised timeline 
- Organisation of first WG call with all members (All):
    - Organise call for action - here the work for us is to engage and motivate the group:
        - See the agenda draft on google docs
        - RGI-on-demand testing and choice of outlines. Ideally, we want a smaller task force to be created for this (too many people detrimental)
        - RGItools and related tools: call for contribution and ideas
        - Organisation of a forum / issue tracker for community feedback regaring RGI6 and future betas of RGI7: see https://github.com/GLIMS-RGI/rgi_issue_tracker
- EGU slides for Frank's session
- AGU session? RAGMAG + RGI + GTNG from Bruce 
- Any other business?


## March 6th 2020 (telecon)

### Participants

Regine Hock, Fabien Maussion (late), Philipp Rastner, Bruce Raup, Frank Paul

Not present: Michael Zemp

### Agenda 

- Decide on the constitution of the working group
    - discussion about the members/contributors application
    - discussion about unclear cases - final list is now ready to be communicated
    - set up of a list of criteria that have to be clearly communicated to all as to what defines a "member" and a "contributor"
- Status of "RGI on demand" button
    - some issues with overlapping polygons that needed to be solved
    - beta release by April if everything goes well

### Action items 

- Regine: will draft an email to all applicant
- Fabien: will check the list again
- Frank: sends an email for the wide RGI meeting at EGU (or rather at the same time as planned in EGU, but probably telecon)
- Fabien: find a format for sharing info in an open manner.
    - I've opened a github repository for now, other suggestions welcome: https://github.com/GLIMS-RGI/rgidocs 

## January 9th 2020 (Zürich)


### Participants

Regine, Michi, Frank, Philipp, Matthias, Fabien, Bruce (remotely from 4 pm)

### Agenda

- Status of the proposal
    - Proposal is still in final review. Some key points need to be clarified by IACS Bureau, in particular wrt to GLIMS in the title or not. We will wait for IACS suggestion, and if they insist we can suggest the following subtitle: “Towards the automatic derivation of multi-temporal RGI products from the GLIMS database”.
- Finalize the call for contributions:
    - Most discussion was about the conditions for participation. Following the examples of other WGs, we now define “WG members” and “WG contributors”. See draft email below (looking good as is, in my opinion) 
- RGI-TOPO beta release
    - Fabien and Matthias made a demo. See https://rgitools.readthedocs.io/en/latest/dems.html . Some small updates are necessary but we will send this out to CRYOLIST soon.
- RGI version 7 timeline
    - We have a lot of work ahead of us! But the meeting was very motivating, and there is a clear path forward.
    - See attached [Gantt chart](https://docs.google.com/spreadsheets/d/1ZYFcPyYySrXSOf0mmv6zPWlntn91VUzO-OVgOA0Pb6E/edit?usp=sharing)
    - Most urgent milestones and responsible persons:
        - Call for data (Michi, Frank, Philipp, Paul): email to be sent to CRYOLIST after the “call for participation” from Fabien and Regine (i.e. right after WG approval)
        - “RGI-on-demand” button in beta-testing version (Bruce) (Feb 1st)
- Communication and outreach
    - Abstract for EGU2020
        - Fabien will write and submit a poster abstract to the “Glaciers from space” session
    - Website(s) and communication platforms.
        - We keep and update the current web presence: 
            - glims.org (Bruce has credentials) 
            - iacs.org (Regine has credentials)
            - We opened a new GLIMS-RGI github organisation. See https://github.com/GLIMS-RGI 


## November 6th 2019 (telecon)

### Participants

Michael Zemp, Regine Hock, Fabien Maussion, Philipp Rastner, Bruce Raup, Matthias Dusch

Not present: Frank Paul

### Agenda

1. WG title
    - After some discussion, we agreed on: "IACS Working Group on the Randolph Glacier Inventory and its role in future glacier monitoring."
2. Issues with diversity and group membership. How to move forward?
    - We agreed to keep the steering commitee as it is because it reflects the engagement of all members up to now. We change Michael's affiliation. 
    - We make some changes in the text about future membership and make clear that the "steering" comittee is here to "steer", not make aritrary decisions.
3. Task forces 
    - in the proposal we are now committing ourselves to do a certain work. I kind of made those "task forces" myself, so I would like to hear your views about it, and especially know if you are OK with committing to this.
    - Add a new task force to make it clear that generating the RGI is going to imply human decision (and some level of arbitrary). The steering commitee will have to do that.
4. Next steps
    - Submit ASAP. Start to work already, because "in one way or another", it will be accepted. 
    - Fabien will merge all the comments in the text and "wrap-it-up", send out for final review and submit early next week.
    - Suggested reviewers:
        - Pierre Pitte (Mendoza, Argentina): pierrepitte@mendoza-conicet.gob.ar 
        - Thorsten Seehaus (Erlangen, Germany): thorsten.seehaus@fau.de
        - Jon Ove Hagen (Oslo, Norway): j.o.m.hagen@geo.uio.no
        - Akiko Sakai (Nagoya University): shakai@nagoya-u.jp
        - Guðfinna Aðalgeirsdóttir (Iceland): gua@hi.is
        - Adina Racoviteanu (Aberystwyth, UK): adr18@aber.ac.uk

    - New RGI has to be delivered within 18 months in order to meet Copernicus deadline.
5. Any other business?
    - We agreed on a "in site" meeting in Zürich, Jan 9 afternoon (for Innsbruck to be continued on 10)
6. Status of DEM work. 
    - Advancing well! Thanks Matthias for all the work. Summary here: https://hackmd.io/kZ808zYwTlKZbdamrx1AtA
