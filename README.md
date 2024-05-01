
# CodePath AWS S3 HoneyBucket Incident Analysis
## Description
![](https://mma.prnewswire.com/media/890598/CodePath_Logo.jpg?p=publish)  <br /><br />
Welcome to the GitHub repository for Team 32's final project in the [CodePath](https://www.codepath.org/) course, [Cybersecurity 102 - Intermediate Cybersecurity - Spring 2024 Cohort](https://www.codepath.org/courses/cybersecurity). This project presents a thorough analysis and strategic response to simulated cybersecurity threats identified in AWS S3 HoneyBucket Logs. Leveraging the AWS IRP-DataAccess framework, our project demonstrates the effective use of data from AWS S3 HoneyBuckets to improve security measures and incident response capabilities.  



## Dataset Used
<img src="https://securitydatasets.com/_static/logo.png" width="100" height="100"> </img>  
[Security Datasets: AWS S3 HoneyBucket Logs](https://securitydatasets.com/notebooks/atomic/aws/discovery/SDAWS-2202181000.html)
- The Security Datasets project is an open-source initiative that contributes malicious and benign datasets, from different platforms, to the infosec community to expedite data analysis and threat research.
- This dataset represents adversaries trying to scan, discover and access open S3 honeybucket based on known hostname patterns
- Here is a [quick guide](https://docs.google.com/document/d/1O6lXYG97sNBVd_iQPrYLgws4izJ2PVqb5237-LbRHCc/edit) on how to locate the ```.csv``` files from these datasets.


## Playbook Used
<img src="https://avatars.githubusercontent.com/u/8931462?s=200&v=4" width="100" height="100"> </img>  
[AWS Incident Response Runbook Samples: IRP-DataAccess.md](https://github.com/aws-samples/aws-incident-response-playbooks/blob/master/playbooks/IRP-DataAccess.md)<br /><br />
**Playbook Outline**
  1. Gather Evidence
  1. Contain and then eradicate the incident
  1. Recover from the incident
  1. Conduct post-incident activities, including post-mortem and feedback processes
 
## Key Features: 
- **Incident Analysis using [Splunk](https://www.splunk.com/)**: Detailed examination of anomalous activities within AWS S3 logs using Splunk, providing insights into the patterns and tactics of potential cyber threats.
- **Incident Management with [Catalyst](https://catalyst-soar.com/)**: Utilization of Catalyst for case management and documentation, emphasizing the workflow from the threat detection to resolution.
- **Playbook Application**: Implementation of a specific incident response playbook aimed at addressing and mitigating issues identified in the HoneyBucket dataset.
- **Theat Identification and Response**: Analysis includes identification of threat vectors and deployment of strategies to mitigate risks and enhance data security.

<p align="center">
  <img src="https://www.splunk.com/content/dam/splunk2/images/social/D2E-social.jpg" width="100" height="100">
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://catalyst-soar.com/img/flask.svg" width="100" height="100">
</p>



## Technologies Used:
- 

## Team 32
Anaye Abernathy  
Elian Fernandez  
Camille Wong  
Justin Pudiquet
