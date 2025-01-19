
# Components

- [[Direct Sales]]
- [[Standalone Install Base]]
- [[OEM Sales]]
- [[Product Matching]]
- [[Customer Validation]]
- [[Overrides]]
- [[Account Director and Sales Reps]]
- [[Cust_ID columns]]
- [[MID Columns]]
- [[Bed and Procedures]]
- [[Geolocation columns]]
- [[Time columns]]

### Uploading
- Updating Master List
- Updating Matched and Unmatched Lists
- Upload to ACM

# Knime / Alteryx Integrations
- Individual scripts should be usable inside of these programs

# Todo
- Automate nightly sql downloads
- Process into duck_db or leave as csv (with timestamp)

# Action Items
- IDNs
	- solidify who and maintain appropriately
- Override List and other things that should be Maintained
	- IDNs
	- Matching Table
	- Product Group List
- OEM follow up and missing pieces
	- Create relationships with each
	- Automate drops if possible
	- Zoll missing dates
	- Missing entire things for jacobi and alaris/bd
- Rep Alignment Sanity Check
- Allison Priority
- Date Alignment
	- Take maximum date for old OEM
		- Will call cutoff date, most recent complete date
- Product Category Duplicates
	- 



#### Misc Issues
- OEM_Ctry was missing from direct sales when translated from SQL to python
- Standalone has many products which are not categorized anywhere yet, can find them with Material ID where Product Name is Nan (and can be filled in using lookup table that matches product names. Cap 20, capt 35, etc)
- Need account director lookup created (Linda berry, kiyo, robin keene, etc)
- Note: Override needs to be before the Cust_ID column matching because lots of things are joined downstream of it
-  COL Check Step 9 vs alteryx: Missing certified cust and regular date (modified ac.gi date) columns, 40 vs 42
- Beds and procedures need to be summed and grouped by cust_mid (can be done in sql query)
- Step 9: in the OEM_ORIG_CUST_NM I have an error, think I did string of "sold_to_customer_name" instead of the column
- Step 12, the global location columns, GSDM_GEOGRAPHY are missing (Geo region and geo sub region)
- The GE OEM file is not complete on product matching, you have approx 893 items that do not match. Will remove for now.

## Standalone Python
- Current structure
	- main.py
		- utils
			- data_processor.py class
			- data_merger.py class
			- file_utils.py
			- db_utils.py


## Misc

Alright now we will do our first merge using DataMerger. I have a dir in main called PREPROCESSED_DIR and within it are two files: processed_direct_sales_data_0119.csv and processed_standalone_data_0119.csv. These are the output of the previous data processing steps 1 and 2.

I would like to use the same latest_file and prefix structure to read in these files when needed. I will also be merging dataframes directly from the reference_files dir without needing to process them, so I need functionality to read in both.

The first actual merge would be merging standalone and direct sales. I would like to print out the columns of each dataframe read in before beginning for debugging purposes and to catch errors, and then begin the merges.