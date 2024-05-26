# Google-stack-env

![Alt text](environment-google.png)


## INTRODUCTION
This is project to build simple Data Science Environment with google stack. It suitable for small business and only have small data to analyze. Due to data privacy, In this sample project we use data Google Analytics Sample provided by Google. The main goals of this project are below:
- Develop data science environment using Google Platform.
- Generate advance machine learning model to predict demand of category products.
- Visualize the result into dashboard. This dashboard must give insights about product demand.

The constraint about this project:
- We focus on customers in United States.
- We choose the top 5 category products.
- the data displayed is the last 3 months data.
- The data for modeling is transaction data from 2016-08-01 - 2017-08-01.

The result visualization result is [here](https://lookerstudio.google.com/reporting/cafa51c6-4cfb-4cc3-959b-5135f98169d6/page/HIA1D).

Documentation about data [here] (https://support.google.com/analytics/answer/3437719?hl=en)

NOTE: Some data intentionally omitted.

### How to Export Data from Google Analytics to BigQuery
Please see this tutorial from Google, how to export the data from Google Analytics to BigQuery by click this [link](https://www.youtube.com/watch?v=u4QlVsNh2Q4)


### How to Connect BigQuery to Notebook

Connecting Google BigQuery to a Jupyter Notebook involves a few steps. Here's a detailed guide to help you set up and run queries on BigQuery from a Jupyter Notebook:

#### 1. Set Up Your Google Cloud Project
Before you can use BigQuery, you need a Google Cloud project with billing enabled.

1. **Create a Google Cloud Project:**
   - Go to the [Google Cloud Console](https://console.cloud.google.com/).
   - Create a new project or select an existing one.

2. **Enable the BigQuery API:**
   - In the Google Cloud Console, navigate to `APIs & Services` > `Library`.
   - Search for "BigQuery API" and click "Enable".
   

#### 2. Install Necessary Python Packages
You need to install the `google-cloud-bigquery` and `pandas` libraries. You can do this via pip:

```bash
pip install google-cloud-bigquery pandas
```

#### 3. Authenticate Your Google Cloud Account
You need to authenticate your Google Cloud account to access BigQuery.

1. **Create a Service Account:**
   - Go to the [Service Accounts](https://console.cloud.google.com/iam-admin/serviceaccounts) page in the Google Cloud Console.
   - Create a new service account and grant it the `BigQuery User` role.
   - Generate a new key (JSON) and download it.

2. **Set the Environment Variable:**
   - Set the `GOOGLE_APPLICATION_CREDENTIALS` environment variable to the path of the JSON file you downloaded. You can do this in your Jupyter Notebook:


```python
import os
os.environ["GOOGLE_APPLICATION_CREDENTIALS"] = "SERVICE_ACCOUNT PATH"
```

3. **Use the package to notebook**
- You can see the documentation in [here](https://cloud.google.com/bigquery/docs/python-libraries)

### Workflow

![Alt text](project-workflow.png)

The explanation:
1. Export data from Google Analytics into BigQuery
2. Exported data then will be prepared for modeling
3. Import the modeling result and addition data into BigQuery
4. Import data from BigQuery into Looker Studio and visualize the result
