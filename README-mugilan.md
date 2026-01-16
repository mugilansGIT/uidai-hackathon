This document records the exact work completed so far in Power BI

1.Objective

-> Load multiple CSV datasets

-> Clean and standardize data

-> Combine related datasets into a single integrated Master table
_____________________________________________________________________________________________________________________________________________________________________________________________________________________

2. Datasets Used
   
2.1 Enrolment Dataset

-> Source format: CSV (multiple files)

-> Loaded using folder-based ingestion

-> Contains enrolment-related counts and age metrics


2.2 Demographic Dataset

-> Source format: CSV (multiple files)

-> Loaded using folder-based ingestion

-> Contains demographic and age-group statistics


2.3 Biometric Dataset

-> Source format: CSV (multiple files)

-> Loaded using folder-based ingestion

-> Contains biometric and age-group counts
_____________________________________________________________________________________________________________________________________________________________________________________________________________________

3.Tools Used

-> Power BI Desktop Used For Primary analytics and integration tool

-> Power Query Editor Used For Data cleaning, transformation, and merging

-> CSV Files	Are Raw data source format

-> Folder-based ingestion Used For Automated combination of multiple files
_____________________________________________________________________________________________________________________________________________________________________________________________________________________

4. Data Organization Performed

Before loading data, CSV files were organized into three folders:

-> api_data_aadhar_biometric

-> api_data_aadhar_demographic

-> api_data_aadhar_enrolment
_____________________________________________________________________________________________________________________________________________________________________________________________________________________

5.Data Ingestion

All CSV files in each folder were automatically combined into three tables:

-> Enrolment

-> Demographic

-> Biometric
_____________________________________________________________________________________________________________________________________________________________________________________________________________________

6. Data Cleaning

6.1 Date Formatting

-> Date columns converted using Change Type → Using Locale

-> Locale set to English (India)


6.2 Location Standardization

State and District columns cleaned using:

-> Trim

-> Capitalize Each Word


6.3 Pincode Handling

-> Pincode columns converted to Text data type

-> Prevented incorrect numeric aggregation


6.4 Null Value Handling

All age and count columns had null values replaced with 0
_____________________________________________________________________________________________________________________________________________________________________________________________________________________

7.Merge Keys Used

The following columns were used as composite keys:

-> Date

-> State

-> District

-> Pincode


7.1 Merge Operations

1. Enrolment merged with Demographic using Left Outer Join
Resulting intermediate table: Merge1

2. Merge1 merged with Biometric using Left Outer Join
Resulting table renamed as Master


7.2 Post-Merge Cleanup

-> Expanded nested tables

-> Removed duplicate columns such as date.1, state.1

-> Disabled column name prefixing
_____________________________________________________________________________________________________________________________________________________________________________________________________________________

8. Storage and Access

All transformations are saved as (.pbix) format

Data can be accessed via:

-> Power BI Data View

-> Export to CSV if required
_____________________________________________________________________________________________________________________________________________________________________________________________________________________
