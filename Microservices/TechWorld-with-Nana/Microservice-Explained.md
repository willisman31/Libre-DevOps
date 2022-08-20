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
 - 

