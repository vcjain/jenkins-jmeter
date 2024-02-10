# Jmeter integration with Jenkins

## Pre-requistic
- Java 17
- Install plugin Performance (Type Jmeter in Avaiable plugin search box)
----
## Steps to Install Jmeter on Ubuntu 22.x

To run jmeter from jenkins, we need to have jmeter installed on the machine on which Jenkins Job will execute. 

Below are the steps to install jmeter.
```shell
- wget https://dlcdn.apache.org//jmeter/binaries/apache-jmeter-5.5.zip
- sudo apt install unzip
- unzip apache-jmeter-5.5.zip
- mv apache-jmeter-5.5 jmeter
```
Update the executable path of jmeter
```shell
- sudo mv jmeter /opt
- echo 'export PATH="$PATH:/opt/jmeter/bin"' >> ~/.bashrc
- source ~/.bashrc
- Jmeter
```
----

## How to create Test Plan

The above command jmeter will not be run successfull, as jmeter is a desktop application hence if you have GUI on 
linux then you will be able to setup test script in jmeter. 

To avoid below steps and for quick practice, a sample testplan simplilearn.jmx file is added in the repository. This file
can used to run jmeter and publish performance result in jenkins.

To create a script in Jmeter, please refer 
```
- Create a Test plan, provide some appropriate name
- Right click on Test plan in left menu --> Add -> Threads (users) --> Thread Group
- - Add Number of threads as 5 or any your preferred number
  - Loop Count, set to 2
  - Keep other as default 

### Add Http Request for testing
  - Right click on Thread Group --> Add --> Sampler --> HTTP request
	- Add www.simplilearn.com in Server
	- Add the path to different pages in the website simplilearn.com like http://www.simplilearn.com/resources
	- Add multiple requests for different pages in the website, following above 2 steps.

### Setting the results viewer 
	- Right click on Thread Group --> Add --> Listener --> View results in Table
	- Save the test plan
```

