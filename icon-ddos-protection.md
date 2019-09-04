
# ICON Blockchain DDoS Protection 
This project aims to build in DDoS (distributed denial of service) protection on P-Rep and Citizen nodes for the ICON Blockchain with reveres proxies running in a cluster of spot instances in an autoscaling group.  

### Business case idea
Nodes for ICON are major targets for DDoS attacks as there is a direct monitary incentive to taking down the network and exploiting an arbitrage in price during attacks.  The best way to protect these nodes is to run a cluster of reverse proxies to handle each session and limit excessive usage by throttling requests as well as restricting useage from a whitelisted set of IPs. Building in this feature will greatly enhance the survavability of the network when it is attacked. 

### Challenge
- Autoscaling groups on all nginx instances (containers?) hooked up and tested against appropriate metrics 
- Reverse pro

### Tools
- terraform 
- docker / docker-compose / kubernetes (multiple options)
- nginx or another reverse proxy (ie Envoy)

### Success Metrics
- Successful deployment of sentry nodes communicating to ICON nodes 
- Tests to show connectivity during deployment and as a health check 
- Load testing to validate network integrity

### Difficulty
- 3/5 
    - Just using nginx will be the easier route
- 4/5 
    - Getting all the health checks to align properly with autoscaling policies  
- 5/5 
    - If using envoy this might be very difficult

### Resources 

- []

