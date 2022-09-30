---
seotitle: Labor Economics Winter 2021
title: "Labor Economics, Session 01: A glance at the data"
description: Exercise in Labor Economics, winter term 2021
author: Johannes Michael Ossatnik
type: post # Defines the layout. Default is post.
updated: 2021-04-23T13:23:00+00:00 # This date is set by the chair, please do not edit.
headerimage: # Image for the header
sitemap:
  lastmod: 2021-04-25T20:35:00+00:00  # This date is set by the chair, please do not edit.
url: /labor-econ-01/ # The URL is created by the chair, please do not edit.
tags: # Tags are supplied by the chair, please do not edit.
    - course material
    - labor economics
    - Student Master
---

## <a name='content'>Content</a>
- **[Welcome](#welcome)**
- **[Course outline](#courseoutline)**
- **[Why Stata?](#whystata)**
<br><br>
- **[Homework 1](#homework1): Get the data**
- **[Homework 2](#homework2): Linkage validation**


<a name='welcome'></a>
## <span style="color:orange">[Welcome](#content)</span>
In this exercise accompanying the lecture you will work with data from the Current Population Surcey by the U.S. Bureau of Labor Statistics.  The course is held in English and so must be your project work.
You should choose a topic early and download the data you need, so that you can work on your own data set for the tasks that might fit to your analysis as well.
Since we use Stata for this exercise, every participant needs a computer. I would like to ask you to work on your own machines. Stata is available via the remote desktop environment provided by the IMTZ.

<a name='courseoutline'></a>
## <span style="color:orange">[Course outline](#content)</span>
In this course, we will work on the Current Population Survey (CPS), which is commissioned by the U.S. Bureau of Labor Statistics.
The data we use is provided by IPUMS (Integrated Public Use Microdata Series, University of Minnesota).
This version of the data is reprocessed and harmonized for many variables. The most noteable feature is the creation of a unique individual identifier, that lets you track individuals across 4 months or 2 years.
In all exercises, we will work on data from the CPS. Your projects will base on data from the CPS as well.

The course covers basic descriptive statistics, analysis of sub samples, difference in difference analysis, the regression discontinuity approach and a search and matching model. For the latter we will use Matlab (via the remote desktop environment).

At the end of the course you will be more familiar with the data and maybe also with Stata. This course should show you that tackling exentsive data is nothing to be afraid of. You will obtain some insights into possible analysis of labor market data.

<a name='whystata'></a>
## <span style="color:orange">[Why Stata?](#content)</span>
Stata is a proprietary statistical software and pretty common in social sciences. A big community with diverse background supplies packages for almost every need and answers to almost every question.
Even though I would like to refrain from using proprietary software, I choose Stata because it can handle bigger data sets quite well and - most importantly - quick.
The CPS extracts you are going to create will most likely be several gigabytes in size.
Stata offers a short-term license for students, which expires after one week. You can apply for it here: https://www.stata.com/customer-service/short-term-license/.
For bigger data sets, best practice would be to create a smaller subsample from your extract to work on via the remote desktop environment and finish the .do-file for your analysis of the whole data during the one week stata is offering you a free license.   

But eventually, the choice is up to you: For your analysis, feel free to use whatever tool you prefer working with.

<a name='homework1'></a>
## <span style="color:orange">[Homework 1](#content)</span>

Visit <a href="https://cps.ipums.org/cps/">https://cps.ipums.org/cps/</a> and create an account. Register with any valid e-mail adress, preferably your uni-mail adress. Select all the variables and samples potentially relevant to your project. Use the desciprtion of the variables to decide which to include in your extract. Try to minimise the number of variables in your extract. Submit your request. It may take some time for your extract to be prepared and ready for download. The download link will be provided to you via e-mail once the data is processed.

Hint #1: If you already stumbled upon research papers dealing with questions similar to your project and working with CPS-data, you may include the author's choice of variables in your set as well.

Hint #2: take your time. This task is not trivial. Your work depends on the data at hand. Carefully chosen variables suited for answering a particular question facilitate your research.

- We confine our analysis to the years 2000 - 2019
- Choose your variables wisely: The number of variables inflates the size of the data set. E.g. 80 variables across monthly data between 2000 and 2019 constitute more than 7 gb of data
- adding supplements you receive data sets as large as 50 gb and more
- the bigger your extract,
  - the more time it takes the IPUMS server to process your request (from several hours to possibly several days)
  - the more time it takes you to download it
  - the more time and processing power is required to modify and analyse the data
- Good practice: Select cases to reduce the size, drop redundant variables (e.g. recodes), do not include every supplement (since for most individuals in the monthly survey the values are blank anyway)

<a name='homework2'></a>
## <span style="color:orange">[Homework 2](#content)</span>

Validate the CPSID linkages following the hints in the description of the variable. (<a href="https://cps.ipums.org/cps-action/variables/cpsidp#description_section">LINK</a> to description)

It is recommended to verify the linkages by checking the consistency of the variables AGE, RACE and SEX.
For a linkage to be valid, a CPSID should have a unique gender and race. Though age is not a static variable, it should be in a certain range for the survey lifetime of an individual, i.e. between <span>\\( AGE_{i, t=1} = AGE_{i, t=0} + d \\)</span> with \\( d \in [0, 2] \\) .

Hint: This is not an easy task to do. You might come up with an own approach outside of Stata, you might be able to write proper code in Stata. Fortunately we can find a do-file for that <a href="https://cps.ipums.org/cps/resources/workshop_materials/validate_long.txt">here</a>. Check the code and try to understand what is done there. Do you agree with this approach? Would you do it differently?
