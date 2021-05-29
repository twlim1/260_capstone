# Using NLP to Predict the Severity of Cyber Security Vulnerabilities

Cyber-attacks continue to be one of the world’s foremost safety and economic threats, and, in recent years, have become 
more numerous and severe.  Cybersecurity engineers use industry-standard “Common Vulnerabilities and Exposure” (CVE) 
records to understand and address known threats.  CVE records generally contain “Common Vulnerability Scoring System” 
(CVSS) scores, which indicate a human-determined level of severity. These scores are important to cybersecurity 
engineers in threat prioritization. Unfortunately, nearly half of all CVE records have not yet been assigned CVSS v3 
scores, a critical component of the overall CVSS score.  The VulnerWatch product is introduced as a machine learning 
solution for predicting CVSS v3 scores. Bidirectional Encoder Representation (BERT) is used on CVE record text 
descriptions to predict eight metrics that, in aggregate, indicate a CVSS v3 score. VulnerWatch provides the user with 
a prioritized list of CVE records that do not have human-determined CVSS v3 scores, along with a predicted score.  
It also allows the engineer to manually enter text describing threats and receive a predicted CVSS v3 score in near 
real-time. The accuracy of predictions for metrics determining CVSS v3 scores is favorable, averaging close to 0.9, 
with similar levels of precision and recall. Resultant CVSS v3 score predictions are also favorably accurate 
(MSE = 1.27, MAE = 0.5, R2= 0.51). At this level of accuracy, VulnerWatch is deemed to be successful in providing a 
valuable tool in combatting cyber-attacks.

## Data are saved in Git Large File Storage (LFS) 
Refer to the link for usage. https://git-lfs.github.com/
