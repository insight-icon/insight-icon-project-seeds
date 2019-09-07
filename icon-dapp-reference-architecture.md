
# ICON Blockchain Distributed Application Reference Architecture 

### Business case idea
One of the ICON Blockchain's best strengths is in their flexible SDK that allows developers to easily build distributed applications that work on the chain.  To run those applications, developers need to have a baseline [reference architecture](https://en.wikipedia.org/wiki/Reference_architecture) so that they can easily go from concept to reality in as little time as possible.  This project concerns itself with building the most generalized baseline that each developer will need to get a simple application running on chain with the appropriate boilerplate that will run a simple app.  We will be canvassing the community to get a little guidance of what they need but we can start with a simple 3 tier app and then break out on and off-chain components and make it modular so users can reassemble it.  Last we can set that up in a code generator like [cookiecutter](https://github.com/cookiecutter/cookiecutter) allowing users to generate that stack with customizations similar [to what Rob did](https://github.com/robc-io/cookiecutter-terragrunt-aws-icon) during his fellowship.    

### Challenge
- First we'll need to canvass the community to find out some specs and possibly get someone's actual application to run 
- We'll then need to do some ringfencing of different components to make sure the reference architecture fits into a production style deployment
    - We will NOT be considering how to run it in production as an afterthought 
- We'll then think about the different styles of applications that we can accomodate for
    - One of our Decentralized Consensus Insight fellows is building an app that has an NFT component and would be great to support that 
- Would be awesome if we could get a kafka cluster going and build a few little microservices subscribing to a couple topics
    - You won't be able to get the app going but you will be able to do some basic microservices and we'll find a couple very doable ones. 

### Tools
- terraform + terragrunt 
    - You will replicate the pattern that we are already using [here](https://github.com/robc-io/terragrunt-icon-insight-p-rep)
- Simple 3 tier application 
    - You can find one from a former Insight project 
    - Best if sourced from ICON community 
- Kafka microservice sweet goodness
    - We should have something simple running that we can iterate on with the community that shows how to run Microservices 

### Success Metrics
- `one-click`
- Testing done in CI for application 
    - terratest / test kitchen / python 
- You know you did a good job if anyone shows that they want to use it.  I don't think it will be hard to get a couple users but the [rule of three](https://en.wikipedia.org/wiki/Rule_of_three_(computer_programming)) is at play


### Difficulty
- 2/5 Simple application running 
    - The basics 
- 3/5 Clean application running 
    - Make the layout DRY and really think about how the application will grow putting in space for things like IAM and IdPs
- 4/5 Build a code generator and logic behind that 
    - No logic will be super simple - Rob will help 
- 5/5 Kafka microservices 
    - This will make a lot of people very happy 

### Resources 
- [terragrunt-reference-architecture](https://github.com/antonbabenko/terragrunt-reference-architecture/issues/1)