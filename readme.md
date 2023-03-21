**Appendix**

**Supplementary Table 1**. Sensitive Information Categories and Relevant Regular Expressions_

| **Sensitive Information** | **Subcategory** | **Regular expression patterns** | **Explanations** |
| --- | --- | --- | --- |
| **(A) Names** | Firstname, lastame | ^[A-Z]\'?[-a-zA-Z]+$ | match names, A'Bsfs, Absssfs, A-Bsfsfs |
| Title |
(Dr\.|Mr\.|Mrs\.|Ms\.|Miss|Sir|Madam)\s(([A-Z]\'?[A-Z]?[\-a-z]+(\s[A-Z]\'?[A-Z]?[\-a-z]+)\*)) | match salutation |
| Middle name | \*\*PHI\*\*,? (([A-CE-LN-Z][Rr]?|[DM])\.?) | (([A-CE-LN-Z][Rr]?|[DM])\.?),? \*\*PHI\*\* | match middle initial |
| **(B) Geographic subdivisions** | Postal code | \b(\d{5}(-\d{4})?)\b | match postal code |
| Address | address\_indictor = ['street', 'avenue', 'road', 'boulevard', 'drive', 'trail', 'way', 'lane', 'ave', 'blvd', 'st', 'rd', 'trl', 'wy', 'ln','court', 'ct', 'place', 'plc', 'terrace', 'ter','highway', 'freeway', 'autoroute', 'autobahn', 'expressway', 'autostrasse', 'autostrada', 'byway', 'auto-estrada', 'motorway', 'avenue', 'boulevard', 'road', 'street', 'alley', 'bay', 'drive', 'gardens', 'gate', 'grove', 'heights', 'highlands', 'lane', 'mews', 'pathway', 'terrace', 'trail', 'vale', 'view', 'walk', 'way', 'close', 'court', 'place', 'cove', 'circle', 'crescent', 'square', 'loop', 'hill', 'causeway', 'canyon', 'parkway', 'esplanade', 'approach', 'parade', 'park','plaza', 'promenade', 'quay', 'bypass''dr.', 'ave.', 'rd.', 'st.', 'blvd.','pkwy.','city'] | address keywords |
| **(C) Dates** | General date | \b(.\*?(?=\b(\d{1,2}[-./\s]\d{1,2}[-./\s]\d{2}|\d{1,2}[-./\s]\d{1,2}[-./\s]\d{4}|\d{2}[-./\s]\d{1,2}[-./\s]\d{1,2}|\d{4}[-./\s]\d{1,2}[-./\s]\d{1,2})\b))\b
month\_name = Jan(uary)?|Feb(ruary)?|Mar(ch)?|Apr(il)?|May|Jun(e)?|Jul(y)?|Aug(ust)?|Sep(tember)?|Oct(ober)?|Nov(ember)?|Dec(ember)?
\b(\d{4}[\-/](0?[1-9]|1[0-2]|"""+month\_name+r""")\-\d{4}[\-/](0?[1-9]|1[0-2]|"""+month\_name+r""") # YYYY/MM-YYYY/MM|(0?[1-9]|1[0-2]|"""+month\_name+r""")[\-/]\d{4}\-(0?[1-9]|1[0-2]|"""+month\_name+r""")[\-/]\d{4} # MM/YYYY-MM/YYYY|(0?[1-9]|1[0-2]|"""+month\_name+r""")/\d{2}\-(0?[1-9]|1[0-2]|"""+month\_name+r""")/\d{2} # MM/YY-MM/YY|(0?[1-9]|1[0-2]|"""+month\_name+r""")/\d{2}\-(0?[1-9]|1[0-2]|"""+month\_name+r""")/\d{4} # MM/YYYY-MM/YYYY|(0?[1-9]|1[0-2]|"""+month\_name+r""")/([1-2][0-9]|3[0-1]|0?[1-9])\-(0?[1-9]|1[0-2]|"""+month\_name+r""")/([1-2][0-9]|3[0-1]|0?[1-9]) #MM/DD-MM/DD|([1-2][0-9]|3[0-1]|0?[1-9])/(0?[1-9]|1[0-2]|"""+month\_name+r""")\-([1-2][0-9]|3[0-1]|0?[1-9])/(0?[1-9]|1[0-2]|"""+month\_name+r""") #DD/MM-DD/MM|(0?[1-9]|1[0-2]|"""+month\_name+r""")[\-/\s]([1-2][0-9]|3[0-1]|0?[1-9])[\-/\s]\d{2} # MM/DD/YY|(0?[1-9]|1[0-2]|"""+month\_name+r""")[\-/\s]([1-2][0-9]|3[0-1]|0?[1-9])[\-/\s]\d{4} # MM/DD/YYYY|([1-2][0-9]|3[0-1]|0?[1-9])[\-/\s](0?[1-9]|1[0-2]|"""+month\_name+r""")[\-/\s]\d{2} # DD/MM/YY|([1-2][0-9]|3[0-1]|0?[1-9])[\-/\s](0?[1-9]|1[0-2]|"""+month\_name+r""")[\-/\s]\d{4} # DD/MM/YYYY|\d{2}[\-./\s](0?[1-9]|1[0-2]|"""+month\_name+r""")[\-\./\s]([1-2][0-9]|3[0-1]|0?[1-9]) # YY/MM/DD|\d{4}[\-./\s](0?[1-9]|1[0-2]|"""+month\_name+r""")[\-\./\s]([1-2][0-9]|3[0-1]|0?[1-9]) # YYYY/MM/DD|\d{4}[\-/](0?[1-9]|1[0-2]|"""+month\_name+r""") # YYYY/MM|(0?[1-9]|1[0-2]|"""+month\_name+r""")[\-/]\d{4} # MM/YYYY|(0?[1-9]|1[0-2]|"""+month\_name+r""")/\d{2} # MM/YY|(0?[1-9]|1[0-2]|"""+month\_name+r""")/\d{2} # MM/YYYY|(0?[1-9]|1[0-2]|"""+month\_name+r""")/([1-2][0-9]|3[0-1]|0?[1-9]) #MM/DD|([1-2][0-9]|3[0-1]|0?[1-9])/(0?[1-9]|1[0-2]|"""+month\_name+r""") #DD/MM)\b | Date in various formats. YYYY/MM-YYYY/MMMM/YYYY-MM/YYYYMM/YY-MM/YYMM/YY-MM/YYMM/YYYY-MM/YYYYMM/DD-MM/DDDD/MM-DD/MMDD/MM-DD/MMMM/DD/YYMM/DD/YYYYDD/MM/YYDD/MM/YYYYYY/MM/DDYYYY/MM/DDMM/YYYYMM/YYMM/YYYYMM/DDDD/MM |
| DOB | \b(.\*?(?=\b(\d{1,2}[-./\s]\d{1,2}[-./\s]\d{2} # X/X/XX|\d{1,2}[-./\s]\d{1,2}[-./\s]\d{4} # XX/XX/XXXX|\d{2}[-./\s]\d{1,2}[-./\s]\d{1,2} # xx/xx/xx|\d{4}[-./\s]\d{1,2}[-./\s]\d{1,2} # xxxx/xx/xx)\b))\b | Match date of birth |
| Age | \b(age|year[s-]?\s?old|y.o[.]?)\b | Match age |
| **(D)Telephone/FAX numbers, (I) Health plan beneficiary numbers, Account numbers, Medical record numbers** |
 | \b((\d[\(\)\-\']?\s?){6}([\(\)\-\']?\d)+ |(\d[\(\)\-.\']?){7}([\(\)\-.\']?\d)+ # test)\b\b(\d{5}[A-Z0-9]\*)\b\b([A-Z0-9\-/]{6}[A-Z0-9\-/]\*)\b | Phone/fax/account number/MRN, etc. in the format of SSN/PHONE/FAX XXX-XX-XXXX, XXX-XXX-XXXX, XXX-XXXXXXXX, etc.
 |
| **(F) Email addresses** |
 | \b([a-zA-Z0-9\_.+-@\"]+@[a-zA-Z0-9-\:\]\[]+[a-zA-Z0-9-.]\*)\b | e.g., xxx.xxx@xxxx.xxx |
| **(G) Social security numbers** |
 | \b((\d[\(\)\-\']?\s?){6}([\(\)\-\']?\d)+|(\d[\(\)\-.\']?){7}([\(\)\-.\']?\d)+)\b | e.g., xxx-xx-xxxx, etc. |
| **(N) Web URLs** |
 | \b((http[s]?://)?([a-zA-Z0-9$-\_@.&+:!\*\(\),])\*[\.\/]([a-zA-Z0-9$-\_@.&+:\!\*\(\),])\*)\b | e.g., http://xxx.xxx.xxx/xxx.xxx |
| **(O) Internet Protocol (IP) addresses** |
| ^(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$ | e.g., xxx.xxx.xxx.xxx |
| **(R) Other unique identifiers** | Race | "(White/Caucasian|White|Caucasian|American|Indian|Alaska|Native|Asian|Black|African|Native|Hawaiian|Pacific|Islander)" | Match race |
| Gender | "(Male|Female)" | Match gender |
| Ethnicity | "(Hispanic|Latino)" | Match ethnicity |

**Supplementary Table 2**. Summary of the engineered features_

| **Engineered features** | **Description** |
| --- | --- |
| Data\_type | The data type of this column: int, float, string, datetime |
| categorical | Whether the data is categorical data type |
| order | whether the data in this column is ordered |
| null\_count | the number of null entries in this column |
| min | minimum value in the sample |
| max | maximum value in the sample |
| mode | mode of the entries in the sample |
| median | median of the entries in the sample |
| median\_absolute\_deviation | the median absolute deviation of the entries in the sample |
| sum | the total of all sampled values from the column |
| mean | the average of all entries in the sample |
| variance | the variance of all entries in the sample |
| stddev | the standard deviation of all entries in the sample |
| skewness | the statistical skewness of all entries in the sample |
| kurtosis | the statistical kurtosis of all entries in the sample |
| num\_zeros | the number of entries in this sample that have the value 0 |
| num\_negatives | the number of entries in this sample that have a value less than 0 |
| histogram | contains histogram relevant information |
| bin\_counts | the number of entries within each bin |
| bin\_edges | the thresholds of each bin |
| quantiles | the value at each percentile in the order they are listed based on the entries in the sample |
| categories | a list of each distinct category within the sample if categorical = 'true' |
| unique\_count | the number of distinct entries in the sample |
| unique\_ratio | the proportion of the number of distinct entries in the sample to the total number of entries in the sample |
| categorical\_count | number of entries sampled for each category if categorical = 'true' |
| gini\_impurity | measure of how often a randomly chosen element from the set would be incorrectly labeled if it was randomly labeled according to the distribution of labels in the subset. Gini\_impurity = where is the number of categories in the column, and is the proportion of the samples that belong to category . |
| diversity index | A value denoting how frequently entries differ from one another within the sample |
| precision | A dict of statistics with respect to the number of digits in a number for each sample |

**Engineered features designing logics**

Data type:_sensitive attributes can be more often to have certain data types than non-sensitive attributes, such as date of birth (datetime), address (string). On the other hand, non-sensitive attributes such as lab tests, vitals, medication dosages are often in float format.

Categorical attributes:_sensitive attributes are often categorical, such as sex, ethnicity.

Order_:if the values of a column follows a certain order, it can be a sensitive attribute such as medical record numbers, encounter IDs. This depends on whether the data samples have been sorted or not.

Null count_:columns with a lot of null values are more often to be non-sensitive attributes, especially for the lab tests and medication columns when not all patients have performed the test or been prescribed.

Min_: The minimum value of a column. Too large a minimum value of a column may indicate this is a sensitive attribute, such as medical record number; whereas non-sensitive attributes (lab test result, medication dosage) minimum number can be small.

Max/Median/median absolute deviation/sum/mean_: Same logic as the minimum number.

Mode_:If there is no mode for the data, all data samples are unique and it is highly likely to be a sensitive attribute. Need to be combined with other features to decide, because for example, lab tests results in float numbers are very unlikely to have two of the same numbers among a certain number of data samples.

Variance/Standard deviation_: Unique values have very large variance and lab tests, vitals values are relatively more concentrate

Skewness_: For example, sensitive attributes like medical record numbers and encounter IDs are likely to have a symmetric distribution, with an equal number of values on either side of the mean, resulting in a skewness value of 0. On the other hand, non-sensitive attributes like lab test results and medication dosages are likely to have a skewed distribution, where the tail is longer on one side of the mean. This can be due to factors such as outliers or a natural skewness in the underlying biological processes.

Kurtosis_: Non-sensitie attributes such as lab tests, vitals signs can follow a normal distribution (most data falls beside the mean and it becomes less as data being further away from the mean) has a kurtosis of 3, which is considered as the reference value for kurtosis. This means that the normal distribution has neither peakedness nor flatness compared to other distributions. On the other hand, sensitive attribute such as medical IDs has a uniform distribution, with a kurtosis of -1.2. This indicates that the uniform distribution has flatter peaks and thinner tails compared to the normal distribution.

Num zeros/Num negatives:_medications, diagnosis, treatment often uses 0 to indicate not prescribed with a medication, not diagnosed of a disease or not receiving a treatment

Histogram (bin counts, bin edges)_: For sensitive attributes, we may expect to see a more uniform distribution of values across the bins or a few dominant values with a small number of other values scattered across the bins. For example, if we look at a histogram of birth year, we may expect to see a relatively uniform distribution with a slight peak for the most common birth year. On the other hand, non-sensitive attributes like lab results may have more skewed distributions with a few dominant values and a large number of values clustered around zero or a specific range.

Bin counts_: For example, if a column has a small number of distinct values with a high frequency in each bin, it may indicate a sensitive attribute, such as a patient's unique medical record number or social security number. On the other hand, non-sensitive attributes such as lab test results or medication dosages may have a larger number of distinct values with more evenly distributed bin counts.

Bin edges_: For example, if a column has a narrow range of values with a small number of distinct values, it may be a sensitive attribute. On the other hand, if the column has a wide range of values with many distinct values, it is less likely to be a sensitive attribute. Additionally, if the bin edges reveal patterns or clusters of values, it may indicate that the column contains sensitive information.

Quantiles (0.25, 0.75)_: first quartile (Q1) and third quartile (Q3) can provide insights into the distribution of the values in the column. For sensitive attributes, the values may be more concentrated around a certain range, resulting in a smaller interquartile range (IQR) and a higher median. In contrast, for non-sensitive attributes, the values may be more spread out, resulting in a larger IQR and a lower median.

Categories_: if a column contains sensitive attributes such as ethnicity, race, or religion, then the values in the column will be unique and categorical. On the other hand, non-sensitive attributes such as lab tests, medication dosages, and vitals, will have a wide range of values and are not categorical.

Unique count:_ Sensitive attributes may have a smaller number of distinct entries than non-sensitive attributes, especially for categorical attributes like sex and ethnicity.

Unique ratio:_ if a column has a high proportion of distinct entries (i.e., a large number of unique values compared to the total number of entries in the column), it could suggest that the column contains sensitive information that is unique to each individual.

Categorical count:_ helps to identify the distribution of the data across different categories, and can provide insights into whether a particular attribute is sensitive or not.

Gini impurity:_ the probability of a data sample is labeled wrong if it is randomly labeled according to the distributions of labels in this column

Diversity index:_ If a column has high diversity, meaning that the values in that column are unique or distinct from one another, it may indicate that the column contains sensitive information, such as a medical record number or an encounter ID.

Precision (min, max, mean, var, std, sample size, margin of error, confidence level)_: Statistics with respect to the number of digits in a number for each sample, because sensitive attributes may have a uniform number of digits, e.g., medical record number.
