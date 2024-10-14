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
 

| number | arms_down | alarm_on | northbound_present | southbound_present | north_approach | south_approach | north_depart | south_depart | ringing | safety_hazard |
|--------|-----------|----------|--------------------|--------------------|----------------|----------------|--------------|--------------|---------|---------------|
| 0      | 0         | 0        | 0                  | 0                  | 0              | 0              | 0            | 0            | 0       | 0             |
| 1      | 0         | 0        | 0                  | 1                  | 0              | 1              | 0            | 0            | 0       | 1             |
| 2      | 0         | 0        | 1                  | 0                  | 1              | 0              | 0            | 0            | 0       | 1             |
| 3      | 0         | 0        | 1                  | 1                  | 1              | 1              | 0            | 0            | 0       | 1             |
| 4      | 0         | 1        | 0                  | 0                  | (1,0,1)        | (0,1,1)        | (1,0,1)      | (0,1,1)      | 1       | 0             |
| 5      | 0         | 1        | 0                  | 1                  |                |                |              |              |         | 1             |
| 6      | 0         | 1        | 1                  | 0                  |                |                |              |              |         | 1             |
| 7      | 0         | 1        | 1                  | 1                  |                |                |              |              |         | 1             |
| 8      | 1         | 0        | 0                  | 0                  |                |                |              |              | 0       | 0             |
| 9      | 1         | 0        | 0                  | 1                  |                |                |              |              |         | 1             |
| 10     | 1         | 0        | 1                  | 0                  |                |                |              |              |         | 1             |
| 11     | 1         | 0        | 1                  | 1                  |                |                |              |              |         | 1             |
| 12     | 1         | 1        | 0                  | 0                  |                |                |              |              |         | 0             |
| 13     | 1         | 1        | 0                  | 1                  |                |                |              |              |         | 1             |
| 14     | 1         | 1        | 1                  | 0                  |                |                |              |              |         | 1             |
| 15     | 1         | 1        | 1                  | 1                  |                |                |              |              |         | 1             |
