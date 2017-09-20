#ikewai-data

**Data Management Guidelines - University of Hawaii EPSCoR - ʻIke Wai: Knowledge of Water**


###ʻIke Wai Spreadsheet Guidelines

These guidelines apply to all ʻIke Wai datasheets. Use them with Excel spreadsheets, Open Office, Google sheets, comma-separated csv files, tab-delimited or plain text files - wherever data are stored in a linear or sequential way. The goal is to leave your data clean, simple, and calculation-ready, making it easier to pull data into any software, allow datasets to work together, reuse procedures and code, and store and retrieve data reliably now and long into the future. Your effort is an investment that will pay off quickly and for a long time to come.

**1. ORGANIZATION**

**Spreadsheet organization** should put variables across the top, in columns, and observations running down the spreadsheet, in rows. That way each column contains identically structured and formatted data of one type. The first column ideally holds a unique identifier (ID) for each row (such as a simple sequence of numbers, or a sample ID if used for exactly one row in the spreadsheet).

**Column headers** should indicate data content, include units if any, and may use underscores and dashes. Do not include any other special characters such as slashes, parentheses, commas, spaces, symbols, or diacritical marks (ʻokina, kāhako). Column headers must be restricted to the top line only. Column headers should be unique within a spreadsheet. It can be helpful to re-use identical column header names among spreadsheets where the meaning also remains identical. 

**A Comment or Notes column** can be used for notes that apply to individual lines. In conversion to csv (comma-separated value format), entries in any text column with commas must be set off with quotation marks “ ” around the entries that contain commas.

**Formatting.** Usually, working with the default of left-justified text and right-justified numerals is a good visual check on values, decimal points, and significant digits. Do not center-justify. Do specify number of decimal points and limit significant digits where appropriate (“precision as displayed”).

**BEFORE**: This spreadsheet may be pretty to look at, but it is not calculation-ready.


**DURING**: Here are some of the changes that have to be made.


**AFTER**: Samples have meaningful unique IDs, and variables and formats are calculation-ready.


**2. OBSERVATIONS**

**Units** should be indicated in each column heading with a measurement. The regular guidance with column headers applies here. In writing units, do not include any special characters including slashes, parentheses, commas or spaces. Underscores and dashes are allowed.
   Example: header **SpCond_uS_cm** for Specific Conductance in microSiemens per centimeter. The standard substitution for “micro” is “u” to avoid using the Greek symbol “mu” (μ), a special character.

**Use NA** (not n.a. or na or N/A) to indicate data not acquired. A blank cell implies that an entry is still to be filled in. Programs like R have simple commands to disregard NA (treating them as blank or missing rather than zero during analysis), so NA is the most widely used for uniformity and consistency.

**BDL**. If a lab measurement is Below Detection Limit, a simple convention is to enter a value that is one-half (½) of the detection limit. Do not enter “<0.01” or “BDL” – these are text entries and will mangle quantitative work. If needed, use a separate column to retain any original lab-reported text entries.


**3. FORMATS**

**Filenames** should briefly indicate data content (such as isotope, geochem, microbial, salinity) plus an idea of space or time scale (such as subproject, aquifer, island, year)  for easy identification. Filenames and folder names must not include special characters, and should not include spaces. Underscores and dashes are allowed.

**Dates and Times** are **CRITICAL** pieces of information, and we must treat them consistently.
Dates should be given as **YYYY-MM-DD**.
Times must always use 24-hour time: **hh:mm** or **hh:mm:ss**.  Do not use AM or PM.
DateTime format within a single column is **YYYY-MM-DDThh:mm**.

**More on Dates and Times**. Note that the “**T**” between YYYY-MM-DD and hh:mm (or hh:mm:ss) is standard, and also forces Excel to treat the entry as text and keep the format intact. If the T is omitted, or a space is used in place of the T (sometimes permissible), Excel automatically imposes its own (often misleading) formats instead, so please include the T in spreadsheet cell entries for DateTime. For this project all times are assumed local HST. 
   Data in the ʻIke Wai project spans multiple centuries. Use **YYYY-MM-DD** format for **ALL** data. Note that for casual use, you can also use **YYYYMMDD** (no dashes) within a text string or filename. If you use a date within a filename or column name, you MUST use the sequence YYYYMMDD or YYYY-MM-DD. Do not use a different order, do not use slashes, and do not shorten the 4-digit year.
   If you have Date and Time data you must provide DateTime format as the official record. If you wish, you may ALSO have, in addition, a separate date column and time column for your own use.

**Latitudes and Longitudes:** All latitudes (y, or N-S) and longitudes (x, or E-W) should be in **decimal degrees**.  Do not use degree minute second or decimal minute formats..Do not include letters (such as N or W) with these entries: they should be simple numeric values.  In Hawaii, longitude will be a negative number. Column headings should include the full word “Latitude” and “Longitude”, not abbreviations.

**REVISED**: Include more data columns if they help you see, track, sort, or select information more easily. Here, site information could be a separate file, or can be incorporated if it simplifies analysis.


**4. DATA DEFINITIONS**

**A Data Definitions page** is a separate sheet to add definitions or descriptions for each column header, including full names of abbreviations and all units. This is also the place to include equipment notes, lab information, lab methods, detection limits and their numeric substitutions, and any other general observations or notes that do not have a place within the spreadsheet but need to be kept with the datasheet. If exporting a workbook as csv files, this can be saved as a separate page, possibly as text rather than csv, and should be kept with the data files as **scientific metadata** (e.g., similar name, zipped together).

If you have **geospatial coordinates**, the Data Definitions page **must** include a description of **(1) the source** of the geospatial coordinates (e.g., field-measured with GPS, or specific phone app; estimated visually from Google maps in the lab; GPS from earlier site characterization; pre-existing source such as CWRM well record, etc.), and **(2) the datum** of the source.

**EXAMPLE** of a Data Definitions sheet to accompany a dataset:


**5. BEST PRACTICES**

**Dont’s**. Do not merge cells. Do not insert blank rows. Do not require colors, fonts, etc. for interpretation. Do not insert text along with numbers in a cell (e.g., “27.0 m”, “< 0.03”). Do not include more than one piece of information in a cell - add another column if necessary. Do not leave blanks (NA preferred).

**Other notes**. The final copy should be fully readable and interpretable as undecorated csv or text files, exporting one file for each workbook page. If multiple files are needed to characterize a complete dataset, they should usually be kept together and made available simultaneously. Zipping files together to make a complete data package, including the Data Definitions page as a file, may be a good storage decision.

For **geospatial coordinates**, datum is most likely to be NAD83 (“ North American Datum 1983” - e.g., most state GIS files) or WGS84 (“World Geodetic System 1984” - e.g., most GPS units and Google maps), but you should know rather than guess. IF the datum is neither WGS84 or NAD83, you must specify the datum in the column heading (e.g., Latitude_NAD27). If these terms are new to you, please read geospatial data guidelines for background. Again, know and record rather than guess.

**Codes**. You may need to define group-accepted identifiers or codes to be used uniformly in field notebooks, lab spreadsheets, analyses, etc. These could include consistent abbreviations for Expeditions, Site names, Sampling events, Sample numbers, Laboratories, Methods, and Researcher name designations (e.g., first initial plus last name). These lists can be determined ahead of time, should be included in the Data Definitions page, and should be agreed to and used consistently by all of the relevant cooperators in the project. Otherwise it becomes very difficult to later reconnect field data, lab data, and the wide variety of subsequent analyses and visualizations back to each other, to the place and time and context they came from, and to samples and analyses over the time and space of the entire project. 

**Calculation formulas** should normally be removed from the spreadsheet once complete. For repository use, these can be copied and pasted as value-only, with a list of conversion formulas or calculations stored on the Data Definitions (scientific metadata) page. For repository storage and program use, single page flat files in .csv or text formats are strongly preferred. However, IF calculation formulas in an Excel spreadsheet are part of your documentation of your work and the way you will share that work, you may store BOTH an Excel workbook or spreadsheet with calculations AND duplicate values-only simple .csv or text format files for longevity, but must provide both.

**More situations will arise** than are described here. Default choices should favor clear documentation, uniform standards, and simple formats. Your finished files should be human-readable, machine-readable, and computation-ready. For further guidance, please consult the excellent data management resources at [New Mexico EPSCoR](https://www.nmepscor.org/data_portal/data-management-document-training) and [DataONE](https://www.dataone.org/sites/all/documents/DataONE_BP_Primer_020212.pdf).
 
**Want more resources?** Check out [Data Organization in Spreadsheets](https://peerj.com/preprints/3183/); go into deeper detail with this [Data Carpentry lesson](http://www.datacarpentry.org/spreadsheet-ecology-lesson/); or see why these guidelines are important when [sharing data for collaboration](https://peerj.com/preprints/3139.pdf). See USGS [Data Definitions](https://nhd.usgs.gov/NHDDataDictionary_model2.0.pdf) example.


This [spreadsheet example](https://docs.google.com/spreadsheets/d/18O8ZBmzKx5ftix5-Hkz8sMj7fFLtMiLqhye2BUhTDog/edit#gid=0) illustrates a number of the guidelines described.

Author: Ouida Meier, PhD, ʻIke Wai Data Manager, rev.20170920


### Next section to come: Special considerations for geospatial data

