
# Primary

## Projects
- [[Socket Tracing]]
- [[VA Work]] 
- [[Commercial Wind-Down | Client Termination]]
---

## Tasks
- [x] Add clients 
- [ ] Look for other prime IDN accounts
- [ ] Update task planner
	- [ ] Audit (account update list) by tuesday the 15th
- [ ] Make dashboard work checklist
- [ ] Create [[ACM Master DB]] template and mapping
- [ ] Update [[Philips]] and [[Testing Suite]]
- [ ] Refactor into Components
- [ ] Show functionality in [[Knime]]
- [ ] meet with mallory once completed
- [ ] Update [[Philips]] consumables data and apply the override file
	- [ ] Apply on comparison string, might need multiple
	- [ ] Alternatively: name and cust_id combo
- [ ] Learn who is mirth expert now?
- [ ] Get location of salesforce data from [[Allison]]
- [[BIS INVOS TABLE AND DASHBOARD]]
	- Documentation
		- Give the specifics for each OEM
			- what dates we have info for
			- what their main business is (bis, invos, microstream) (percentage?)
			- whether mostly us or mostly international (percentage?)
			- date last updated
	- Create standardized columns for table
		- Add Date Processed and Date Uploaded
	- Organize OEMs into this format
	- Create One big upload function
	- Upload to table
	- Refactors
	- Update Files and Get Date Timestamps



### Other
- For OEM
	- Match Intellivue as Product Name
	- Match MP5 as Product Name
- Process for checking what source it's coming from:
	- Check Channels: MDT is medtronic, or OEM is OEM, go to the customer
		- Check consumables after that, if consumable column is yes, then direct sales
		- if no then its install base
- Process for top 200 checklist
	- check for dups in name, ie if phoenix children's, search phoenix children's in rest of it
	- verify numbers in raw data file
	- validate bed data 
		- coming into dataset
		- and bed data googlable? and how far off is it
	- check raw procedure file data
	- is this idn level or is this sold to?
		- check consumable piece and it will tell you
		- if its 0 consumables, flag that its 0 idn
	- 
- OEM part ID, mat_lvl6_num, only the hardware
	- install base num from hardware
	- filter
	- agg and sort by 
- idn vs mid analysis
- [ ] Create Master Uploader
	- [ ] Create Way to Update individual Clients
		- [ ] Take master file for each, have an "update" function for each one
		- [ ] Spit out Matched, Unmatched, and Transactions for each one
		- [ ] Once created, can make a consolidated CID file
		- [ ] Document specifics on each client in plain english
		- [ ] Create QA flow for anyone wanting to update unmatched things or etc
		- [ ] Once uploaded, create change table or monitor table
		- [ ] Test new uploads
	- [ ] Flow into master upload file
	- [ ] Monitor changes, which OEM, and what type (socket or consumable)
	- [ ] Push that into ES_MITG table
- Meeting Discussion 5/13
	- [ ] [[TODO]] Top 100, 200, 500, 1000
		- Standalone install base + oem descending
			- note: philips should not show up as a customer there
	- Certified customer field:
		- Once checked, gives a yes/no or 1/0, whatever to mean that it's clean and good for the dataset
	- Critera of top 200
		- Sort by standalone desc
		- sort by oem desc
		- sort with both added together
		- have a column showing what they have in common
		- Sort by philips sockets, install 
	- Summary for direct sales:
		- At month transaction level per customer per item


---
