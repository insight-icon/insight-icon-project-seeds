
# ICON Blockchain Terragrunt Deployment on GCP

### Business case idea
GCP was a late entry into the major cloud provider space but have quickly caught up in feautures to AWS and Azure.  Currently they have the best kubernetes distribution and they are considered the strongest in the area of analytics.  Some of the P-Rep candidates are running on GCP and we want to support them by building out our reference architecture features from AWS onto GCP. Running infrastructure on GCP also gives redundent DDoS protection taking advantage of the internal networking feautres of each cloud.  

### Challenge
This project will have a very clear guideline of what is needed to be built, an exact feature by feature copy of what is done in AWS. There is room for creativity for sure but it will be relatively straightforward in design as we want to have the configuration steps shared between the two clouds. If the fellow wants to build in new features as well, we can try to spice the project up and give the replication back to the ICON community to do if you find things that you want to add.  

Feature:
- Nodes - P-Rep | Citizen | Sentry | Logging | Monitoring 
- Security groups
- Networking 
- Load balancers
- Alarms 
- Audit trails
- etc etc etc 

### Tools
- Terraform + Terragrunt 
- All the applications we are running on AWS 

### Success Metrics
- `one-click`
- Running tests
    - terratest / test kitchen / python other... 
- Number of components / feautures 

### Difficulty
- 2/5 
    - Simple basic replication 
- 3/5
    - Simple analytics stack with managed airflow 
    - We'll have to make sure you have a good demo with a nice DAG that runs things like load tests
- 4/5 
    - Custom alarms and reporting 
    - Other features - we can discuss 
- 5/5 Multi cloud load balancing 
    - This is going to have to do with 
