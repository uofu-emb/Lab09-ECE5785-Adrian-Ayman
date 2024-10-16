# Invariants

- Power always stays on
- Barrier will always be down when the train approaches
- Trains enter the protected block one at a time
- Approach signal will always preceed a depart signal
- Timer will only be triggered off of the first approach
- Time will not be interrupted by another approach if running

# Counter Example
- NB_Approach -> SB_Approach -> Elaspsed -> NB_Depart
  - SB Train is still present in block, arms were raised at the NB departure
 

| number | arms_down | alarm_on | northbound_present | southbound_present |  north_approach | south_approach | north_depart | south_depart | elapsed | safety_hazard |
|--------|-----------|----------|--------------------|--------------------| ----------------|----------------|--------------|--------------|---------|---------------|
| 0      | 0         | 0        | 0                  | 0                  |  6              | 5              | 16           | 16           | 17      | 0             |
| 1      | 0         | 0        | 0                  | 1                  |  3              | 19             | 16           | 0            | 21      | 1             |
| 2      | 0         | 0        | 1                  | 0                  |  19             | 3              | 0            | 16           | 21      | 1             |
| 3      | 0         | 0        | 1                  | 1                  |  19             | 19             | 1            | 2            | 21      | 1             |
| 4      | 0         | 1        | 0                  | 0                  |  6              | 5              | 16           | 16           | 0       | 0             |
| 5      | 0         | 1        | 0                  | 1                  |  7              | 19             | 16           | 4            | 13      | 1             |
| 6      | 0         | 1        | 1                  | 0                  |  19             | 7              | 4            | 16           | 14      | 1             |
| 7      | 0         | 1        | 1                  | 1                  |  19             | 19             | 5            | 6            | 15      | 1*            |
| 8      | 1         | 0        | 0                  | 0                  |  14             | 13             | 16           | 16           | ?       | 0             |
| 9      | 1         | 0        | 0                  | 1                  |  11             | 19             | 16           | 0            | ?       | 1             |
| 10     | 1         | 0        | 1                  | 0                  |  19             | 11             | 0            | 16           | ?       | 1             |
| 11     | 1         | 0        | 1                  | 1                  |  19             | 19             | 9            | 10           | ?       | 1             |
| 12     | 1         | 1        | 0                  | 0                  |  14             | 13             | 16           | 16           | ?       | 0             |
| 13     | 1         | 1        | 0                  | 1                  |  15             | 19             | 16           | 4            | ?       | 0             |
| 14     | 1         | 1        | 1                  | 0                  |  19             | 15             | 4            | 16           | 20*     | 0             |
| 15     | 1         | 1        | 1                  | 1                  |  19             | 19             | 13           | 14           | 20 *    | 0             |

| number | invariant                         |
| 16     | Train Departed Without Approach   |
| 17     | Timer Activated Withoout Approach |
| 18     | Arms Down With No Alarm           |
| 19     | One train at a time in block      |
| 20     | Timer will only be triggered off of the first approach |
| 21     | Arms and Alarm must be on



