
## Todos
- Playoff picture
	- Clinched? 
	- In contention?
	- Round 1 Bye? 
---
#### Next Steps
- Create analysis
	- different positions?
- hosting? 

## Things you need
- Name of league
- Median Game Yes or No
- Output for each individual week
- Current Record as win - loss
- Current Standings
- Style/Format (Inferred from Rosters?)

## Calculated
- In Season
	- Win %
	- Win/Loss Grid
	- Win % / Week
- Pre-season
	- Total Amount of Leagues
	- Total Buy in
	- Total Roster Setup (xQB/yRB/zWR etc)


## Manual Entry
- Entry Fee
- Placement Winnings 1st 2nd 3rd 
- Misc Notes
- 

## Bonus?
- Rosters
- Calculate exposure to players?
- Key for formats
	- Number of starters
	- If 2 QB or if WRTQ, then superflex
	- IF any K or D, note
- 

## Sleeper API
- [Docs](https://docs.sleeper.com/)
### Useful Queries

#### Get my user info

##### Query
```bash
curl "https://api.sleeper.app/v1/user/Incertophile" | jq 
```

##### Description
- This gives me user id, which is currently: "783744588341989376"

#### Get Leagues and current info for user

##### Query
```bash
curl "https://api.sleeper.app/v1/user/783744588341989376/leagues/nfl/2024" | jq
```

##### Relevant Fields
- name: name of the league
- status: whether its in_season, or pre-draft, etc
- league_id: id of the league I have access to
- roster: Array of the league positions
- total_rosters: number of teams 12 or 14 etc
- Also has scoring requirements for PPR, TEP, Pass_TD 6 or 4, etc

#### Get Specific League Info

##### Query
```bash
curl "https://api.sleeper.app/v1/league/1048285971550277632" | jq
```

##### Relevant Fields
- Similar to above with leagues and current info
- league_average_match = whether theres a median game, if 1 then YES

#### Get Rosters




---

## MFL API
### Useful Fields
- name: name of the league
- url: url of the league
- league_id: id of the specific league
- franchise_id: id of the team
- franchise_name: the name of the team
- name: the league name

#### Getting my Cookie for auth
- Use this `curl -s -X POST "https://api.myfantasyleague.com/2024/login?USERNAME=Skantastico&PASSWORD=my_pw&XML=1" -i` with your mfl credentials
- After you will get a response that says `MFL_USER_ID="long_string"` and use that
- latest: bRNv28ySvqL0i1v/aRqFOGFc

#### Get leagues 
- `curl -H "Cookie: MFL_USER_ID=bRNv28ySvqL0i1v/aRqFOGFc" "https://api.myfantasyleague.com/2024/export?TYPE=myleagues&YEAR=2024&FRANCHISE_NAMES=&JSON=1" | jq`
- Gives league id and franchise ID for each league

#### Get Roster for specific league (need league id and franchise id from above)
- 