## Table of Contents
- [What is Jenkins?](#what-is-jenkins-)
- [What is Continuous Integration?](#what-is-continuous-integration-)
- [How does Jenkins work?](#how-does-jenkins-work-)
- [Advantages of using Jenkins](#advantages-of-using-jenkins)
- [Disadvantages of using Jenkins](#disadvantages-of-using-jenkins)
- [Modern Development Philosophies](#modern-development-philosophies)
- [Continuous Integration, Continous Delivery, and Deployment](#continuous-integration--continous-delivery--and-deployment)
- [Jenkins Workflow](#jenkins-workflow)
- [Jenkins Installation](#jenkins-installation)
- [Different Types of Jenkins Jobs](#different-types-of-jenkins-jobs)
- [Jenkins Pipeline](#jenkins-pipeline)
- [Jenkins Pipeline Syntax Example](#jenkins-pipeline-syntax-example)
- [Jenkinsfile](#jenkinsfile)
- [Jenkins Snippet Generator](#jenkins-snippet-generator)
- [Distributed Jenkins components](#distributed-jenkins-components)
- [Jenkins Architecture](#jenkins-architecture)
  * [Jenkins Master](#jenkins-master)
  * [Jenkins Managed Nodes](#jenkins-managed-nodes)
- [Continous Integration and Continous Delivery Summary](#continous-integration-and-continous-delivery-summary)


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
* It is an open-source tool with great community support.
* It is easy to install, configure, extend, and modify. 
* It allows the instant generation of tests and building, automation, and deployment of code on different platforms.
* It has 1000+ plugins to ease your work. If a plugin does not exist, you can code it and share it with the community.
* It helps in detecting errors very early, thus saving developers a lot of time and hard work.
* It is built with Java and hence, it is portable to all the major platforms.

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

## Distributed Jenkins components
* **The Jenkins controller** is the Jenkins service itself, which is a webserver that also acts as a "brain" for deciding how, when, and where to run tasks. 
	• It is a webserver that also acts as a "brain" for deciding how, when and where to run tasks. Management tasks (configuration, authorization, and authentication) are executed on the controller, which serves HTTP requests. Files written when a Pipeline executes are written to the filesystem on the controller unless they are off-loaded to an artifact repository such as Nexus or Artifactory.
	
* **A node** is a server where Jenkins runs build jobs on executors. Note that the Jenkins controller also runs on a node. Nodes are the "machines" on which build agents run. Jenkins monitors each attached node for disk space, free temp space, free swap, clock time/sync and response time. A node is taken offline if any of these values go outside the configured threshold
	
* **An executor** is effectively a thread for execution of tasks. An executor is a slot for execution of tasks; effectively, it is a thread in the agent. The number of executors on a node defines the number of concurrent tasks that can be executed on that node at one time. In other words, the number of concurrent Pipeline stages that can execute on that node at one time.
	
* **The agent** is the tool that manages the executors on a remote node, on behalf of Jenkins. They are actually small (170KB single jar) Java client processes that connect to a Jenkins controller and are assumed to be unreliable. An agent can use any operating system that supports Java. Tools required for builds and tests are installed on the node where the agent runs; they can be installed directly or in a container (Docker or Kubernetes). Each agent is effectively a process with its own PID (Process Identifier) on the host machine

## Jenkins Architecture
Jenkins follows Master-Slave architecture to manage distributed builds. In this architecture, slave and master communicate through TCP/IP protocol.
Jenkins architecture has two components:
* Jenkins Master/Server
* Jenkins Slave/Node/Build Server

![jenkins-architecture](https://user-images.githubusercontent.com/84156957/132950212-e67cf3f9-75d8-4f04-b97a-4e7498e4a90e.jpg)

### Jenkins Master
The main server of Jenkins is the Jenkins Master or Controller. It is a web dashboard which is nothing but powered from a war file. By default it runs on 8080 port. With the help of Dashboard, we can configure the jobs/projects but the build takes place in Nodes/Slave. By default one node (slave) is configured and running in Jenkins server. We can add more nodes using IP address, user name and password using the ssh, jnlp or webstart methods.

The server's job or master's job is to handle:
* Scheduling build jobs.
* Dispatching builds to the nodes/slaves for the actual execution.
* Monitor the nodes/slaves (possibly taking them online and offline as required).
* Recording and presenting the build results.
* A Master/Server instance of Jenkins can also execute build jobs directly.

### Jenkins Managed Nodes
Jenkins slave is used to execute the build jobs dispatched by the master. We can configure a project to always run on a particular slave machine, or particular type of slave machine, or simple let the Jenkins to pick the next available slave/node.

As we know Jenkins is developed using Java is platform independent thus Jenkins Master/Servers and Slave/nodes can be configured in any servers including Linux, Windows, and Mac.

![jenkins-architecture2](https://user-images.githubusercontent.com/84156957/132950258-2eca0160-fa5a-41b4-b0d1-7612dd850327.png)

## Continous Integration and Continous Delivery Summary
* A CI/CD pipeline automates the process of software delivery.
* CI/CD pipeline introduces automation and continuous monitoring throughout the lifecycle of a software product.
* Continuous integration is a software development method where members of the team can integrate their work at least once a day.
* Continuous delivery is a software engineering method in which a team develops software products in a short cycle.
* Continuous deployment is a software engineering process in which product functionalities are delivered using automatic deployment.
* There are four stages of a CI/CD pipeline 1) Source Stage, 2) Build Stage, 3) Test Stage, 4) Deploy Stage.
* Important CI/CD tools are Jenkins, Bambo, and Circle CI.
* CI/CD pipeline can improve reliability.
* CI/CD pipeline makes IT team more attractive to developers.
* Cycle time is the time taken to go from the build stage to production.
* Development frequency allows you to analyze bottlenecks you find during automation.
* Change Lead Time measures the start time of the development phase to deployment.
* Change Failure Rate focuses on the number of times development get succeeds vs. the number of times it fails. 
* MTTR (Mean Time to Recovery) is the amount of time required by your team to recover from failure.
* MTTF (Mean Time to Failure) measures the amount of time between fixes and outages.
	

