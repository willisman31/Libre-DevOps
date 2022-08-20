# Microservices Explained - the What, Why and How?

## Monolith and its downsides

 - monolith = all app components are part of a single unit
   - "all in one" codebase
 - development, deployment, and scaling done in terms of this single unit
 - only 1 tech stack can be used
 - different teams working on the same monolith must carefully coordinate with each other so they don't step on each others work
 - 1 artifact must be deployed all at once
 - traditional means of building an app

## Challenges of monolithic architecture

 - app is too large and complex
 - who app must be scaled at once even if only part of the app needs scaling
 - parts are more likely to become entangled
 - only one dependency version for entire app
 - longer release process
 - whenever the app is release the ENTIRE app must be:
   1. tested
   2. built and deployed
   3. freed from any fatal bugs in any part of the app

## What are Microservices?

 - split monolith into several small independent services
 - questions to consider:
   - how do we break down the existing monolith?
   - where does the existing code go in the new microservices?
   - how many services should be created?
   - how big should these services be?
   - how will these services interact/communicate with each other?
 - break up monolith into services based on **BUSINESS FUNCTIONALITIES**
 - each service does exactly ONE job
   - 1 service - 1 job
 - each microservice should be self-contained and independent of one another
   - they should all be able to be developed, deployed, and scaled separately = loose coupling
   - each microservice has its own version

## How Do Microservices Communicate with Each Other?

 - communication via API calls - each service has its own API
   - services often use HTTP requests for synchronous communication
 - communication can be done via Message Broker
   - service sends message to Message Broker, Broker sends message to target service
 - Communication via service mesh
   - very popular with K8s deployments
 - delegation of communication is what allows different tech stacks and teams to be used for each service

## Downsides of Microservices

 - added complexity of moving to a distributed system
   - communication configurations
   - monitoring of multiple services/instances

### Tools being developed to help ease use of microservices

 - Kubernetes (K8s) - most popular option
 - Hashicorp (paid endorsement)

## CI/CD Pipeline for Microservices

 - strong pipelines allow for fast/frequent updates with no downtime
 - having more microservices means that better pipelines are more important
   - no point in distributing the work for creating an application if all teams have to go through the same lengthy build process as before

## Monorepo vs Polyrepo - How to manage code for microservices

 - monolith always gets monorepo (single repository)
   - all application code in one place (this is always going to make sense when all that code is getting deployed together)
 - microservices can have either a monorepo or polyrepo (multiple repositories)
  - how to structure multiple services within a single repo?
    - use folders - directory for each service/project
    - simple to manage and share code and track changes
    - easy to break the rules and more tightly couple code; git interactions become very slow; additional challenges in the build process
  - polyrepos allow code to be completely isolated
    - teams can still look at each others code when needed
    - microservices can also have repos "grouped" for easy management
    - straightforward pipelines - no extra logic needed
    - broad application changes are more difficult
    - searching, testing, and debugging is a challenge for certain features/bugs
    

