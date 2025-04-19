# Assignment: Questionnaire Design and Sample Evaluation

## Requirements

The goal of this assignment is to practice developing and evaluating sampling materials.

### Part A - Survey Design:

Select one of the scenarios below and design a survey to meet the need(s) outlined in the prompt.

1.	In two to three sentences, describe the purpose of your survey
2.	Describe your target population, sampling frame, sampling units, and overall sampling strategy.
3.	Write a 5-10 question survey to address your chosen scenario below.

##### Scenarios
1.	You work in the Human Resources Department at a large tech company. Over the past few months, the company has been experiencing a high turnover rate across many of its departments, specifically within the entry- and lower-level positions. The company wishes to understand why this turnover is happening, and what changes need to occur to improve employee satisfaction.
2.	You work for a Canadian national political party during a federal election. Throughout the campaign period, your party has seen relatively high approval ratings, but an opposing party is also polling favorably and may still have a chance to win the election. You are one month away from the election and you want to understand what voters want from your party and its leader in order to maintain your lead and eventually win the election.
3.	You are a student researcher in the sociology department at the University of Toronto. You are working on a research project that concerns the relationship between music taste and age. This involves both comparisons between different people of different ages and comparisons of the same individual at different ages during their lifetime. You wish to understand to what extent age influences music taste, specifically as it relates to perceptions of popular music. Your results will be written into an academic paper that you hope to publish.

### Part B - Survey Evaluation:

For the **Canadian General Social Survey on Giving, Volunteering, and Participating, 2018 (cycle 33)**, conducted by Statistics Canada find any and all available documentation for the data gathered and identify and describe the survey features indicated below.

1. Sample type
2. Sample size
3. Target population
4. Sampling frame
5. Survey mode(s) 
6. Timeline
7. Response rate
8. Weights
9. Data processing
10. Cleaning, imputation, etc
11. Sources of error
12. Limitations, known biases, etc
13. Link to documentation and any additional sources used


# Your Changes: Assignment Completed by Darshan Panesar

## Part A - Survey Design: 

The number of your chosen topic: `3`

Describe the purpose of your survey:
```
This survey aims to assess whether music taste is influenced by age in adults of various age ranges. Alongside, this survey will also gauge perceptions of popular music across those age groups. Retrospectively, this survey hopes to also ascertain how music taste changes with age from an individuals youth. 
```

Describe your target population, sampling frame, sampling units, and observational units:
```
a.	Target population: adults 18-65 years of age
b.	Sampling frame: 1000 university students, faculty and staff filling a quota of 200 per age group} 18-24, 25-34, 35-44, 45-54, 55-65 years of age
c.	Sampling units: individuals 
d.	Overall sampling strategy: Stratified Sampling because I am conceptually dividing individuals into the above 5 age groups. Then 200 individuals are “taken”/evaluated from that group. But this strategy involves convenience and quota sampling as individuals are all from U of T. There will be qr codes posted in each department and participants will need to provide an email address during the consent process. (this will avoid duplication).

```

Your 5-10 question survey:
```
1.	What is your year of birth:____________________

2.	How many hours a day do you listen to music:____________________

3.	How many hours a week do you listen to music:___________________

4.	What is your favourite song currently:__________________________________

5.	What is your favourite genre of music currently? (pick one)
   a.	Pop
   b.	Rock
   c.	Hip Hop/Rap
   d.	Electronic/Dance Music (EDM)
   e.	R&B/Soul
   f.	Country
   g.	Classical

6.	Have you listened of any of the following artists/musicians over the last week? (select all that apply)
   a.	Taylor Swift
   b.	Dua Lipa
   c.	Travis Scott
   d.	The Black Eyed Peas
   e.	Tim McGraw
   f.	The Weeknd
   g.	The Royal Symphony Orchestra

7.	Please select your main way of listening to music (pick one):
   a.	Streaming Services (Spotify, apple music, etc.)
   b.	Music videos and YouTube
   c.	Digital Download
   d.	Radio
   e.	CDs
   f.	Vinyl
   g.	Cassette Tape

8.	What emotion does your favourite song elicit (pick one):

9.	Think back to your youth (high school), what was your favourite song then:_____________________

10.	Think back to your youth (high school) what was your favourite genre of music then:
   a.	Pop
   b.	Rock
   c.	Hip Hop/Rap
   d.	Electronic/Dance Music (EDM)
   e.	R&B/Soul
   f.	Country
   g.	Classical

```

## Part B - Survey Evaluation:

Identify and describe survey features:

```
1.	Sample type: 
The sample type can be broken down into 3 parts. Overall, it’s a cross-sectional sample design, using a stratified sample which uses probability sampling.  Sampling was done at the province and census metropolitan area level. Lastly it was random sampling by selecting one randomly selected individual (15 years or older) from each household.

2.	Sample size: The sample size was noted as 24000 (with a response rate of 41.9% it may be more appropriate to estimate (0.419*50000 = 20950 or 0.419*40000 = 16760 if accounting for response rate)).

3.	Target population: The target population for the GSS Giving, volunteering and participating includes all persons 15 years of age and older living in the ten provinces of Canada. It excludes full-time (residing for more than six months) residents of institutions.

4.	Sampling frame: The sampling frame was a representative field sample target set that would be representative of the total population. This was 50000 (later noted as 40000) potential survey respondents (surveys sent out) who had landlines, cell phones, and various admin sources and were associated with a single address.

5.	Survey mode(s): Recruitment via phone. Responses were collected via phone (computer assisted telephone interviews) and electronic questionnaires.

6.	Timeline: Data collection for this reference period: 2018-09-04 to 2018-12-28.

7.	Response rate: The overall response rate is 41.9%.

8.	Weights: Estimation section notes the weighting factors. Weighting was using because this is a probability sample. They were mainly used to adjust for discrepancies such that the sample was representative of the target population with regard to certain characteristics. It was done for non-volunteers and for income (by province). It was noted as WGHT_PER which was a basic weighting factor for analysis at the individual person level. This was to calculate estimates of the number of persons have one or several given characteristics. Bootstrap writing were also created for design-based variance estimation.

9.	Data processing: Data processing was done using a structured framework for processing survey data with predefined steps/tools called SSPE. The SSPE includes error detection, feasibility and customization, efficiency for processing workflow, and quality assurance. There was automatic and manual processing at macro and micro levels (various stages). These included family, consistency, and flow edits. In addition, checks were performed to ensure survey data consistency. Lastly error checks were done through with edits programmed into the CATI system that was used.

10.	Cleaning, imputation, etc:
Three steps are included in this section: 
   a.	Estimation which was denoted above in the weights section.
   b.	For imputation,  it was made using donor records selected using a scoring system. Comparisons between item or partial non    item individual’s responses were made with characteristics on all donor records. Then based on comparative scoring, missing data was imputed based on highest comparator score between respondent and donor score. For values that donor imputation could not be used mean imputation amosite the entire donor pool was used. 

Additionally, a 9 step imputation strategy was used:
	i. personal and family income
	ii./iii./iv. Imputation of formal volunteer variables in the master file.
	v./vi. Informal volunteer variables in the master file.
vii./viii./ix. Imputation of variables in the donation file and solicitations in the master file
Lastly personal income data was obtained from individuals’ tax data (for those who consented)	

c.	There was also a thorough Quality Assessment which included: analysis of changes over time, verifications of estimates, through cross tabulation, and confrontation with similar data sources for verification.

11.	Sources of error: There were prominent sources of error notes:
   a.	Non-sampling error: due to imperfect coverage and non-responses resulting in differences between target and survey population.
      i.	Included households without t telephone or service
      ii.	Occurs at both household and individual level
      iii.	The survey was adjusted for this by weighting  
      iv.	Other errors may include response and processing errors for data
b.	Non-Response Bias:
   i.	There was almost 60% non-response (i.e., people did not respond)
   ii.	Survey weights and imputation were used to adjust for this to some extent.
c.	Coverage Error: when sample frame is not a representation of the target population
   i.	There were some issues due to coverage error were noted as the sample frame was created using linked sources between census data, admin data, billing files. However many were mitigated or adjusted for as follows:
      1.	Coverage was improved based on the recruitment strategy in comparison to random digit dialing for recruitment.
      2.	All interviews were conducted by heavily trained interviewers and by electronic questionnaires.
      3.	However, households without phones were sill excluded.
d.	  Lastly, there may have been other non-sampling bias/error though significant efforts noted to minimize this using well tested questionnaires, proven methods (they noted proven), specialized interviewers and strict quality assessments.
 
12.	Limitations, known biases, etc
   a.	Some biases were noted as part of the error sources section. Here are some additional limitations and biases:
      i.	The questionnaires and interviews do involve some self report which may have limitations and reliability issues.
      ii.	Imputation was used (perhaps heavily) which means those values are missing and are an estimate of the true value. Therefore, there is a margin of error or bias there.
      iii.	There is definitely exclusion of groups of people namely those without landlines/phones.
      iv.	Given the age range 15 may be too young or the overall age of inclusion may have issues with age being an important moderating factor. I would also expect there is no tax data for many individuals especially those who are 18 and younger. 
      v.	Lastly, there maybe some issues with stratification they note that higher density areas look like they have more representation within the sample frame. This also raises the issue that some people may be from one place living in another therefore the demographics and survey data results may change accordingly. E.g., someone from Sudbury living in Toronto.

13.	Link to documentation and any additional sources used
All documentation was acquired from: https://www23.statcan.gc.ca/imdb/p2SV.pl?Function=getSurvey&Id=796234#a2
```

## Rubric

-	All required components are present and complete **Complete / Incomplete**
-	Choice of sampling strategy for Part A is justified and related to survey purpose **Complete / Incomplete**
-	Information for Part B is complete and correct **Complete / Incomplete**

## Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `23:59 - 18/04/2025`
* The branch name for your repo should be: `assignment-2`
* What to submit for this assignment:
    * This markdown file (a2_survey_design_and_evaluation.md) should be populated and should be the only change in your pull request.
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sampling/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [x] Create a branch called `assignment-2`.
- [x] Ensure that the repository is public.
- [x] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [x] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via the help channel in Slack. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
