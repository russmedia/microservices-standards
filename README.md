# Microservice standards recommendation
The group wide microservices standards recommendation.

The purpose of this repository is to gather all the requirements which enable cooperation between different teams and companies in development of microservices.


## I. General requirements:
0. Keep service small enough to stay focused.
1. Every microservice should have own repository with proper README file:
- the microservice purpose section
- installation steps/setup guide or provide setup script
- how to develop/contribute to it
- holding the documentation, e.g. also describes the fired events (and event data)
2. The application must be containerized, which means Dockefile must be included.
3. Applcation should expose health check i.e. `/health` endpoint.
4. If application is using database, cache or any other resources, they have to be exlusive per this service only.
5. Credentials and all configuration settings that are depending on the environment are always stored/received from environment variables. Samples should be included in the documentation.
6. If http API is exposed, swagger/open api spec documentation should be exposed with common url (e.g. /swagger or /doc)
7. Unit tests should be include, other type of tests depends of the type of the application.
8. Microservice should emit some events to nofity other systems about the actions/state changes.
9. Asychronous comunication is preffed than sychronous to avoid tight coupling of microservices. For asynchronous comunication `correlationID` should be included in all type of messages.
10. Required deployment files should be included i.e. terraform files or Kubernetes helm charts/yaml files.

## II. Language and frameworks
Although microservices do not have defined exact programming languages and frameworks, they should be developed in the technology which is appropriate to the problem it solves. The language also must be know in the group to enable other team/companies reviewing it.

Preferered languages:
1. node.js
2. php
3. Java or .NET

### III. Recommendations:
1. Usage of DBAL.
2. Prepare for scalability/stateless.
3. REST API.
4. Abstraction for logging.
5. docker-compose.yml with all depedencies i.e. database.
6. Abstraction for caching.

