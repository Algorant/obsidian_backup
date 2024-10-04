
### 01/16 Meeting Notes
- Questions
	- How far into alteryx process?
		- James got stuck on a variable being 
	- Is the consumables data prepped enough to give to Tzahi at 80% filled?
	- What is the data source for the creation of the master list? Is it ranked by sales amounts? Can just get the highest priority ones missing from Tzahi
	- What is next step for going through the manual verifications
- Next for me
	- Create Instructions for how to run the Alteryx pipelines
	- Get a baseline for new monthly additions and create pipeline for just that monthly update
	- Create scaffolding for next vendors
		- Nihon Koden?
- What are the locations for the next 

#### Next Steps
- New Baseline Flow -> 
	- First Pass
		- Clean up file -> Remove Quantity Columns -> Match by Recent Customer List -> Get Result above baseline
	- Second Pass 
		- Manual Assessment
		- Match to Sales Data and Upload
- Every Month flow
	- One Pass, Clean up File -> Compare to Already Matched list -> If new, append to Master list
	- Match to Sales Data and Upload
- Test Oct 2023 and Nov 2023 against matched file to get an idea of new work per month


#### Final join
- join new cid to philips match file
- filter and rename
- join mitg cols on philips
- filter and rename

### Troubleshooting
- Run Alteryx As Admin First time (Use Medtronic Admin Function)
	- This is to install packages, only needed first time, not any other time
- A lot of the time, you need to re-run the Alteryx thing for it to work


#### Basic Outline

- Step One
	- MITG Master (can be csv or SQL Query) -> Notebook Process -> Output
- Step Two
	- Philips Master (Can Get Files from Folder and combined or CSV) -> Notebook Process -> Output
- Step Three
	- MITG Master + Philips Master -> Fuzzy Match Logic -> Output
	- Has Designated Cutoff, can be customized

#### Jupyter Notebook
- Runs Code sequentially in order
- If it errors out anywhere, it will tell you where
- I have outlined every step along the way in plain english
- To re-run a cell, either click at the top run cell, or press shift+enter
- 