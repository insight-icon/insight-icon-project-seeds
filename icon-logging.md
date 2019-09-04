
# ICON Blockchain Centralized Logging 

**THIS PROPOSAL IS A WORK IN PROGRESS**

- This might be too simple of a project for a fellow to take on. 

This project aims to centralize the logging collection from the P-Rep, Citizen nodes, and sentry nodes for the ICON network. 

### Business case idea
We are currently developing numerous different configurations of P-Rep nodes that we will be testing under load to determine the reliability of the network.  During these tests, we will be intentionally introducing numerous different kinds of stress to the network and expect all kinds of different failures to occur.  The only way to diagnose the root cause of these failures is if we have a robust log collection infrastructure.  This project will empower numerous different workstreams that depend on those logs, thereby increasing development productivity as we gain observability into the application layer of the network. 

### Challenge
This project has two components.  
1. Basic version running that is a minimal configuration to run in an issolated environment that tracks 
2. More advanced configuration - tbd 

#### Minimal Configuration Challenges 
- This was basically [already done](https://github.com/angelayanhe/insight-elk-monitoring) by a recent fellow [Angela He](https://platform.insightdata.com/profile/2997) 
- The simple solution could be that we just run a node and spin up this docker-compose in `user-data`
- Setting up agent config from the application nodes
    - We should start to nail down what streams are coming in and how to analyze them in Kibana 
- Spinning up terraform
    - Rob will help with this.  You should have a copy of the stack you need when you start the project
- Dealing with secrets appropriately
    - We'll need to fiugre out a short and long term plan for secrets 
        - Short term we'll be going for the easiest approach and we'll just tranfer keys manually 
        - Long term we need a simple solution that the community feels comfortable with 

#### Kubernetes Configuration Challenges 
- tbd


### Tools
- terraform + terragrunt (basic architecture supplied)
- ELK stack 


### Success Metrics


### Difficulty

- 2/5 
    - Simple setup with helm 

### Resources 

#### Minimal deployment 

- [Storage best practices](https://www.elastic.co/guide/en/elasticsearch/plugins/master/cloud-aws-best-practices.html)
- [tf_aws_elasticsearch](https://github.com/terraform-community-modules/tf_aws_elasticsearch)
- [terraform-aws-elasticsearch](https://github.com/cloudposse/terraform-aws-elasticsearch)
