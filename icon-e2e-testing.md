
# ICON Blockchain E2E Testing Workflow

### Business case idea
ICON is transitioning their network from TestNet to MainNet at this time though operators are still expected to maintain parallel copies of their network for testing purposes.  This is because we need to run various tests on non-production environments to expose security flaws that might impact MainNet.  So far, TestNet has undergone load tests but there are a wide variety of other tests that still need to be done including chaos, penetration, and various aspects on integration testing.  To orchestrate these tests, we will need a tool to execute the test, gather logs and metrics from the network, and then agregate them into KPIs that can then be then used for analysis. 

The ICON Blockchain is also considering running their own version of ["game of stakes"](https://github.com/cosmos/game-of-stakes) where users are incentivized to take down the TestNet.  This is because blockchain validator nodes are consistently under attack by malevolent actors trying to slow it down to take advantage of arbitrage.  It is a major concern, so much so that the community is trying to figure out governance policies to ensure that node operators are maintaining adequate security.  This project, if successful, could turn into a key governance tool that makes sure that P-Rep nodes are able to sustain a certain level of prescribed attack, thereby incentivizing node operators to make sure their nodes are robust. 

### Challenge

This project is broken into two components, dev ops and data engineering.  These two projects are planned to work in parallel and meeting at the end.  The dev ops portion will be a blocker to the data engineering portion as the proper way to run the dags is with a manifest attached to the dag though as soon as the airflow cluster is running on k8s, they can meet together and then the dev ops portion wrt the permissions schemes can be filled in behind that. 

#### Dev Ops 
Main challenge is going to be in setting up the airflow cluster on k8s with production ready features such as proper RBAC permissions schemes tied to identity providers.  Once you figure out all the appropriate manifests for that, you will then put all that into a immutable terraform deployment with a one-click deployment.  This won't be hard though as the pattern is pretty straightforward with terraform + terragrunt.  Proper immutability will all boil down to secrets management though which will be a challenge.  

- A prior insight fellow, [Raymond Etornam Agbeame](https://www.linkedin.com/in/retornam/) did [his project](https://github.com/retornam/kopsflow) in this space that might be helpful. 
- Setting up airflow cluster that can scale up to handle the simulated attacks and logging ETL 
- Writing a few DAGs that run a few benchmarks off of - See data engineering project 
- Setting it up in Kubernetes with a shared volume to read DAGs from 
    - This is a reach but is definately the way to go
    - Setting up kubernetes in Airflow was a non-trivial endeavor until the newer `Airflow Operator` was introduced that ran worker pods as a statefulset on k8s - would be great to find how the new operator works as I don't know.  

    
#### Data Engineering 
- Run locust load testing script to simulate traffic against a node 
- Run logs collection ETL task - assume logging cluster exists
    - Filter logs by different response types 
    - Generate latency statistics on each call 
    - Cross reference it with metrics gathered from the node to find optimal operating configuration settings  
    - Inform optimal node configuration - ie autoscaling behavior / node charetoristics 
- Run penetration tests
    - More on this later 
    

### Tools
- terraform + terragrunt 
- airflow + git sync or NFS for DAGs 
- DO
    - Permissions on airflow to sync to an IDP - something oauth 
    - CI tool 
    - Private registry
- DE
    - locust and or other load testing tool for DE
    - Dashboarding tool like [dash](https://github.com/plotly/dash) for visualization 
    - Any database you want - this should be requested from the DO fellow

### Success Metrics
- Proven workflow to run airflow
- Successful load tests 
    - Able to take down simple node configurations
- DO 
    - Immutablility all the way through
    - Proper permissions 
- DE 
    - Nice dashboards 
    - well organized DAGs 

### Difficulty
These projects will all depend on what kind of code examples you can find out there.  All of this has been done before in some variation. It is up to the fellows to find the simplest approach that satisifies all the requirements. 

