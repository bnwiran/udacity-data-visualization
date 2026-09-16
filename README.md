# Ford GoBike System Data
## by Belal Nwiran

## Dataset

This project analyzes **Ford GoBike** (now Bay Wheels) trip-history data for the San Francisco Bay Area in **February 2019**. Each row represents one bike-share trip and records its start and end time, duration, station locations, bike ID, user type, and optional self-reported rider demographics.

The original file contains 183,412 trips and 16 variables. For analysis, the timestamps were converted to datetime values and the following features were derived: trip duration in minutes, rider age, trip start hour, day of week, and weekday/weekend. The cleaned dataset removes 192 records with implausible ages above 80 while retaining missing demographic values. Duration is strongly right-skewed, so analyses that compare its distribution use a logarithmic scale rather than discarding unusually long trips.

**Source:** [Ford GoBike System Data](https://video.udacity-data.com/topher/2020/October/5f91cf38_201902-fordgobike-tripdata/201902-fordgobike-tripdata.csv). The February 2019 Ford GoBike CSV file, and the cleaned version, were supplied with this project.

## Summary of Findings

The data supports a clear two-segment view of Ford GoBike use:

- Trip duration is highly right-skewed. Most rides are short, while a small number last many hours.
- **Subscribers** account for about **89%** of trips. They take shorter rides (median about **8.2 minutes**) and have pronounced weekday peaks around **8 AM** and **5-6 PM**.
- **Customers** account for about **11%** of trips. Their median trip is longer (about **13.2 minutes**) and their daily usage pattern is lower and comparatively flat.
- Overall ridership is highest Tuesday through Thursday and substantially lower on weekends. The weekday morning/evening pattern disappears on weekends.
- The busiest origin stations include locations at or near Caltrain, BART, and the Ferry Building. Together with the timing and membership patterns, this is consistent with a strong last-mile commuting role.
- Age and gender add little explanatory value to the key duration and timing patterns. The median member age is about 32; among reported gender values, most trips are made by male riders.

These findings are observational. Station names and trip timing support, but do not directly prove, a commuter or leisure trip purpose.

## Key Insights for the Explanatory Presentation

The final explanatory slide deck focuses on one cohesive question: **what separates commuter-oriented and casual Ford GoBike trips?** It communicates this story with four polished visualizations:

1. **Membership share:** a percentage bar chart establishes Subscribers as the system's dominant users.
2. **Hourly trip volume:** weekday and weekend lines, shown separately by user type, reveal that the commute peaks are specifically a Subscriber behavior. Volumes are normalized to average trips per day so the five weekdays and two weekend days are comparable.
3. **Trip duration by membership:** a log-scaled box plot shows the higher Customer median while retaining the full duration distribution without undue influence from extreme values.
4. **Busiest start stations:** a horizontal bar chart shows the concentration of leading trip origins around regional transit connections.

The presentation concludes that Ford GoBike primarily served regular, short, commute-like Subscriber trips, alongside a smaller segment of longer and more casually timed Customer trips.
