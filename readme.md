**Appendix**

**Engineered features designing logics**

Data type: sensitive attributes can be more often to have certain data types than non-sensitive attributes, such as date of birth (datetime), address (string). On the other hand, non-sensitive attributes such as lab tests, vitals, medication dosages are often in float format.

Categorical attributes:sensitive attributes are often categorical, such as sex, ethnicity.

Order:if the values of a column follows a certain order, it can be a sensitive attribute such as medical record numbers, encounter IDs. This depends on whether the data samples have been sorted or not.

Null count:columns with a lot of null values are more often to be non-sensitive attributes, especially for the lab tests and medication columns when not all patients have performed the test or been prescribed.

Min: The minimum value of a column. Too large a minimum value of a column may indicate this is a sensitive attribute, such as medical record number; whereas non-sensitive attributes (lab test result, medication dosage) minimum number can be small.

Max/Median/median absolute deviation/sum/mean: Same logic as the minimum number.

Mode:If there is no mode for the data, all data samples are unique and it is highly likely to be a sensitive attribute. Need to be combined with other features to decide, because for example, lab tests results in float numbers are very unlikely to have two of the same numbers among a certain number of data samples.

Variance/Standard deviation: Unique values have very large variance and lab tests, vitals values are relatively more concentrate

Skewness: For example, sensitive attributes like medical record numbers and encounter IDs are likely to have a symmetric distribution, with an equal number of values on either side of the mean, resulting in a skewness value of 0. On the other hand, non-sensitive attributes like lab test results and medication dosages are likely to have a skewed distribution, where the tail is longer on one side of the mean. This can be due to factors such as outliers or a natural skewness in the underlying biological processes.

Kurtosis: Non-sensitie attributes such as lab tests, vitals signs can follow a normal distribution (most data falls beside the mean and it becomes less as data being further away from the mean) has a kurtosis of 3, which is considered as the reference value for kurtosis. This means that the normal distribution has neither peakedness nor flatness compared to other distributions. On the other hand, sensitive attribute such as medical IDs has a uniform distribution, with a kurtosis of -1.2. This indicates that the uniform distribution has flatter peaks and thinner tails compared to the normal distribution.

Num zeros/Num negatives:medications, diagnosis, treatment often uses 0 to indicate not prescribed with a medication, not diagnosed of a disease or not receiving a treatment

Histogram (bin counts, bin edges): For sensitive attributes, we may expect to see a more uniform distribution of values across the bins or a few dominant values with a small number of other values scattered across the bins. For example, if we look at a histogram of birth year, we may expect to see a relatively uniform distribution with a slight peak for the most common birth year. On the other hand, non-sensitive attributes like lab results may have more skewed distributions with a few dominant values and a large number of values clustered around zero or a specific range.

Bin counts: For example, if a column has a small number of distinct values with a high frequency in each bin, it may indicate a sensitive attribute, such as a patient's unique medical record number or social security number. On the other hand, non-sensitive attributes such as lab test results or medication dosages may have a larger number of distinct values with more evenly distributed bin counts.

Bin edges: For example, if a column has a narrow range of values with a small number of distinct values, it may be a sensitive attribute. On the other hand, if the column has a wide range of values with many distinct values, it is less likely to be a sensitive attribute. Additionally, if the bin edges reveal patterns or clusters of values, it may indicate that the column contains sensitive information.

Quantiles (0.25, 0.75): first quartile (Q1) and third quartile (Q3) can provide insights into the distribution of the values in the column. For sensitive attributes, the values may be more concentrated around a certain range, resulting in a smaller interquartile range (IQR) and a higher median. In contrast, for non-sensitive attributes, the values may be more spread out, resulting in a larger IQR and a lower median.

Categories: if a column contains sensitive attributes such as ethnicity, race, or religion, then the values in the column will be unique and categorical. On the other hand, non-sensitive attributes such as lab tests, medication dosages, and vitals, will have a wide range of values and are not categorical.

Unique count: Sensitive attributes may have a smaller number of distinct entries than non-sensitive attributes, especially for categorical attributes like sex and ethnicity.

Unique ratio: if a column has a high proportion of distinct entries (i.e., a large number of unique values compared to the total number of entries in the column), it could suggest that the column contains sensitive information that is unique to each individual.

Categorical count: helps to identify the distribution of the data across different categories, and can provide insights into whether a particular attribute is sensitive or not.

Gini impurity: the probability of a data sample is labeled wrong if it is randomly labeled according to the distributions of labels in this column

Diversity index: If a column has high diversity, meaning that the values in that column are unique or distinct from one another, it may indicate that the column contains sensitive information, such as a medical record number or an encounter ID.

Precision (min, max, mean, var, std, sample size, margin of error, confidence level): Statistics with respect to the number of digits in a number for each sample, because sensitive attributes may have a uniform number of digits, e.g., medical record number.
