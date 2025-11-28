# celestial-dynamics.api
Project Overview
SpaceRisk is a data analytics project that transforms NASA open-source APIs into meaningful insights about space hazards — including asteroids, solar flares, geomagnetic storms, and coronal mass ejections.
The goal is to understand how these hazards behave over time, how they differ by intensity, and how they impact sectors such as aviation, telecommunications, and satellite operations.
The project also proposes a business concept:
👉 a real-time risk app that converts NASA event data into actionable alerts, risk scoring, and insurance-relevant metrics.
🔭 Datasets Used
1. NASA DONKI (Space Weather)
Solar Flares (FLR)
Coronal Mass Ejections (CME)
Geomagnetic Storms (GST)
Kp Index (geomagnetic intensity)
Event metadata (time, location, speed, class, linked events)
2. NASA NEO (Asteroids)
Diameter (min & max)
Estimated hazard category
Close approach date
Miss distance (km)
Relative velocity (km/s)

🧩 Hypotheses
Space hazards follow recognizable time-based patterns.
Visualizing DONKI and NEO events reveals clustering around certain dates and periods.
Asteroid size, speed, and miss distance correlate with hazard level.
Larger, faster, and closer asteroids indicate higher risk.
Polar and high-altitude environments show increased storm exposure.
Kp index spikes disproportionately affect polar routes and satellite orbits.
Different NASA APIs together provide a more complete risk picture.
Combining CME speed, GST Kp index, and NEO threat level shows cross-hazard patterns.

🧼 Data Cleaning & Processing
The data required a multi-step cleaning process due to API inconsistencies:
✔ Cleaning Steps
Flattened deeply nested JSON using pandas.json_normalize()
Converted timestamps to datetime objects
Removed null entries for CME speed, Kp index, and diameters
Merged DONKI datasets using linked event IDs
Created new variables:
asteroid_avg_diameter
kp_intensity_category
cme_speed_category
✔ Unique Techniques
Harmonized multiple datasets with different time formats
Mapped event severity scales (CME class, Kp, NEO hazardous flag)
Built charts from API-generated datasets of varying lengths

📊 Data Visualizations
Your project includes several visualizations:
NEO (Asteroids)
Histogram of asteroid sizes
Scatter: relative velocity vs miss distance
Frequency of hazardous vs non-hazardous NEOs
DONKI (Solar Weather)
Line chart of geomagnetic storm Kp index over time
CME speed distribution
Heatmap of Kp intensity
Cross-Event Comparisons
CME speed vs resulting geomagnetic storm strength
Event timelines combining FLR, CME, and GST
📱 Proposed Application: Celestial dynamics App
A real-time hazard intelligence platform enabling:
For Aviation
✈ Alerts for polar route disruptions
✈ High-frequency radio blackout warnings
✈ Pre-flight risk score based on solar & geomagnetic activity
For Telecom Providers
📡 Satellite interference predictions
📡 GPS accuracy degradation alerts
For Insurance
💰 Risk-adjusted pricing during solar maximum
💰 Claims forecasting based on historic Kp spikes
Core Features
Live NASA event monitoring
Risk scoring model (0–10 scale)
Customized alerts by location, altitude, and industry
Downloadable reports for operations teams
