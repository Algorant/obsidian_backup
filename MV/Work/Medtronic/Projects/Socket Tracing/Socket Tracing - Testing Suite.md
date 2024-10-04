

## Notes


- 



## QA Tests for Certifying Accounts for the Dashboard

#### Test 1: Last 12 Months Consumables For Match
- 30% threshold currently, else fail

#### Test 2: Check for similar customer Names in List (recursive)
- Explanation
- 
#### Test 3: Check if OEM Name matches Mid Name
- Can Cross check using IDN Name, and City/State Info
- Do a city check after same state
- 
#### Test 4: Install Base Check

#### Test 5: IDN Level Check
- Not useful if idn is blank, check for this
#### Test 9: Previous Certification (or IDN) ?
- Will have to check for previous certification by MID
- Its possible an account can get added again or have different profile when re-run, can be useful to dismiss bad test or to flag new accounts