----------------------------------------
Resume Application
----------------------------------------
Description: A full stack engineering project to serve as a demonstration 
of my knowledge of PHP, DevOps, AWS, Containerization/Orchestration and 
creation and usage of microservices.

React Application front end container running nginx. 
Traffic load balanced between different Kubernetes nodes.

Backend would be a Laravel Application to serve requests to the React Application
via JSON responses constructed from MySQL models to store data. 

Implement caching layer between React and the backend so React application makes less calls.

Allow adding new data via JSON post requests with authentication to RDS instance.

Create Jenkins host for Continuous Integration and Continuous Deployment. 

Create Tests to ensure the React application functions.
Create Tests to ensure Laravel api is returning correct responses.

----------------------------------------
Architecture
----------------------------------------
    React Frontend
----------------------------------------
    Serve from S3 bucket since it'll be all Javascript?
    - Pros:

    - Cons:

    Serve via separate NGINX container than the API?
    - Pros:

    - Cons:
----------------------------------------
    API
----------------------------------------
    Routes/Models /api/v0
        - /about - only 1 database entry. use PATCH request for updating information.
            id
            name
            email
            phone number
            github
            linkedin
        - /experience - order  by most recent date / current at top
            id
            company
            position
            join_date
            left_date
            description
        - /education - order by most recent / current studies
            id
            school 
            join_date
            left_date
            description
        - /goals - 
            id
            goal_name
            goal_description

    Docker Containers
        NGINX - Cache JSON requests & Pass requests for api to php-fpm
        PHP-FPM - Process the PHP and talk to MySQL Backend

    Speaks to Backend MySQL 5.7 RDS Instance
----------------------------------------
    CI/CD Integration
----------------------------------------
    Jenkins

    CodeDeploy

    CodeShip