

## Doing Master File Raw and Comparing
- Load Master File
- Scrub non-US
- Get % of IDs
- Do my own fuzzy match
- Recheck using Name
- Round 1
	- Filter for blank Street
		- 60% have empty Street name
	- Filter for different Street number (first string)
	- Pass those into round 2 -> with name
- Round 2, use 70% as a cutoff
- Still need some manual work
	- Consider using empty zip for 00001, they use that as a fill-in
- Totals with 2 passes and 70% cutoff:
	- 
# Round 3 On 12/13

### First Pass (No Name of Facility, Flattened)
- First pass (No Name and flattened file):
	- 57% (320/563) matching exactly
		- 53% (171/320) matched same ID
			- We can call this "verified correct"
		- 46% (149/320) matched Different ID
			- We can call this "verified incorrect"
			- Can go to Override
### Second Pass
- Second pass (Manual Check on non-exact match Until Definitely Wrong (above 80%ish)
	- 92 above threshold
		- 35% Same Match
			- "Verified Correct"
		- 65% Matched different ID
			- "Verified Incorrect"
			- Can go to Override
		- Issue Breakdown
			- 40% typo, ours or theirs
			- 20% same facility different building
			- 20% abbreviation error
			- 10% both entries valid
			- 10% wrong record
	- Key
		- DB = Different Building
		- MS = Missing Street (no N for North, etc)
		- TO = typo our error
		- TT = typo their error
		- AB = abbreviation difference
		- BT = Below threshold (very likely wrong)
		- BV = Both entries valid (need to recheck with Name)
		- VC = Verified Correct
		- VI = Verified Incorrect
### Third Pass
- Take all below threshold (80% and not manually checked) and include Name
- Results: Diminishing returns, do not recommend using
- Make available

### Deliverables

- Deliver 2 Files
	- ZC 
		- Full and Labeled 
		- Small with Truncated Duplicates on Name
	- Override List With Key
		- Full and Labeled
		- Small with Truncated Duplicates on Name

## Notes
- Theory for why matches are different after subsequent passes:
	- The way the fuzzy match does the calculation, adding in a new variable will change too many things to be able to call the second pass a true subset of the original
- Can be greatly avoided with more scrubbing, and only using Name in manual cleaning


---

# Round 2 On 11/15/2023

### Methodology:
- Approach 1
	- Take Name, Address, City, State, Zip and stringify separated by period (.)
	- Use difflib first and try finding close matches
- Approach 2
	- Create strings as before
	- Use fuzzywuzzy and get a ratioscore, check results
- Misc
	- Try approaches with removing certain fields, and run through them again.

### Notes
- Potentially add step to remove duplicates in the ZC match if the concatenated string is the same.
- Approach 1 was too slow!
- First pass: everything up to ~1300 (66% of total) looks good (ratio around 70%)
	- Raw file
		- Matched same value: ~800
		- Matched different value: ~ 1300
	- Above threshold (70%)
		- 718 Matched same value
		- 671 Matched different value
- Need a way to keep track of original matches, without using ID I have to create new ones

### New Methodology Notes
- First Pass
	- Try just Address, City, State, Zip
		- Only keep very high threshold, near 100
- Second Pass
	- Try adding name (Name, Address, City, State, Zip)
		- Remove anything that has differing State and Zip
		- Only keep above x threshold
		- Append to first pass
- Third Pass?
- Unify list, keep track of which pass and the percentage match

#### Issues/Questions
- Need to keep track somehow, so new unique ID for each prematched row (that isn't cust_id)
- Make sure the Zip's getting passed are 5 digit, even with leading 0 (lots of 4s!)
- Try with Address, City, State, Zip, and get match score
	- Then add name, and create match score for just name, and also for total
		- Good heuristic to try: if low name match but high address match vs high high, worth taking a look
	- Make a note for missing street address or limited name
		- Create filter from get go



---
# Previous Methodology, prior to 11/15/2023

### Zero Consumables Methodology
- Separated into digestible chunks
	- Names, Addresses, and City/State/Zip for all matches
- Thinks to look for
	- same CustID with different MID (confirmed empty)
		- Didn't find any
	- Difference of state for same CustID
		- Found 1, seems typo of WV and WY (the City is Casper, which is in WY)
	- Difference of City for same CustID
		- Found 40 of these, vast majority very similar or typo
		- Found 6 Entries that seem completely different

### Fuzzy Matching Precleaning Ideas
- Check for na/nan
- Ensure UPPER or LOWER for addresses
- Ensure matching Abbreviations: St, Rd, Ave, Pkwy, Ln
- Ensure Zip has leading zero (for example 01854 being read in as 1854)
- Reconcile whether to use 5 digit or 9 digit

### Questions
- Example of a situation where PH_Name_2 is relevant?
	- Edit after later, suggest using it as a tiebreaker, but not in original fuzzy match
- Did you do any cleaning prior to fuzzy match that you know of? It seems like there's options in the fuzzy match engine itself.
- Do you know what kind of fuzzy matching alteryx it's using? I can try alternate approaches after cleaning. The documentation says it uses [Levenstein and Jaro](https://help.alteryx.com/current/en/designer/tools/join/fuzzy-match-tool/fuzzy-match-edit-match-options.html#generate-keys-for-each-word)
- What is being done with zip codes, 5 digit vs 9 digit? If Medtronic uses 9 digit, is it useful to create a script that attempts to find these for every address first? Or just pair down medtronic to 5 digit.
- What to do when medtronic info seems inaccurate?
- 

### Problem Children
- ID 1161276
	- It's a VA Hospital, but seems to have been matched to a childrens hospital  in Philips Data.
- ID 1797995
	- Found 3 Entries that Philips had in Name 1 as Collins Moving and Storage, and Name 2 had the same name as Medtronic: Inova Health Systems
	- Example of where name 2 came in partially useful
- ID 1803570
	- Kansas hospital, but different cities 
		- Philips shows Shawnee KS, Medtronic shows Overland Park, KS
		- Philips name 2 shows Receiving Dock info
		- Google maps shows pictures of a cargo dock, and permanently closed
- ID 1834624
	- OH hospital, shows different cities
		- Philips has mostly correct data, in Liberty Township, OH
		- Medtronic has completely wrong city, West Chester OH which is 3 hours away
		- Both have same address
		- Philips has different zip codes for same place, probably error

