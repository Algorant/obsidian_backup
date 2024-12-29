
## Components

#### Parsing / Cleaning / Filtering
- Create empty ACM Table
- Create Updatable Master Fuzzy File
- Organized by [[Socket Tracing - Documentation#Client List ||Client]]
- Creating [[Testing Suite]] for Processing
- 
#### Uploading
- Updating Master List
- Updating Matched and Unmatched Lists
- Upload to ACM

#### Knime / Alteryx Integrations
- Individual scripts should be usable inside of these programs

#### Parts needed:

- Components from SQL
	- Direct Sales
	- Standalone Install Base
	- Bed and Procedures
	- MID Columns
- Components from lookup (current excel, should be SQL)
	- Override Table
	- Product Matching Table
	- Customer Validation Table
	- 

#### Misc Issues
- OEM_Ctry was missing from direct sales when translated from SQL to python
- Standalone has many products which are not categorized anywhere yet, can find them with Material ID where Product Name is Nan (and can be filled in using lookup table that matches product names. Cap 20, capt 35, etc)
- 

