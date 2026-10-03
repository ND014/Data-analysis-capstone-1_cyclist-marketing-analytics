# 🚴 Cyclistic Bike-Share: Marketing Analytics Capstone

**Google Data Analytics Professional Certificate — Case Study 1**

## 📋 Business Task
Analyze how **casual riders** and **annual members** use Cyclistic bikes differently, and provide data-driven recommendations to convert casual riders into annual members.

## 📁 Data Source
- **Source:** [Divvy Bike Trip Data](https://divvy-tripdata.s3.amazonaws.com/index.html) (Motivate International Inc.)
- **Period:** January 2025 – December 2025
- **Size:** ~5.55 million rides across 12 monthly CSV files
- **License:** Public, made available under Divvy's data license agreement

> ⚠️ Raw CSV data files are excluded from this repo due to size (>1.4 GB). Download directly from the source above.

## 🛠️ Tools Used
- **Python** (pandas, matplotlib, seaborn)
- **Jupyter Notebook**

## 🔍 Key Findings

| Insight | Casual | Member |
|--------|--------|--------|
| Ride volume | Lower | Higher |
| Avg ride length | Longer (~17–23 min) | Shorter (~11–13 min) |
| Peak days | Weekends (Sat–Sun) | Weekdays (Mon–Fri) |
| Peak hours | 2pm – 5pm | 8am & 5pm (commute) |
| Peak season | Summer | Summer (less drop in Winter) |
| Bike preference | Classic (longer rides) | Both classic & electric |

## ✅ Top 3 Recommendations

1. **Weekend Membership Tier** — Casuals already ride on weekends. A weekend-only membership lowers the conversion barrier.
2. **Summer Conversion Campaign** — Launch a limited-time offer in May–June when casual ridership peaks.
3. **Promote Commuter Benefits** — Show casuals how membership pays off for daily commutes via cost-per-ride comparisons.

## 📊 Visualizations Included
- Ride share split (casual vs member)
- Rides by day of week
- Average ride length by day of week
- Rides by season
- Average ride length by season
- Monthly ride trend (Jan → Dec)
- Rides by hour of day
- Bike type analysis

## 📂 File Structure
```
├── code.ipynb          # Full analysis notebook
├── .gitignore
└── README.md
```
