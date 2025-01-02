
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

# Parts needed:



#### Misc Issues
- OEM_Ctry was missing from direct sales when translated from SQL to python
- Standalone has many products which are not categorized anywhere yet, can find them with Material ID where Product Name is Nan (and can be filled in using lookup table that matches product names. Cap 20, capt 35, etc)
- Need account director lookup created (Linda berry, kiyo, robin keene, etc)
- Note: Override needs to be before the Cust_ID column matching because lots of things are joined downstream of it
-  COL Check Step 9 vs alteryx: Missing certified cust and regular date (modified ac.gi date) columns, 40 vs 42
- 

