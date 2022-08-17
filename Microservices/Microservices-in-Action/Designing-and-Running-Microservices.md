# Designing and Running Microservices

## What is a microservice application?

 - microservice application = collection of autonomous services
   - each service does exactly ONE thing
   - combinations of microservices create complex systems/applications
 - each microservice should be highly cohesive and almost completely decoupled
   - cohesion = degree to which elements are combined
   - coupled = how much one element knows about another
 - microservices are responsible for a single system capability
 - each microservice owns its own data- data should only be moved as the result of calling on the entire microservice
 - microservices should handle their interplay with each other- this should NOT fall on the messaging mechanism to orchestrate interactions
   - traditional development focuses on creating a service-oriented architecture (SOA) combined with enterprise service buses (ESB); however in these systems, the ESB tends to be enhanced over time to make up for the lack of development to the SOA
   - decoupling services puts the onus of development on the services rather than some orchestration subsystem
 - each microservice is independent of all other microservices in the system- that is, each microservice is a smaller monolithic application
   - monolithic application = one giant program that handles all system functionality
 - each microservice should be replaceable by any given service that performs the same function
   - this just further pushes the point that microservices are decoupled

### Scaling through decomposition

 - there are 3 dimensions of scaling:
   1. x-axis - duplication of deployments
   2. y-axis - scale by splitting and only duplicate the needed functions
   3. z-axis - sharding; not covered here, but can be done by monolithic applications and microservices alike
 - the goal is to minimize unused overhead

### Key principles

 1. Autonomy
 2. Resilience
 3. Transparency
 4. Automation
 5. Alignment

#### Autonomy

 - each service operates and changes independent of the others
 - microservices do not rely on implementation of other microservices
   - microservices interact through published interfaces, so one may be reliant on the function of another in order to perform its own function
 - independent deployment - if you rely on the precise implementation of another microservice, then you miss out on the benefits of microservices
 - autonomy is cultural - teams need to take ownership of their own microservices and delivering value with them

#### Resilience

 - deploying microservices allows system failures to be discovered and isolated very quickly
 - allows for gradual (continuous) releases that slowly introduce new functionality rather than making big risky steps every few months/years
 - potential points of failure do increase and architecture must be carefully designed to prevent cascading failures where many services rely on one unavailable service
   - careful, continuous monitoring and chaos engineering(?)

#### Transparency

 - behavior of the system depends on the behavior of all component microservices
 - diagnosing problems/failures requires insight into how 1+ component microservices function
 - each service should produce logs, metrics, and traces
   - making sense of the data is another problem for the business to solve

#### Automation

 - automation can help you manage added complexity of microservices by providing CONSISTENCY
   - in a well-designed system, the added complexity should be fairly minimal since microservices aren't meant to inherently change the system behavior
 - microservices tend to be best managed through an automated orchestration

#### Alignment

 - focus on leveraging microservices to further business goals
 - architecture (not just microservices) should always be furthering a business goal, otherwise it shouldn't be a business project

-----

 - horizontal decomposition in SOAs means that new functionality must be added into the system into a distributed manner, so that multiple components are being updated in order to add one new feature
 - microservices are the solution to this problem since new functionality is encapsulated within a single service, whether it's an entirely new service or an update to an outstanding one
   - when integrating functionality from a third party, it may make sense to create a separate microservice to handle that integration because it shields the rest of the architecture from uncertainty
 - you should always make sure that new versions maintain backwards compatibility so that services built on top of others aren't being toppled by updates

### Who uses microservices?

 - lots of well-known (technical) organizations have already implemented microservices into their architecture for some of the following reasons:
   - volume = amount of activity that a system performs has outpaced the original design/implementation
   - new features = new features may need a different technology in order to be implemented
   - engineering team growth = large teams are hard to manage, so breaking them up into smaller teams to focus on separate microservices can help with human management
   - technical debt = complexity from a large monolith having work done on it by many distributed individuals/teams tends to result in higher tech debt
   - international distribution = geographic distribution is easier to accomodate with microservices
 - microservices can be the original design choice or a later migration

### Why are microservices a good choice?










