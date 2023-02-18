# goa-ai-data-reports (in progress)

## Overview
GOA and AI data reports summarize data from the trawl survey each year. These reports provide detailed survey summaries for a technical audience. The scripts in this repo pull text from [Google Docs](https://drive.google.com/drive/folders/1UAQKChSuKohsRJ5enOloHPk3qFtk5kVC), turn them into R Markdown files, and knit a report in .docx format summarizing survey data and some basic information about the survey. 
## General workflow
To create the full report, 
- start with `09_create_report_contents.R` and run the whole thing. This will build the tables, figures, and in-text values used in the report.
- When you're ready to build the full report in .docx, check the `tabledate`, `figuredate`, and `reportvaluesdate` in `00_report_settings.R`, and run `10_knit_report.R`. This will produce one .docx for the body of the report, and will draw in appendices from their sources.
- A smidge of post-processing is needed in Word: check table widths, order of appendices, and the headers (in navigation pane) to confirm that the scripts have run and the report draft is ready.

![Diagram of report structure](img/DataReportDiagram.png)

> This document is for informational purposes only and does not necessarily represent the views or official position of the Department of Commerce, the National Oceanic and Atmospheric Administration, or the National Marine Fisheries Service. Not to be cited without permission from the authors.

### Structure

As of February 2023, the sections of the report are as follows:

- Preface - drawn straight from google drive
- Abstract - drawn straight from google drive
- Introduction - drawn straight from google drive
- Methods - drawn straight from google drive
- Results 
  - Results by Area - drawn straight from google drive
  - Results by Species - drawn from RMarkdown and mixed with text sentences from google drive

- Citations
- Appendix A: strata specifications and locations
- Appendix B: Fish and invertebrate taxa encountered - produced with R code
- Appendix C: Length-weight relationships
- Appendix D: Bottom temperatures and surface temperatures

### A note about creating tables and figures
Tables "3" and "4" (CPUE and biomass by survey district and depth, and CPUE and biomass by INPFC area/stratum and depth, respectively) are currently generated outside this code by Paul, saved to the G Drive, and then referenced from there. In the future we want to automate these tables, but for the AI 2022 report this system worked pretty well and helped us share the work.

### A note about using summary tables vs. straight tables from RACEBASE
This report uses biomass and CPUE summary tables from the AI schema. Another way to produce these tables is to start with the raw tables from RACEBASE and do the summarizing in R. 

## Existing documentation
There are instructions for creating the tables and figures for the GOA data report currently in `G:/AI-GOA/Instructions&Procedures/Data Report`. Our goal is to take these and turn them into a Markdown file with documentation. 

## This code is maintained by:
**Margaret Siple** (margaret.siple AT noaa.gov; @MargaretSiple-NOAA)

**Bethany Riggle** (bethany.riggle AT noaa.gov; @bethanyriggle)

**Alexandra Dowlin** (alexandra.dowlin AT noaa.gov; @AlexandraDowlin-NOAA)

Alaska Fisheries Science Center
National Marine Fisheries Service 
National Oceanic and Atmospheric Administration
Seattle, WA 98195

## NOAA disclaimer
This repository is a software product and is not official communication of the National Oceanic and Atmospheric Administration (NOAA), or the United States Department of Commerce (DOC). All NOAA GitHub project code is provided on an 'as is' basis and the user assumes responsibility for its use. Any claims against the DOC or DOC bureaus stemming from the use of this GitHub project will be governed by all applicable Federal law. Any reference to specific commercial products, processes, or services by service mark, trademark, manufacturer, or otherwise, does not constitute or imply their endorsement, recommendation, or favoring by the DOC. The DOC seal and logo, or the seal and logo of a DOC bureau, shall not be used in any manner to imply endorsement of any commercial product or activity by the DOC or the United States Government.

## License
Software code created by U.S. Government employees is not subject to copyright in the United States (17 U.S.C. §105). The United States/Department of Commerce reserve all rights to seek and obtain copyright protection in countries other than the United States for Software authored in its entirety by the Department of Commerce. To this end, the Department of Commerce hereby grants to Recipient a royalty-free, nonexclusive license to use, copy, and create derivative works of the Software outside of the United States.
