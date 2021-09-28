<h2> Multicontainer Docker Deployment to AWS </h2>
Multicontainer setup and AWS deployment(project complex for Fibonacci calculation) :

1. Push code to github
2. travis automaticallys pulls repo
3. Travis builds a test image, test code
4. Travis builds prod images
5. Travis pushes project to AWS Elastci beanstalk
6. EB pulls image from Docker hub, deploy

The Beanstalk doesn't know how to run containers so it delegates the task to amazon ECS(Elastic container service)

There should be a  single docker-compose.yml file on project level and each module should contain specific Dockerfile

The Dockerfile.dev and docker-compose-dev.yml are for dev environment. They will not be honoured by AWS.

<h3>AWS Configuration Cheat Sheet - Updated for new UI</h3>
https://tm.udemy.com/course/docker-and-kubernetes-the-complete-guide/learn/lecture/21321244#overview

We generally don't deploy / host our own copy of RDS(postgress in this case) or redis cache, but we rather rely on AWS Elastic cache for redis and AWS Relational database service for Postgress

* When creating our Elastic Beanstalk environment we need to select Docker running on 64bit Amazon Linux 2

