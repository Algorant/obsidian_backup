
#### September 14th 2024
- [x] refactor to be more readable and clean
- [x] MFL
	- [x] enrich mfl leagues with data that sleeper has so theres parity
	- [x] permanent leagues and franchises, update never
	- [x] players, update never
	- [x] league_record, update weekly
	- [x] league_rosters, update weekly
- [x] Sleeper 
#### September 15th 2024
- [x] push to duck_db
	- [x] update with new  tables (mfl, sleeper, and full)
	- [x] leagues
	- [x] player_exposure
	- [x] league_record
- [x] merge player usage data
- [x] merge player frequency data
	- [x] might needs some adjustments
- [x] merge league data 
	- [x] fix league_url in sleeper
	- [x] add site name mfl or sleeper to individual dbs
	- [x] create sleeper league_url using string and league_id
#### September 16th 2024
- [x] mid-refactor: push into 
- [x] add buy ins to duckdb and full_league_info
#### September 20th 2024
- [x] create basic streamlit dashboard 
	- [x] Stats at a glance
		- [x] Record for the week (full)
		- [x] Record for the week (normalized for median games)
		- [x] "In Week 1 you went (w-l), a win_pct of (pct)"
		- [x] "This week you went (w-l), a win_pct of (pct)"
		- [x] Apex Record (week)
		- [x] Apex Records (List)
		- [x] Big money leagues record (week)
		- [x] Big money leagues records (list)
	- [x] use duckdb instead of pandas to create
	- [x] Positional things to try
		- [x] 1 graph, 1 bar or circle per position, and the top 5 for each with their amount or %age
		- [x] Bin everything below threshold as "Other"
	- [x] load in stats
#### October 8th 2024
- [x] create records by week 
	- [x] in week table?
- [x] create update.py
	- [x] update (weekly)
	- [x] update full (all data) 
	- [x] update duck_db
	- [x] add 'Last updated' column with timestamp
	- [x] create function that gets that value