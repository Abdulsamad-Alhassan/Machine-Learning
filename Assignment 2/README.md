# COVID-19 Data Preprocessing

This project focuses on on cleaning, normalizing, and reducing the dimensionality of a global COVID-19 dataset.

## Tasks Overview
### Task 1: 
#### Objective: Identify inconsistencies and noise in the raw dataset.

### Task 2:
#### Objective: Handle incomplete data without introducing bias.

Global health data is heavily skewed (outliers).
The median is more robust than the mean, ensuring that missing values are filled with a
"typical" global value rather than one inflated by extreme case counts in larger nations.


### Task 3:
#### Objective: Mitigate the impact of extreme values using IQR method.

Values exceeding the upper bound were set to the boundary value. This retains the data points 
(keeping major countries in the set) while preventing them from dominating the variance.

### Task 4:
#### Objective: Rescale numerical features to a common scale.

- Min-Max Scaling: Rescales data to a fixed range of $[0, 1]$.
- Z-Score Normalization (Standardization): Centers data around a mean of $0$ with a standard deviation of $1$.

### Task 5:
#### Objective: Reduce the dataset from 6 dimensions down to 2 for visualization and redundancy removal.

Manual calculation via the Covariance Matrix and Eigen-decomposition.
- PC1: Captures the primary direction of variance (e.g., overall scale of the pandemic).
- PC2: Captures the secondary pattern (e.g., testing intensity vs. population density).

Result: The two components capture approximately 68% of the total information from the original high-dimensional dataset.

## Setup and Requirements

- Python 3.x
- Libraries: pandas, numpy (for logic/math), matplotlib, seaborn (for visualization).
