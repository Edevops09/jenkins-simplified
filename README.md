

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

## Modern development philosophies
The philosophies of modern development emphasize collaboration between different teams, flexibility in planning and development, and shorter development cycles. Three major philosophies are interrelated:
* **Agile** - emphasizes adaptive planning and evolutionary development. Work is planned and completed in "sprints" (usually 1-2 weeks of work), with frequent (usually daily) "scrums" where all team members report progress and plan their next steps. See the Agile Manifesto.
* **DevOps** - extends the Agile philosophy into operations and production by advocating for the automation and monitoring of all steps in the development cycle.  
* **Continuous** - implements Agile and Devops philosophies with tools that standardize the steps in the process and thoroughly test each code modification before it is integrated into the official source.

![image](https://user-images.githubusercontent.com/84156957/132910108-025bbdaa-605c-46b7-989e-47fa04ddde98.png)

## Continuous integration, delivery, and deployment
* **Continuous Integration (CI)** is the frequent, automatic integration of code. All new and modified code is automatically tested with the master code.
* **Continuous Delivery (CD)** is the natural extension of CI. It ensures that the code is always ready to be deployed, although manual approval is required to actually deploy the software to production.
* **Continuous Deployment** automatically deploys all validated changes to production. Frequent feedback enables issues to be found and fixed quickly.

To successfully implement continuous delivery, it is essential to have a collaborative working relationship with everyone involved. You can then use Delivery Pipelines, which are automated implementations of your product’s lifecycle.
![image](https://user-images.githubusercontent.com/84156957/132910147-22b91a5a-22c9-488e-b49b-c20310cc5889.png)


