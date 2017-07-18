# ikewai-data

**Data Management Guidelines - University of Hawaii EPSCoR - Ike Wai: Knowledge of Water**


### Ike Wai Spreadsheet Guidelines

**Your data are precious.** Think how much cumulative time, money, and effort has gone into collecting each line of data or each spreadsheet you have generated. Your spreadsheets are the way you preserve these numbers for immediate use in multiple software programs and tools as well as long-term use in an unknown future. Our datasheets must be both machine-readable and human-readable. (Write data for machines, and write code for humans.) Another motivation: much of the data we produce in our lifetimes will live in spreadsheets rather than make it to a repository, so most of the time we must all act as our own data curators. These guidelines will help capture essential information needed by your future self as well preparing data for a formal repository or data publication.

These guidelines and requirements apply to all Ike Wai datasheets. They apply to Excel spreadsheets, Open Office spreadsheets, Google sheets, csv files, tab-delimited files, text files, etc., where data are stored in a linear and sequential way. 

**Spreadsheet organization** should have variables across the top, in columns, and observations (including sequential observations) running down the spreadsheet, in rows, ideally with a relevant unique identifier for each row.

**Filenames** must be able to stand on their own, unequivocally. The filename should include a brief indicator of data contents plus a designation for the smallest collective level of granularity that the data within the file represents. Brief indicator of data contents: Isotope? Geochem? Collective level of granularity: is it data for one well? One site? One expedition? One island? One year? This is usually location-related or time-related, or may need both to designate a space-and-time window.

**Column headers** must be restricted to top line only, and must have no spaces, slashes, parentheses, commas, or other special characters: only dashes and underscores are allowed in column headings. Diacritical marks used in the Hawaiian language may be included in text or column entries, but not in any column headings or filenames. Special characters, merged cells, and spacer lines all pose problems for software programs ingesting the data. No two columns in a spreadsheet may have identical column headings. Consistent use of column headings in multiple spreadsheets is extremely helpful.

**A Comment or Notes column** may be used for notations that apply to individual lines; be aware that in conversion to csv (comma-separated value format), all entries in this column or any text column with commas will need to be set off with “ ” around text entries.

**Use NA** (not n.a. or na or N/A) to indicate data not obtained. A blank cell implies that an entry is still to be filled in. Programs like R have simple commands to disregard NA (treating them as blank or missing rather than zero during analysis), so NA is designated for uniformity and consistency.

**A Data Definitions page** is a separate sheet to add definitions or descriptions for each column header, including full names of abbreviations and all units. This is also the place to include equipment notes, lab information, lab methods, detection limits, and any other general observations or notes that do not have a place within the spreadsheet but need to be kept with the datasheet. If exporting a workbook as csv files, this can be saved as a separate page, possibly as text rather than csv, and should be kept with the data files as scientific metadata (e.g., similar name, zipped together). 

**No calculation formulas** should remain in the spreadsheet once complete: for repository use, these should be copied and pasted as value-only. A record of any conversion formulas or calculations used should be kept on the Data Definitions or scientific metadata page. 

**Formatting:** in a workbook like Excel, the default of left-justified text and right-justified numerals is a good visual check on values, decimal points, and significant digits. Do specify number of decimal points and limit significant digits everywhere that it is appropriate (“precision as displayed”).

**Dates and Times** are CRITICAL pieces of information, and we must list them consistently. Dates should be given as YYYY-MM-DD (or can use YYYYMMDD within a text string). Times must ALWAYS be in 24-hour time (and for this project all times are assumed local HST). These may be kept in separate columns. DateTime format within a single column is YYYY-MM-DDThh:mm with an additional :00 if seconds are being recorded. Note that the “T” between YYYY-MM-DD and hh:mm , while standard, has the further benefit that it forces Excel to treat the entry as text and keeps the format intact. If the T is omitted, or a space is used in place of the T (sometimes permissible), Excel automatically imposes its own proprietary format displays instead, so please include the T in spreadsheet cell entries for DateTime.

**Latitudes and Longitudes:** All latitudes and longitudes should be in decimal degrees, in Hawaii latitude will be a negative number. Column headings should be “Latitude_datum” and “Longitude_datum”, where datum is WGS84 (preferred datum for project). All entries in a column should be the same datum. If you are converting from another datum, such as NAD83, leave the original latitude and longitude in its existing format and specify its datum, then convert also to WGS84 and enter those locations in two new columns. Retain both original and converted datum. Describe sources of location data, datum used, any conversion details (software, URL), and projection, if any, in the data definitions page.

**BDL:** If a lab parameter measured is “below detection limit”, the convention is to enter a value that is ½ of the detection limit (not “BDL” or “<0.01” – these are text entries and will mess up any quantitative work). Use the scientific metadata page to specify detection limits and your substitution for each parameter being measured.

**Units** should be indicated in each column heading with a measurement; do not use symbol characters or spaces. While dashes and underscores are permissible, slashes, spaces, and parentheses are not readable as column headers by many programs. Example:

SpCond_uS_cm  for Specific Conductance in microSiemens per centimeter. (Note: the abbreviation for micro is written as u to avoid using the Greek letter "mu" as a special or symbol character.)

**Other notes:** Do not merge cells. Do not insert blank rows. The final copy should be fully readable and interpretable as undecorated csv files, exporting one file for each workbook page. For repository storage and program use, flat files are strongly preferred over relationally dependent structures, and the longevity of software-independent plain text files is strongly preferred over software-dependent workbooks. That said, over shorter time frames it is permissible to ALSO upload an Excel file that is a duplicate of (not a replacement for) exported csv files if they are kept together and made available simultaneously.

**Identifiers** such as site names and site codes that may used by multiple people in a project must be well chosen, well documented, and consistently used. These can serve as the reference basis for name codes for sites and samples. Intuitive, readily constructible, and informative unique identifiers are preferred over arbitrary numberings.

**Codes:** You may need to define uniform group-accepted identifiers for: Expedition designation, Sampling code, Site code, and prospective or cumulative lists for: Sites, Samples, Expeditions, Sampling events, Laboratories, Methods, Sampling events, and Researcher name designations (e.g., first initial plus last name). These should be included in a set of data definitions. It is critical to agree upon, share, and consistently use codes across the project in order to be able to link data and observations long after the original researchers' initial engagement with the data.

More situations will arise than can be described here. The default choices should always favor clear documentation, uniform standards, and simple formats. For further guidance, see [New Mexico EPSCoR](https://www.nmepscor.org/data_portal/data-management-document-training) and [DataONE](https://www.dataone.org/best-practices/choose-and-use-standard-terminology-enable-discovery).

###Next section to come: Special considerations for geospatial data###

