# NYC Restaurant Inspection Data Cleaning with Excel Power Query

A data cleaning project on real government inspection records: fixing corrupted text, dates, phone numbers, and ZIP codes using **Microsoft Excel (Power Query)**.

**Dataset:** DOHMH New York City Restaurant Inspection Results (NYC Open Data, downloaded 16 Oct 2026)

## Results

| | After cleaning |
|---|---|
| Rows | **292,614** |
| Columns | **26** |

## Problems found and how they were fixed

| Problem | Fix |
|---|---|
| Duplicate rows | Removed |
| Placeholder inspection date 1900-01-01 (restaurants not yet inspected, all other fields empty) | Rows removed |
| Restaurant names with broken characters (e.g. PANZÓN, CAFÉ) | Characters repaired |
| Extra spaces in names and street names | Removed |
| Mixed upper and lower case in names | Standardized to upper case |
| Phone numbers with underscores, missing or extra digits | Kept only valid 10-digit numbers, others set to Unknown |
| ZIP codes that lost the leading zero (e.g. 7071) | Padded to 5 digits (07071) |
| Building numbers (e.g. 10-39) turned into dates by Excel | Set to Unknown (cannot be recovered reliably) |
| Borough = 0 | Set to Unknown |
| Latitude and longitude = 0 | Set to empty |
| Grade codes N, Z, P and empty grades | Renamed to Not Yet Graded, Grade Pending, Grade Pending (Reopening), Not Graded |
| Empty cuisine and violation fields | Set to Unknown / No Violation |
| Inspection type with two pieces of information | Split into INSPECTION_CATEGORY and INSPECTION_STAGE |
| Useless columns (RECORD DATE, Location) | Removed |
| Inconsistent column names | Standardized (upper case with underscores) |

**Note:** a restaurant appears on several rows when an inspection finds several violations. These rows are not duplicates and were kept. Some critical-flag values (Not Applicable with a violation recorded) come from the source data and were left unchanged.

## Files

- restaurant_inspection_raw.xlsx - raw data sample
- restaurant_inspection_Clean (zipped CSV) - cleaned data

## Tools

Microsoft Excel · Power Query (M language)

## Author

**Basmala Amgad** - Data Entry & Data Cleaning
