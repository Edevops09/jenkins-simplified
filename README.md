

## What is Jenkins?
* **Jenkins** is an open-source Continuous Integration server written in Java for orchestrating a chain of actions to achieve the Continuous Integration process in an automated fashion.
* Jenkins supports the complete development life cycle of software from building, testing, documenting the software, deploying, and other stages of the software development life cycle.


## What is Continuous Integration?
* Continuous Integration is a process of integrating code changes from multiple developers in a single project many times. The software is tested immediately after a code commit. 
* With each code commit, code is built and tested. If the test is passed, the build is tested for deployment. If the deployment is successful, the code is pushed to production.
* This commit, build, test, and deploy is a continuous process and hence the name continuous integration/deployment.

## How does Jenkins work?
Jenkins is a server-based application and requires a web server like Apache Tomcat to run on various platforms like Windows, Linux, macOS, Unix, etc. To use Jenkins, you need to create pipelines which are a series of steps that a Jenkins server will take. 

Jenkins Continuous Integration Pipeline is a powerful instrument that consists of a set of tools designed to host, monitor, compile and test code, or code changes, like:

```
Continuous Integration Server (Jenkins, Bamboo, CruiseControl, TeamCity, and others)
Source Control Tool (e.g., CVS, SVN, GIT, Mercurial, Perforce, ClearCase and others)
Build tool (Make, ANT, Maven, Ivy, Gradle, and others)
Automation testing framework (Selenium, Appium, TestComplete, UFT, and others) 
```

## Advantages of using Jenkins
* Jenkins is being managed by the community which is very open. Every month, they hold public meetings and take inputs from the public for the development of Jenkins project.
* So far around 280 tickets are closed, and the project publishes stable release every three months.
As technology grows, so does Jenkins. So far Jenkins has around 320 plugins published in its plugins database. With plugins, Jenkins becomes even more powerful and feature rich.
* Jenkins tool also supports cloud-based architecture so that you can deploy Jenkins in cloud-based platforms.
The reason why Jenkins became popular is that it was created by a developer for developers.

## Disadvantages of using Jenkins
* Though Jenkins is a very powerful tool, it has its flaws.
Its interface is out dated and not user friendly compared to current UI trends.
* Though Jenkins is loved by many developers, it’s not that easy to maintain it because Jenkins runs on a server and requires some skills as server administrator to monitor its activity.
* One of the reasons why many people don’t implement Jenkins is due to its difficulty in installing and configuring Jenkins.
* Continuous integrations regularly break due to some small setting changes. Continuous integration will be paused and therefore requires some developer attention.

## Modern Development Philosophies
The philosophies of modern development emphasize collaboration between different teams, flexibility in planning and development, and shorter development cycles. Three major philosophies are interrelated:
* **Agile** - emphasizes adaptive planning and evolutionary development. Work is planned and completed in "sprints" (usually 1-2 weeks of work), with frequent (usually daily) "scrums" where all team members report progress and plan their next steps. See the Agile Manifesto.
* **DevOps** - extends the Agile philosophy into operations and production by advocating for the automation and monitoring of all steps in the development cycle.  
* **Continuous** - implements Agile and Devops philosophies with tools that standardize the steps in the process and thoroughly test each code modification before it is integrated into the official source.

![image](https://user-images.githubusercontent.com/84156957/132910108-025bbdaa-605c-46b7-989e-47fa04ddde98.png)

## Continuous Integration, Continous Delivery, and Deployment
* **Continuous Integration (CI)** is the frequent, automatic integration of code. All new and modified code is automatically tested with the master code.
* **Continuous Delivery (CD)** is the natural extension of CI. It ensures that the code is always ready to be deployed, although manual approval is required to actually deploy the software to production.
* **Continuous Deployment** automatically deploys all validated changes to production. Frequent feedback enables issues to be found and fixed quickly.
* To successfully implement **continuous delivery**, it is essential to have a collaborative working relationship with everyone involved. You can then use Delivery Pipelines, which are automated implementations of your product’s lifecycle.

  ![image](https://user-images.githubusercontent.com/84156957/132910774-acedcd9b-0717-4bfc-bf56-15b17eff4ecd.png)

## Jenkins Workflow
Jenkins automatically performs all the activities required to deliver your software. You specify how to build and test your software as well as when, where, and how to deploy it using these guidelines:
* Define a Jenkins Pipeline to run each activity in the same order every time.
*  Pipeline is glue for the activities defined. Do not code build actions directly in the Pipeline! Instead, use shell scripts or a tool such as Apache Maven, Gradle, npm, Apache Ant, or make to define the specific actions required at each step and use the pipeline to define the execution order.
* The pipeline runs each time the code is modified.

## Jenkins Installation
**Installation on Centos 7** 

```
Step 1: Install Jenkins Repository
sudo yum install wget -y
sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo

Step 2: Install epel-release 
sudo yum install epel-release -y
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key

Step 3: Install Java
sudo yum install jenkins java-1.8.0-openjdk-devel -y

Step 4: Verify installtion and start Jenkins
sudo systemctl start jenkins
sudo systemctl enable jenkins

Step 5: Once Jenkins is up and running, access it from the link:
http://localhost:8080
```
**Installation on Ubuntu**
```
Step 1: Install Java
$ sudo apt update
$ sudo apt install openjdk-8-jdk

Step 2: Add Jenkins Repository
$ wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key
| sudo apt-key add –

Step 3: Add Jenkins repo to the system
$ sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable
binary/ > /etc/apt/sources.list.d/jenkins.list’

Step 4: Install Jenkins
$ sudo apt update
$ sudo apt install Jenkins

Step 5: Verify installation
$ systemctl status Jenkins

Step 6: Once Jenkins is up and running, access it from the
link:
http://localhost:8080
```

**To get Initial Admin Password**
```
cat /var/lib/jenkins/secrets/initialAdminPassword
```

**Default Jenkins configuration folder**
```
/var/lib/jenkins
```

## Different Types of Jenkins Jobs
Jenkins provides the option of choosing from different types of jobs to build your project.
* **Freestyle** - build jobs are general-purpose build jobs, which provides maximum flexibility. It can be used for any type of project.
* **Pipeline** - This project runs the entire software development workflow as code. Instead of creating several jobs for each stage of software
development, you can now run the entire workflow as one code.
* **Multiconfiguration** - The multiconfiguration project allows you to run the same build job on different environments. It is used for testing an application in
different environments.
* **Folder** - This project allows users to create folders to organize and categorize similar jobs in one folder or sub folder.
* **GitHub Organization** - This project scans your entire GitHub organization and creates Pipeline jobs for each repository containing a Jenkinsfile
* **Multibranch Pipeline** - This project type lets you implement different Jenkinsfiles for different branches of the same project.

## Jenkins Pipeline
Jenkins pipeline is a single platform that runs the entire
pipeline as code. Instead of building several jobs for each phase, you can now code the entire workflow and put it in a Jenkinsfile. 

Jenkinsfile is a text file that stores the pipeline
as code. It is written using the Groovy DSL. It can be written based on two syntaxes:
* **Scripted pipeline:** Code is written on the Jenkins UI
instance and is enclosed within the node block.
```groovy
node {
scripted pipeline code
}
```
* **Declarative pipeline:** Code is written locally in a file and is checked into a SCM and is enclosed within the
pipeline block.
```groovy
node {
declarative pipeline code
}
```

## Jenkins Pipeline Syntax Example
```groovy
node {
stage(‘SCM Checkout’) {
//Checkout from your SCM(Source Control Management)
//For eg: Git Checkout
}
stage(‘Build’) {
//Compile code
//Install dependencies
//Perform Unit Test, Integration Test
}
stage(‘Test’) {
//Resolve test server dependencies
//Perform UAT
}
stage(‘Deploy’) {
//Deploy code to prod server
//Solve dependency issues
}
}
```

## Jenkinsfile
Jenkins Pipeline can be defined by a text file called JenkinsFile. You can implement pipeline as code using JenkinsFile, and this can be defined by using a DSL (Domain Specific Language). With the help of JenkinsFile, you can write the steps required for running a Jenkins Pipeline.
* **Pipeline:** This is the user-defined block, which contains all the processes such as build, test, deploy, etc. it is a group of all the stages in a JenkinsFile. All the stages and steps are defined in this block. It is used in declarative pipeline syntax.
* **Stage:** This block contains a series of steps in a pipeline. i.e., build, test, and deploy processes all come together in a stage. Generally, a stage block visualizes the Jenkins pipeline process.

## Jenkins Snippet Generator
```
Step 1: Create a pipeline job > configure
Step 2: Select pipeline script from pipeline definition
Step 3: Click on Pipeline syntax > snippet generator
Step 4: Step > select Git > enter repo URL
Step 5: Scroll down > Generate pipeline script
Step 6: Copy the script into your pipeline script UI
```

