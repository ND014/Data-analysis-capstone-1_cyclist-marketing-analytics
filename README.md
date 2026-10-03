# 🚴 Cyclistic Bike-Share: Marketing Analytics Capstone
### Google Data Analytics Professional Certificate — Case Study 1

---

## 📌 Overview

Cyclistic is a Chicago-based bike-share company with over **5.5 million rides** recorded in 2025. The company offers two types of riders:
- **Casual riders** — pay per ride or per day
- **Annual members** — pay a yearly subscription

Cyclistic's marketing director believes converting casual riders into annual members is key to long-term growth. This project analyzes **how casual riders and annual members use Cyclistic bikes differently**, and delivers data-driven recommendations to support that conversion strategy.

---

## 🎯 Business Task

> *"How do annual members and casual riders use Cyclistic bikes differently?"*

Answer this question using 12 months of trip data, then provide **three actionable marketing recommendations** to convert casual riders into annual members.

---

## 📁 Data Source

| Detail | Info |
|--------|------|
| **Provider** | Motivate International Inc. (Divvy Bikes) |
| **Coverage** | January 2025 – December 2025 |
| **Files** | 12 monthly CSV files |
| **Total Rows** | ~5,552,994 rides |
| **Columns** | 13 (ride ID, bike type, timestamps, stations, coordinates, user type) |
| **License** | [Divvy Data License Agreement](https://divvybikes.com/data-license-agreement) |

> ⚠️ Raw CSV files are excluded from this repository due to size (>1.4 GB). Download directly from [Divvy Trip Data](https://divvy-tripdata.s3.amazonaws.com/index.html).

---

## 🛠️ Tools & Libraries

- **Python 3.11** — core analysis
- **pandas** — data manipulation and aggregation
- **matplotlib + seaborn** — visualizations
- **Jupyter Notebook** — interactive analysis environment

---

## 🔧 Data Processing

### 1. Merging
All 12 monthly CSVs were loaded and concatenated into a single DataFrame of **5,552,994 rows**.

### 2. Column Renaming
For clarity:
- `rideable_type` → `bike_type`
- `member_casual` → `user_type`

### 3. Derived Columns
The following columns were engineered from raw timestamps:

| Column | Description |
|--------|-------------|
| `ride_length_m` | Duration in minutes (`ended_at - started_at`) |
| `day_of_week` | 0 = Monday … 6 = Sunday |
| `day_name` | Full day name (Monday, Tuesday…) |
| `hour` | Hour the ride started (0–23) |
| `month_num` | Month number (1–12) |
| `month` | Month name (January…December) |
| `season` | Winter / Spring / Summer / Fall |

### 4. Data Cleaning
- Removed rides with **negative or zero duration** (data entry errors / docked bikes)
- Removed rides **longer than 24 hours** (outliers / abandoned bikes)
- Rows removed: **~147,000** (2.6% of total)
- **Final clean dataset: ~5,405,000 rows**

---

## 📊 Analysis & Findings

### Ride Volume
Members take significantly **more total rides** than casual riders. However, casuals ride for **much longer durations** on average.

| Metric | Casual | Member |
|--------|--------|--------|
| Total rides | ~1.7M | ~3.7M |
| Avg ride length | ~17–23 min | ~11–13 min |
| Median ride length | ~12 min | ~9 min |

---

### Day of Week Behavior

| Day | Casual Pattern | Member Pattern |
|-----|---------------|----------------|
| Mon–Fri | Lower activity | **High — commuter peak** |
| Sat–Sun | **High — leisure peak** | Moderate drop |

- **Members** consistently peak on weekdays → **commuter use case**
- **Casuals** consistently peak on weekends → **recreational use case**
- Casuals ride longer than members on **every single day of the week**

---

### Time of Day

- **Members** show sharp spikes at **8am and 5pm** — classic morning and evening commute windows
- **Casuals** have no such spikes. Rides build gradually through the day, peaking around **2pm–5pm** — consistent with leisure and tourism behaviour
- This is one of the strongest signals differentiating the two groups

---

### Seasonal Trends

| Season | Casual Rides | Member Rides |
|--------|-------------|--------------|
| Winter | Very low (steep drop) | Low but more resilient |
| Spring | Rapidly increasing | Steadily increasing |
| Summer | **Peak** | **Peak** |
| Fall | Tapering off | Tapering off |

- **Summer (Jun–Aug)** is peak season for both groups
- **Casuals drop off far more sharply in Winter** — they are predominantly fair-weather riders
- Even in Winter, casuals still average longer ride durations than members — those who do ride are still using it recreationally

---

### Monthly Trend (Jan → Dec)

The monthly line chart shows:
- Both groups track a similar seasonal arc
- Casual ridership grows **much faster in Spring** and collapses more in Winter
- Member ridership is more **stable year-round**, reflecting habitual commuter behaviour

---

### Bike Type Preferences

| Metric | Classic Bike | Electric Bike |
|--------|-------------|---------------|
| Casual avg ride | Longer | Shorter |
| Member avg ride | Moderate | Shorter |

- **Casuals spend more time on classic bikes** — consistent with slower, sightseeing-style rides
- **Electric bikes are used for shorter trips** across both groups — members use them for quick commutes

---

## 📈 Visualizations

| # | Chart | Key Takeaway |
|---|-------|-------------|
| 1 | Ride Share Split (Pie) | Members dominate in volume |
| 2 | Rides by Day of Week | Members = weekdays, Casuals = weekends |
| 3 | Avg Ride Length by Day | Casuals always ride longer |
| 4 | Rides by Season | Summer peaks, casuals vanish in Winter |
| 5 | Avg Ride Length by Season | Duration gap is consistent year-round |
| 6 | Monthly Trend | Member usage more stable; casual usage more volatile |
| 7 | Rides by Hour | Members = commute spikes; Casuals = afternoon leisure |
| 8 | Bike Type Analysis | Classic bikes favoured for longer casual rides |

---

## ✅ Top 3 Recommendations

### 1. 🗓️ Launch a Weekend Membership Tier
Casual riders already concentrate their rides on **Saturday and Sunday** with longer durations. A discounted weekend-only annual membership directly mirrors their existing behaviour and dramatically lowers the barrier to conversion.

> **Target:** Casual riders active on Sat–Sun  
> **Message:** *"You already ride on weekends — make it cheaper with a weekend membership."*

---

### 2. ☀️ Summer Conversion Campaign
Casual ridership peaks in **June, July, and August**. This is the highest-intent period — casuals are already engaged and riding frequently. A **limited-time Summer membership offer launched in May** captures riders at the moment they're most motivated.

> **Target:** Casual riders in Spring / early Summer  
> **Message:** *"Ride all Summer for less — join before June and save."*

---

### 3. 🚇 Promote Commuter Benefits to Casual Riders
Casuals currently show zero commuter behaviour (no 8am/5pm spike). There's an untapped opportunity to shift them from weekend-only leisure use to weekday commuting. Targeted in-app messaging and station-level marketing near business districts can highlight the **cost savings and health benefits** of riding to work.

> **Target:** Casual riders near high-traffic commuter stations  
> **Message:** *"Save money. Skip traffic. Ride to work with a Cyclistic membership."*

---

## 📂 Repository Structure

```
├── code.ipynb          # Complete analysis notebook (data loading → recommendations)
├── README.md           # This report
└── .gitignore          # Excludes large CSV data files
```

---

## 👤 Author

**Nithish** — Google Data Analytics Professional Certificate Capstone  
[GitHub](https://github.com/ND014)
