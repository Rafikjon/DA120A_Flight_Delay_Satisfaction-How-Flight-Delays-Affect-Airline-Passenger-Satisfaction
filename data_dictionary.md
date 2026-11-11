# Data Dictionary – Airline Passenger Satisfaction

| # | Column | Type | Values / Range | Description |
|---|---|---|---|---|
| 1 | Unnamed: 0 | int | – | Row index from the original file (will be dropped) |
| 2 | id | int | – | Passenger ID |
| 3 | Gender | categorical | Female, Male | Passenger gender |
| 4 | Customer Type | categorical | Loyal Customer, disloyal Customer | Loyalty status |
| 5 | Age | int | 7–85 | Passenger age |
| 6 | Type of Travel | categorical | Business travel, Personal Travel | Purpose of the flight |
| 7 | Class | categorical | Business, Eco, Eco Plus | Travel class |
| 8 | Flight Distance | int | 31–4,983 | Flight distance (miles) |
| 9 | Inflight wifi service | ordinal | 0–5 | Satisfaction with in-flight Wi-Fi (0 = not applicable) |
| 10 | Departure/Arrival time convenient | ordinal | 0–5 | Satisfaction with departure/arrival time convenience |
| 11 | Ease of Online booking | ordinal | 0–5 | Satisfaction with online booking |
| 12 | Gate location | ordinal | 0–5 | Satisfaction with gate location |
| 13 | Food and drink | ordinal | 0–5 | Satisfaction with food and drink |
| 14 | Online boarding | ordinal | 0–5 | Satisfaction with online boarding |
| 15 | Seat comfort | ordinal | 0–5 | Satisfaction with seat comfort |
| 16 | Inflight entertainment | ordinal | 0–5 | Satisfaction with in-flight entertainment |
| 17 | On-board service | ordinal | 0–5 | Satisfaction with on-board service |
| 18 | Leg room service | ordinal | 0–5 | Satisfaction with leg room |
| 19 | Baggage handling | ordinal | 1–5 | Satisfaction with baggage handling |
| 20 | Checkin service | ordinal | 0–5 | Satisfaction with check-in |
| 21 | Inflight service | ordinal | 0–5 | Satisfaction with in-flight service |
| 22 | Cleanliness | ordinal | 0–5 | Satisfaction with cleanliness |
| 23 | Departure Delay in Minutes | int | 0–1,592 | Minutes the departure was delayed |
| 24 | Arrival Delay in Minutes | float | 0–1,584 (393 missing) | Minutes the arrival was delayed |
| 25 | satisfaction | categorical (target) | satisfied, neutral or dissatisfied | Overall satisfaction with the airline |

## Planned engineered features
| Feature | Definition |
|---|---|
| is_delayed | 1 if Arrival Delay > 15 min, else 0 |
| delay_category | On time (0), Short (1–15), Medium (16–60), Long (60+) |
| delay_recovered | Departure Delay − Arrival Delay (time made up in the air) |
| avg_service_score | Mean of the 14 service ratings (excluding 0 = not applicable) |
| satisfied_flag | 1 = satisfied, 0 = neutral or dissatisfied |
