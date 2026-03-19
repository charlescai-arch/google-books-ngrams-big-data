# Big Data Wrangling with Google Books Ngrams

## Overview
This project demonstrates an end-to-end big data workflow using AWS EMR, Hadoop, HDFS, Spark, and Amazon S3. The goal was to load a large public dataset from S3 into HDFS, process it in PySpark, filter it to the token `"data"`, write the filtered output back to HDFS, merge the output into a single CSV, upload it to a personal S3 bucket, and analyze the results locally using pandas and matplotlib.

## Objective
The objective of this project was to apply big data fundamentals in a distributed cloud environment and complete a full workflow from cloud ingestion to local visualization.

## Tools & Technologies
- AWS EMR
- Hadoop
- HDFS
- Apache Spark / PySpark
- Amazon S3
- Python
- pandas
- matplotlib
- Jupyter Notebook

## Dataset
The dataset used was the Google Books Ngrams dataset, provided through a public S3 bucket as a CSV file:

`s3://brainstation-dsft/eng_1M_1gram.csv`

It contains token-level word usage information across published books over time.

## Workflow
1. Created an EMR cluster configured for Spark
2. Connected to the primary node via SSH
3. Copied the dataset from public S3 into HDFS
4. Loaded the CSV into a PySpark DataFrame
5. Described the dataset structure and summary statistics
6. Filtered the dataset to rows where `token = 'data'`
7. Wrote the filtered output back to HDFS
8. Merged Spark part files into a single CSV
9. Uploaded the merged CSV to a personal S3 bucket
10. Read the file locally into pandas and plotted token frequency over time

## Key Results
- Original dataset size: **261,823,225 rows**
- Columns: `token`, `year`, `frequency`, `pages`, `books`
- Filtered dataset size (`token = 'data'`): **316 rows**
- Year range of filtered data: **1584 to 2008**
- Maximum observed frequency: **254,561**

The visualization showed that the token `"data"` remained rare for centuries, then increased sharply throughout the 20th century, especially in the later decades.

## Visualization

[Occurrences of the token 'data' over time](images/'data' token freq line plot.png)

## Repository Contents
- `reports/` – project report in PDF format
- `notebooks/` – local analysis notebook and optional EMR notebook
- `images/` – screenshots and visual assets
- `README.md` – project summary and documentation

## Next Steps
Given more time, I would:
- expand the token analysis to compare multiple words or themes over time

## Author
Charles Cai  
[LinkedIn](https://www.linkedin.com/in/caicharles98)
