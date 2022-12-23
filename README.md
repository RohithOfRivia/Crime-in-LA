![banner](assets/Credit_card_approval_banner.png)


![Python version](https://img.shields.io/badge/Python%20version-3.9%2B-green)
![GitHub last commit](https://img.shields.io/badge/Last%20Commit-Dec%202022-yellowgreen)
![GitHub repo size](https://img.shields.io/github/repo-size/semasuka/Credit-card-approval-prediction-classification)
![Type of ML](https://img.shields.io/badge/Type%20of%20ML-Binary%20Classification-red)
![License](https://img.shields.io/badge/License-MIT-green)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1CfV6yEsHBjFiJbTKwY72k2g4AvszcF5R)
[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://share.streamlit.io/semasuka/credit-card-approval-prediction-classification/main/cc_approval_pred.py)
[![Open Source Love svg1](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://github.com/ellerbrock/open-source-badges/)

Badge [source](https://shields.io/)

## Authors

- [@RohithOfRivia](https://github.com/RohithOfRivia)

## Table of Contents

  - [Project Description](#project-description)
  - [Data source](#data-source)
  - [Methods](#methods)
  - [Tech Stack](#tech-stack)
  - [Quick glance at the results](#quick-glance-at-the-results)
  - [Lessons learned and recommendation](#lessons-learned-and-recommendation)
  - [Limitation and what can be improved](#limitation-and-what-can-be-improved)
  - [Run Locally](#run-locally)
  - [Explore the notebook](#explore-the-notebook)
  - [Deployment on streamlit](#deployment-on-streamlit)
  - [App deployed on Streamlit](#app-deployed-on-streamlit)
  - [Repository structure](#repository-structure)
  - [Contribution](#contribution)
  - [Blog post](#blog-post)
  - [Project featuring](#project-featuring)
  - [License](#license)




## Project Description

In this project, recent criminal activity data based in Los Angeles is analyzed extensively to find patterns and insights for many different aspects of crime. No. occurences for different types of crime, sex of affected victims, weapons used, location and premise of the incident and many more things are investigated with this dataset. 

The user can interact with the Tableau workbook for more in-depth and focused visualizations.
 
## Data source

- [Crime Data from 2020 to Present](https://data.lacity.org/Public-Safety/Crime-Data-from-2020-to-Present/2nrs-mtv8)

## Methods

- Exploratory data analysis
- Bivariate analysis
- Multivariate correlation
- S3 bucket model hosting
- Model deployment

## Tech Stack

- Python (refer to requirement.txt for the packages used in this project)
- Tableau(interface for the model)



## Quick glance at the results

Crimes grand total: 

![Total no. of crimes](assets/kpi.png)

### Dashboards
**Monthly occurences by category - Map**

![Monthly occurences by category - Map](assets/map.png)
 
**No. of incidents by month**
\
\
![No. of incidents by month](assets/by&#32;month.png)
\
\
**Crime categories vs sex**
![Crime categories vs sex](assets/victim&#32;sex&#32;vs&#32;cat.png)
\
\
**Age vs type of crimes**
![Age vs type of crimes](age&#32;vs&#32;cat.png)
\
\
**Status of investigation and victim sex**
![Status of investigation and victim sex](status&#32;and&#32;time.png)
\
\
**Premise & weapons used**
![Premise & weapons used](location&#32;and&#32;weapons.png)
\
\
**Percentage of incidents by area**
![Percentage of incidents by area](map2.png)






- **The final model used for this project: Gradient boosting**
- **Metrics used: Recall**
- **Why choose recall as metrics**:
  Since the objective of this problem is to minimize the risk of a credit default, the metrics to use depends on the current economic situation:

  - During a bull market (when the economy is expanding), people feel wealthy and are employed. Money is usually cheap, and the risk of default is low because of economic stability and low unemployment. The financial institution can handle the risk of default; therefore, it is not very strict about giving credit. The financial institution can handle some bad clients as long as most credit card owners are good clients (aka those who pay back their credit in time and in total).In this case, having a good recall (sensitivity) is ideal.

  - During a bear market (when the economy is contracting), people lose their jobs and money through the stock market and other investment venues. Many people struggle to meet their financial obligations. The financial institution, therefore, tends to be more conservative in giving out credit or loans. The financial institution can't afford to give out credit to many clients who won't be able to pay back their credit. The financial institution would rather have a smaller number of good clients, even if it means that some good clients are denied credit. In this case, having a good precision (specificity) is desirable.

    ***Note***: There is always a trade-off between precision and recall. Choosing the right metrics depends on the problem you are solving.

    ***Conclusion***: Since the time I worked on this project (beginning 2022), we were in the longest bull market (excluding March 2020 flash crash) ever recorded; we will use recall as our metric.


 **Findings**

- Based on the created visualizations and analysis, it is clear that some types of crime have a very clear area where incidents keep being reported. For example, sex trafficking and many related crimes are focused primarily near the Vermont Knolls area. Most of these incidents have not yet resulted in an arrest of the offender. Interestingly, 80% of all crimes have not yet resulted in an arrest.

- Top 3 common crimes are vehicle theft, simple assault, and burglary from vehicle. Simple assault has a much higher concentration around the Downtown area. The other two are much more spread out throughout the city. 

- About 25% of crimes are reported to have happened on the street. 45% of crimes occur in confined areas like apartments, garage, vehicles etc. 

 - Battery is the most common type of crime for victims belonging to all age categories. 66% of burglaries occur to a senior, whereas 72% of assaults with a deadly weapon occur to adults. In fact, 60% of all crimes are faced by adults.
 
 - While most crimes occur without any weapons (about 70%), at least 10,400 out of more than 500k incidents involved the use of a handgun. 

- Males are 3 times more likely to fall victim to an assault to a deadly weapon. Females are 3 times more likely to suffer assault from their partners. These incidents have a higher chance to occur during night time. This is when you should be the most careful to stay safe.

## Limitation and what can be improved

- The victim sex is unclear in a large number of incidents, so the data was filtered accordingly for analysis. 
- Statistical tests to confirm if some of the findings are statistically significant. (Correlation test, t-test)

- More findings to be discovered from the data



## Run Locally
Initialize git

```bash
git init
```


Clone the project

```bash
git clone https://github.com/semasuka/Credit-card-approval-prediction-classification.git
```

enter the project directory

```bash
cd Credit-card-approval-prediction-classification
```

Create a conda virtual environment and install all the packages from the environment.yml (recommended)

```bash
conda env create --prefix <env_name> --file assets/environment.yml
```

Activate the conda environment

```bash
conda activate <env_name>
```

List all the packages installed

```bash
conda list
```

Start the streamlit server locally

```bash
streamlit run cc_approval_pred.py
```
If you are having issue with streamlit, please follow [this tutorial on how to set up streamlit](https://docs.streamlit.io/library/get-started/installation)

## Explore the notebook

To explore the notebook file [here](https://nbviewer.org/github/semasuka/Credit-card-approval-prediction-classification/blob/main/Credit_card_approval_prediction.ipynb)

## Deployment on streamlit

To deploy this project on streamlit share, follow these steps:

- first, make sure you upload your files on Github, including a requirements.txt file
- go to [streamlit share](https://share.streamlit.io/)
- login with Github, Google, etc.
- click on new app button
- select the Github repo name, branch, python file with the streamlit codes
- click advanced settings, select python version 3.9 and add the secret keys if your model is stored on AWS or GCP bucket
- then save and deploy!

## App deployed on Streamlit

![Streamlit GIF](assets/gif_streamlit.gif)

Video to gif [tool](https://ezgif.com/)
## Repository structure


```

├── assets
│   ├── confusion_matrix.png                      <- confusion matrix image used in the README.
│   ├── gif_streamlit.gif                         <- gif file used in the README.
│   ├── heatmap.png                               <- heatmap image used in the README.
│   ├── Credit_card_approval_banner.png           <- banner image used in the README.
│   ├── environment.yml                           <- list of all the dependencies with their versions(for conda environment).
│   ├── roc.png                                   <- ROC image used in the README.
│
├── datasets
│   ├── application_record.csv                    <- the dataset with profile information (without the target variable).
│   ├── credit_records.csv                        <- the dataset with account credit records (used to derive the target variable).
│   ├── test.csv                                  <- the test data (with target variable).
│   ├── train.csv                                 <- the train data (with target variable).
│
│
├── pandas_profile_file
│   ├── credit_pred_profile.html                  <- exported panda profile html file.
│
│
├── .gitignore                                    <- used to ignore certain folder and files that won't be commit to git.
│
│
├── Credit_card_approval_prediction.ipynb         <- main python notebook where all the analysis and modeling are done.
│
│
├── LICENSE                                       <- license file.
│
│
├── cc_approval_pred.py                           <- file with the model and streamlit component for rendering the interface.
│
│
├── README.md                                     <- this readme file.
│
│
├── requirements.txt                              <- list of all the dependencies with their versions(used for Streamlit).

```
## Contribution

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change or contribute.

## Blog post

The accompanying blog post for this project can be found [here](https://semasuka.github.io/blog/2022/10/12/credit-card-approval-prediction.html)

## Project featuring

This project was featured on [Luke Barousse Youtube Channel](https://www.youtube.com/c/LukeBarousse), Click on the thumbnail to watch the video

[![IMAGE_ALT](https://img.youtube.com/vi/5Q0gB7imNOo/0.jpg)](https://www.youtube.com/watch?v=5Q0gB7imNOo&t=222s)


## License

MIT License

Copyright (c) 2022 Stern Semasuka

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

Learn more about [MIT](https://choosealicense.com/licenses/mit/) license
