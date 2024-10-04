

#### Glossary

- [[Microstream]] = [[Philips Microstream]]
- Socket
- [[Mindray]]
- Consumable
- [[Baxter]]: socket vendor
- [[Alteryx]]: software that currently houses the fuzzy matching process for [[OEM]] vendors to our data
- Jerusalem
- MDT = Customer Master Data Management Team ?


### File List

- [[MDT Cust Master]] : The master list of matched customers so far with [[Medtronic]] sales data and [[Philips Microstream]] data.
- [[Philips Zero Consumable Matching]]
- [[Philips Master File]]: The master file of customers matched between [[Philips Microstream]] and [[Medtronic]] sales
	- Sockets or consumables?
- Socket Sales File
	- For [[Allison]]
- OEM COMM SOCKET
	- Smaller, basic columns, for [[Tzahi]]
- 


### Notes
- Assumptions:
	- The State field is almost always correct
	- Consumable details would be very similar to the socket file details
	- James: tried running [[Baxter]] against current [[Philips Microstream]] process and found several matches, because they would sell to same hospital as [[Philips Microstream]]
- Alteryx approach: Fuzzy matching on certain criteria
	- Name, City, State, 5 digit Zip
	- Interesting note: Running it multiple times continued getting matches
		- Why is this ???
- MDT Customer Master has columns like `Sum_BASE_UOM_NET_QTY_TRADE` and `Sum_CNTRCT_DOLLARS` which can be used to prioritize matching (top 100/250 or top 20% etc)
- Procedures / Basic rules:
	- Prioritize Facility over the Address whenever possible
	- Use MDT CustomerID for tiebreakers, choose the more recent one (higher number)
	- The MDT List has ability to override the matching list, because that is our current "source of truth" that can be updated, and those changes should be reflected in end product
	- In [[Philips Microstream]] process, street address was originally not included, now it is
	- We typically send to hospitals, not to anything downstream (doctors, specific wings, etc if just hospital exists)

### EDA Analysis
- Master List:
	- 16,000 total customers
		- top 500  is 67% of sales
		- top 1000 is 80%
		- top 3000 is 95%

### Questions
- What is `MATL_HRCHY_LVL5` column in MDT list? Relevant?
- What are the situations and information where similar records need to be kept?
	- Permutation column approach, "alternate_name", etc
- Idea: for overrides, keep top 2 records, have a column called "next best ID" and only keep that ID from the [[MDT]] list
- Consider using UPPER or LOWER (all uppercase or lowercase) during matching to reduce duplicates, 
- Same with manipulating common abbreviations: St, Rd, Ave, Pkwy, Ln, to be universal etc



#### Reconcile Master List
- [ ] Evergreen example
	- [ ] 4 entries from Philips, to 3 different customerIDs, top and bottom one the same
	- [ ] It's almost always just to the hospital that we sell to
	- [ ] One of them is blocked, why?
- [ ] Things to look at
	- [ ] No consumable scrub list
		- [ ] Alternative? 
- [ ] 'Street' column can act as filter and match on 'Address'
- [ ] Start excel files of the overrides


----

### Meeting Notes 

#### Workshop Meeting on 11/14

##### Question:
- How do I access MITG_Main?
	- Alison gave me credentials, through teams and email

##### New Methodology
- Take ZC List
- Match without customer ID on MDT with Consumables
- Basically fuzzy match process

---

#### Meeting on 11/28/23 about 
- Guessed at alignment for rep type, EAM vs ??? for Philips
- Only aligned customer reps with consumables of past 2 years
- Cross matched tables with alignment
- Primary rep type (one per product), or see across all diff types
- Product, customer number, and rep type and reps
- Type of customer, alignment rules, etc
