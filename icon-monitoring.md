
# ICON Blockchain Node Monitoring

### Business case idea
This project aims to monitor ICON Blockchain node metrics and building alarms to respond to different events so that node operators recieve notifications when certain health checks fail, thereby alerting when problems occur. This is essential if node operators should ever want to leave their desk. 

### Challenges
Right now there is no consensus on what the best monitoring tool we should use (ie Prometheus vs TICK stack).  The fellow will first have to pick a technology and determine the cheapest way to run that configuraration on a VM.  Then the whole configuration needs to be made immutable such that nodes are bootstrapped with the proper configuration files.  This should take little time once the fellow is oriented.  

The main challenge is going to be in setting up alarms that send emails, slack notifications, and text messages when various health checks fail.  The fellow will then be wise to write tests that validate the different notifications which will be the main proof that the project was a success.  When the fellow reaches this point, the E2E testing project (if it is taken up), will be providing interesting simulations that will be a great demonstration of the tool in action. 

### Tools
- prometheus / influxdb 
- grafana / telegraf 
- terraform 
- CI tooling for tests 

### Success Metrics 
- Alarms triggered when health metrics fail 
- Immutable deployment in terraform 

### Difficulty 
- 2/5
    - For the basic setup 
- 3/5 
    - For simple notifications
- 4/5 
    - For fully tested notifications in CI 
- 5/5
    - For integrations with identity management we want to restrict access to everything based on an authenticated identity and authorization provided via RBAC. This will make things harder. 
