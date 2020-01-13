# InstyMatch [![Generic badge](https://img.shields.io/badge/Build-Passing-lightgreen.svg)](https://shields.io/) [![Generic badge](https://img.shields.io/badge/License-MIT-green.svg)](https://github.com/wlanalysis2017/InstyMatchAPI/blob/master/LICENSE.txt) [![Generic badge](https://img.shields.io/badge/Version-1.0.0-blue.svg)](https://shields.io/)


## Table of Contents

* [About the Project](#about-the-project)
* [Try it out](#try-it-out)
* [Getting Started](#getting-started)
* [License](#license)
* [Contact](#contact)


## About The Project


The *InstyMatch API* allows users to match **one Job Description** against up to **10 resume files** and obtain a scored result. 
*  The result scores are broken up into 3 categories: **Dynamic**, **Static**, and **Distributed**. 
* **Dynamic scores** represent a Resumes qualifications with respect to the Job Description (e.g. how well the Skills section in a Resume match up against the Skills required in the Job Description). 
* **Static scores** are given in respect to the Resume independently (e.g. The higher the education degree achieved or the more prestigious the university then the higher the educational static score). 
* **Total score** is a combination of the Dynamic & Static scores, after which are given the **Distributed scores**, which are a measure of how much each Dynamic & Static section weighed on the resulting Total Score. 
* Lastly a Feedback value is returned with every Resume with feedback from our internal engine as to how one can improve the contents of their Resume.

## Try it out
[https://instymatch.com/docs/](https://instymatch.com/docs/)

## Getting Started

1. Build a multipart/form-data POST request to [https://instymatch.com/openapi/instymatch](https://instymatch.com/openapi/instymatch)
2. Attach to form-data each Resume file to score with a form-value of "file" + index (0-9) (Up to 10 Resume files may be submitted).
```sh
"file0" : firstResumeFileToScore.pdf
```
```sh
"file1" : secondResumeFileToScore.pdf
```
```sh
"file2" : thirdResumeFileToScore.pdf
```
3. Attach to form-data of key name "JobPostingText" the text of a Job Description to score your Resume set against.
```sh
"JobPostingText" : "Must have a BS in Computer Science. Must have 2+ years of experience ..."
```
4. Parse successful JSON response from server
```sh
{"Data":{"firstResumeFileToScore.pdf":{"dist_work":5.11,"dist_sim":61.64,"dist_skill":16.08,"dist_github":5.17,"dist_educ":12,"static_educ":48.37,"static_github":70,"static_sim":15.52,"static_skill":89,"static_work":24.98,"dynamic_sim":65.13,"dynamic_skill":51.6,"dynamic_work":0,"dynamic_github":25,"total":66.55,"feedback":"The total score of this resume is ranked 42.24% in our database. The ranking among other resumes for total scores (static \u0026 dynamic) of education: 64.81%, skill: 92.94%, work experience: 0.45%, and similarity to job description: 17.34%.  The number of tech-related skills are good and higher than other similar resumes. The static skill score is good. The static score for work experience is low compared to other similar resumes. Adding more action words, work exprience years, and specific tech-related company names to the resume can increase this score."},"secondResumeFileToScore.pdf":{"dist_work":5.11,"dist_sim":61.64,"dist_skill":16.08,"dist_github":5.17,"dist_educ":12,"static_educ":48.37,"static_github":70,"static_sim":15.52,"static_skill":89,"static_work":24.98,"dynamic_sim":65.13,"dynamic_skill":51.6,"dynamic_work":0,"dynamic_github":25,"total":66.55,"feedback":"The total score of this resume is ranked 42.24% in our database. The ranking among other resumes for total scores (static \u0026 dynamic) of education: 64.81%, skill: 92.94%, work experience: 0.45%, and similarity to job description: 17.34%.  The number of tech-related skills are good and higher than other similar resumes. The static skill score is good. The static score for work experience is low compared to other similar resumes. Adding more action words, work exprience years, and specific tech-related company names to the resume can increase this score."},"thirdResumeFileToScore.pdf":{"dist_work":5.11,"dist_sim":61.64,"dist_skill":16.08,"dist_github":5.17,"dist_educ":12,"static_educ":48.37,"static_github":70,"static_sim":15.52,"static_skill":89,"static_work":24.98,"dynamic_sim":65.13,"dynamic_skill":51.6,"dynamic_work":0,"dynamic_github":25,"total":66.55,"feedback":"The total score of this resume is ranked 42.24% in our database. The ranking among other resumes for total scores (static \u0026 dynamic) of education: 64.81%, skill: 92.94%, work experience: 0.45%, and similarity to job description: 17.34%.  The number of tech-related skills are good and higher than other similar resumes. The static skill score is good. The static score for work experience is low compared to other similar resumes. Adding more action words, work exprience years, and specific tech-related company names to the resume can increase this score."}},"ErrorMessage":"","Message":"Success","Code":200}
```

## License

Distributed under the MIT License. See [LICENSE](https://github.com/wlanalysis2017/InstyMatchAPI/blob/master/LICENSE.txt) for more information.

## Contact

Contact us @ [InstyMatchSupport](mailto:yevgeniy.vasilyev@wailiantech.com?subject=[Github]InstyMatch%20API)