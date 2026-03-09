# Proactive Spatiotemporal Analytics for Dynamic Patrol Allocation
#### Moving Policing from Reactive to Proactive through Deep Learning and Optimization

### Aim of Investigation
This project builds an end-to-end spatiotemporal analytics framework designed to transition urban policing from a reactive (responding to calls) to a proactive (preventing incidents) model.
By combining Big Data analytics, deep learning (LSTM), and Linear Integer Programming, the framework measures how crime hotspots "drift" across a city over time. The ultimate goal is to dynamically allocate limited patrol resources to maximize safety coverage without requiring additional staff or budget.

### Research Questions
1. Diagnostic (The "Why" & "Where")
How do temporal factors (time of day, day of week, seasonal effects) and premise types (commercial vs. residential) statistically affect the density of violent versus property crimes?

2. Predictive (The "When")
Can deep learning models, specifically Long Short-Term Memory (LSTM) networks, accurately forecast crime volumes at a fine-grained, city-block level with a 14-day lead time?

3. Prescriptive (The "How")
How can Linear Integer Programming be used to optimally distribute a limited number of patrol units across space to maximize coverage of predicted high-risk zones?

4. Operational (The "Impact")
Does a dynamic allocation strategy (adjusting patrol centers by time of day) theoretically outperform current static district/beat assignments in terms of incident coverage efficiency?

### Hypothesis
Crime follows a self-exciting point process, where past incidents and specific environmental conditions strongly predict future clusters. I hypothesize that:

LSTM-based models will outperform static averages by capturing non-linear "drifts" (e.g., crime shifting from business districts during the day to nightlife areas after dark).

A dynamic resource allocation algorithm can improve coverage of high-priority incidents by at least 15% compared to existing static deployment models.

### Project Roadmap
#### Phase 1: Descriptive & Diagnostic Analysis
Data Cleaning: Handling null values, cleaning coordinates, and categorizing ~140 crime descriptions into "Violent" vs. "Property."

Spatial Clustering: Using K-Means to identify primary hotspots for initial EDA.

Statistical Profiling: Creating density matrices to correlate Premise Type and Time of Day with crime volume.

#### Phase 2: Predictive Modeling (Deep Learning)
Feature Engineering: Building a "12-hour Lookback" sliding window to create temporal sequences.

Model Showdown: Comparing XGBoost (Static/Non-linear) against LSTM and GRU (Temporal/Sequential) to prove the superiority of deep learning in detecting "drift."

#### Phase 3: Prescriptive Optimization
Resource Mapping: Integrating model predictions into a Linear Integer Programming framework.

Optimization: Calculating the optimal GPS coordinates for patrol units for every 4-hour shift.

#### Phase 4: Operational Evaluation
Backtesting: Running the dynamic model against historical static data to measure the "15% improvement" hypothesis.

### Tech Stack
Language: Python

Data Science: Pandas, NumPy, Scikit-Learn

Deep Learning: TensorFlow / Keras

Optimization: PuLP / SciPy (Linear Integer Programming)

Visualization: Matplotlib, Seaborn, Folium (Geospatial Heatmaps)