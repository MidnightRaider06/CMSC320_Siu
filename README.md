# CMSC_320_Siu

Group members: Abhinav Kota, Surya Prabhu, Aidan Suk, Aarav Verma

Dataset source: https://github.com/hudl/open-data

---

# Schedule

| Deliverable | Date | Points |
|---|---|---|
| Checkpoint 1 | Sep 29, 2026 | 5 |
| Checkpoint 2 | Oct 29, 2026 | 25 |
| Final | Dec 10, 2026 | 70 |

# Checkpoint 1 Summary

- Chose Hudl StatsBomb soccer dataset
- Since then, narrowed the dataset down to the 2022 World Cup due to the vast amount of information available

# Checkpoint 2 Summary

- There are 64 total matches in the 2022 WC. The data in each match is as follows:
  - Match ID
  - Date
  - Kickoff Time
  - Match Week
  - Home Team and Away Team with:
    - ID
    - Name
    - Group
    - Country
    - Managers with DOB, Name, Nationality
  - Final Home and Away Score
  - Competition State
  - Stadium
  - Referee

- The 'match' data does not contain events, lineups, or 360 data.
- The 'events' folder for a match provides approximately 3000 on-ball events PER match
- The 'lineups' folder for a match provides the players per team and their position [important for RQ]
- The 'three-sixty' folder for a match provides freeze-frame tracking for matches
---

- Based on all this information, we need more information than just the matches file (events, lineups, three-sixty) because the dataset with just matches is too small to do proper analysis

---

Research Question: Within the 2022 World Cup, how do shooter positions, body parts, shot types, and levels of defender pressure are associated with a shot resulting in a goal vs no-goal?

---

Dataset 'Setup':
| Columns | Source (File) | What it means |
|---|---|---|
| event_id | events | ID field for event |
| match_id | matches | ID field for match |
| player | events | Player associated with shot |
| team | events | Team of said player |
| opponent | matches and events | Opponent of said player |
| outcome | events | Detailed label of what happened |
| period | events | Segment of the match |
| shot_type | events | The type of shot that was made |
| body_part | events | What body part the shot was made with |
| position | events | Specific position on the field |
position_group | 'derived' | Midfielder, Forward, etc |
| under_pressure | events | Whether the player was under pressure |
| x, y | events | Position of the player |
| distance, angle | derived | Distance from goal and which angle they shot from |
| freeze-frame data | events | Where players are on the field at that specific time |
| stage | matches | Stage of the World Cup |
| match_week | matches | The week of the match |
| minute | events | Minute of the shot |
| statsbomb_xg | events | Expected Goals from StatsBomb's own model |