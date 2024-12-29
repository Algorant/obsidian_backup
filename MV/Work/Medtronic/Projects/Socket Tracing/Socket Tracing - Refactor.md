
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

### Parts needed:

- Creation of Structured Data with set columns
- Fuzzy Match of that Data
- Separating Matched and Unmatched Data
- Creating Master Data List (with date and OEM Source included)
- Populating Master Table with OEM Info for each OEM

#### Misc Issues
- OEM_Ctry was missing from direct sales when translated from SQL to python
- You need to add in the Install Base Filter to the flow at some later point, removed it for now
- 

