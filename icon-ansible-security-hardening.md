
# ICON Blockchain Ansible Security Hardening

### Business case idea

Running blockchain validator nodes is like running a bank. You need to take the all precautions possible to make sure your nodes are not only running with as many 9's of uptime but also that your node itself can't be hacked.  If a malicious actor found an exploit in a common configuration, they can comprimise the entire network. To mitigate this, we need to run a suit of hardening steps on our application and run our validator node in the most stable / secure configuration possible directly on the VM. 

### Challenge

- We need to first run a suite of andsible hardening steps on each VM as part of the bootstrapping process. We then need to do a quick audit and track exactly what we are doing.  
- Then we need to take apart a docker container and turn it into an ansible playbook as we don't want to run that app on a container.
    - This might get pushback initially but I think it is a good long term goal to run the application as close to metal as possible, ideally in a tier 4 data center with dedicated HSM.
- Configure bastion to connect to IdP 
    - gravitational's teleport or rolling own
- Setup P2P network configs and build agent to update the firewall
    - This gets into it but if you are here, your project will start looking really good
- Build CI to run tests
    - Tests written early, CI later 

### Tools

- Ansible 
- Terraform + terragrunt 
    - All your ansible will be folded into this repo.  Don't worry, Rob will help 
- Pen / Load tests
    - Find a few good packages to run a few tests around 
- terratest / test kitchen / python 
    - Whatever works 

### Success Metrics
- Node that shown to be more resiliant based on some metrics like you run nmap and nothing is open and you ran a pen testing package and you failed, then you passed

### Difficulty
- 2/5 
    - Basic ansible hardening in terraform 
- 3/5 
    - Get a few features together 
- 4/5 
    - Run suite of tests  
- 5/5 
    - Fiugure out a P2P networking challenge we have 

### Resources 
- [ansible-os-hardening](https://github.com/dev-sec/ansible-os-hardening)   
    - We need to dive into exactly what is done here
- [Certus One](https://kb.certus.one/security.html)
    - This is how professionals operate