## Jenkins Pipelines on AWS
In this project, an instance was created and ran on AWS, Jenkins was installed and configured, and a pipeline created to deploy a static website on S3.

### Getting Started
This project is a hands on practice on Jenkins pipelines on AWS. 

### Deployment - Steps taken to execute the project
#### 1. Set up IAM credentials.
A new IAM user created with EC2 and S3 access, this user is not the root or admin user in AWS. 

#### 2. Launch EC2 instance.
An Ubuntu 18.04 t2.micro is launched and can be accessed via SSH using the PEM file. 

#### 3. Jenkins is installed and running
Jenkins (an automation server that supports building, deploying and automating projects) was installed via SSH. The Jenkins instance can be reached over HTTP publicly.

#### 4. ‘Blue Ocean’ is enabled
Blue Ocean is one of the plugins available on Jenkins, it is a visual pipeline editor. Blue Ocean was installed, the link shows in the sidebar and loads its interface. It is completely different from the standard Jenkins. 

#### 5. Barebones Pipeline is added
A GitHub repository is added and shows in the BlueOcean dashboard, it automatically recognizes the Jenkinsfile, an initial pipeline is set up with 1 stage. 

#### 6. Publishes the static site to S3
The set up in 5 publishes an index.html file to the right bucket in the right region, and the url is accessible via HTTP from anywhere. 

#### 7. Linter catches issues with HTML
A linter is added to the Jenkins server, the linter catches HTML problems with the sample index.html, after addressing the problems with the html, the job builds and publishes the contents once again.

#### 8. Jenkinsfile is demonstrated
A Jenkinsfile is provided, it has the stages and steps defined that match how the pipeline looks in the Jenkins dashboard. ‘stage(‘Lint HTML’)’ shows as ‘Lint HTML’ in the pipeline. The AWS credentials and bucket name are all mapped to an existing S3 bucket that is publicly accessible and it displays the contents of the index.html file. 

A screenshot showing the result of steps 1-8 provided below

### Files included
Screenshot-01.jpg - The IAM AWS console with the permissions being created and unique AWS URL 

Screenshot-02.jpg - Showing the unique AWS URL of EC2 instance as captured

Screenshot-03.jpg - Showing the unique AWS url after Jenkins installation

Screenshot-04.jpg - Shows the sidebar with the Blue Ocean link (Blue Ocean plugin installation)

Screenshot-05.jpg - Shows the GitHub project as a pipeline

Screenshot-06.jpg - Setting up pipeline for AWS, shows "index.html" rendered with unique AWS url

Screenshot-07.jpg - Shows the failure when linting

Screenshot-08.jpg - Shows pipeline passing the linting stage and deploys to S3

gitHubRepo.txt    - A file containing link to GitHub Repo

### Requirements
AWS Account, IAM username and password, EC2 Key pair

An EC2 instance with Ubuntu 18.04  

Latest Jenkins installed on the EC2 instance

Blue Ocean plugin

"Tidy" linter

A personal GitHub repository

SSH Client

A basic knowledge of bash scripting

Basic programming skills

### Versioning
Git used for versioning. 

### Author
Folasade Adedeji

### Detailed direction for completing the project
[Detailed instruction for completing Jenkins pipelines on AWS](https://github.com/folasade/static/Jenkins-Pipelines-on-AWS.pdf)

### Acknowledgments
Hat tip to my family for giving me space to complete this project.
