# AI_for_Health
This repository contains the initial phase of a pilot study to detect breathing irregularities from overnight sleep data. The project focuses on high-frequency signal processing and automated clinical visualization.
1. Advanced Visualization
vis.py segments the data into 96 individual images to allow detailed inspection of 8-hour recordings.
Time-Alignment: Synchronizes 32 Hz respiratory data with 4 Hz SpO₂ data on a shared X-axis.
Event Overlay: Automatically highlights annotated irregularities using semi-transparent overlays across all three signal subplots.
2. Signal Preprocessing & Filtering
Human breathing typically occurs between 10–24 breaths per minute (0.17 Hz to 0.4 Hz). To ensure data quality for future modeling:
Digital Filtering: A Butterworth Bandpass Filter (0.1 Hz – 0.5 Hz) is applied to Nasal and Thoracic signals. This removes electronic noise and baseline drift.
Windowing: Signals are split into 30-second windows with a 50% overlap (15s step).
Labeling Logic: Windows are labeled as "Normal" or a specific irregularity based on a >50% overlap rule with the clinical event file.
Gemini (Google AI) provided technical support and code optimization for this project.
Note: The Machine Learning classification component (1D CNN) is currently under development.
