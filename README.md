# econ3916-lab04-anomaly-detection

# Robust Statistics -- Automated Anomaly Detection

## Objective

I set out to compare how different summary statistics and anomaly detection methods hold up when a dataset contains outliers, using the California Housing dataset (20,640 observations).

## Methodology

- I computed standard and outlier-resistant summary statistics on the data, including mean, median, trimmed mean, standard deviation, IQR, and MAD
- I implemented Tukey Fences by hand to flag price outliers based on the IQR
- I applied Isolation Forest to detect anomalies across multiple variables at once
- I compared the observations flagged by Tukey Fences against those flagged by Isolation Forest to see how much they overlapped
- I ran a contamination experiment, injecting 5% corrupted values into the data to see how each statistic responded

## Key Findings

- Tukey Fences and Isolation Forest did not flag the same observations -- each method picked up on a different kind of outlier
- After contaminating the data by 5%, the mean shifted by 67.13%, while the median shifted by only 3.56%
- This gap shows that some statistics are far more sensitive to corrupted data than others, even at a small contamination level
