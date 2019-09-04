# ICON Blockchain Pacemaker HA Deployment 

### Business case idea
ICON Blockchain needs to run validator nodes that need to stay on without disruption all the time.  These nodes also can't be run like a traditional web app due to the nature of blockchain signing technology and hence, to run the signing nodes in high availability (ie multiple zones with failover), one needs to run a tool called pacemaker to keep a virtual IP address that maintains addressability when a node fails.  

### Challenge
The main challenge will be immmutably setting up the nodes and doing integration testing to validate the setup.  For immutability you can assume that you will have easy to run terraform / terragrunt code to spin up the node, this is very simple. The challenge will be in writing ansible scripts that properly configure the node.  Once that is done, you will back track into secrets management and making the whole deployment secure. 

There are also various ways to run pacemaker.  Some validators use an Active / Active (AA) pattern whereby nodes with the fastest transaction time are awarded the signing.  There are also Active / Passive (AP) patterns that simply maintain a backup node in the event of failover.  This project should start the AP pattern and then consider the AA. 

### Tools
- terraform 
- ansible
    - called by terraform or simply using terraform null resource
- pacemaker 
- secrets management 

### Success Metrics
- Immutable deployment 

### Difficulty
This is probably the least difficult project 

