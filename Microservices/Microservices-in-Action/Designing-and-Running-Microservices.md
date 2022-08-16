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




