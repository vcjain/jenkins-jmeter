# Jmeter

## Steps to Install Jmeter on Ubuntu 22.x

- wget https://dlcdn.apache.org//jmeter/binaries/apache-jmeter-5.5.zip
- sudo apt install unzip
- unzip apache-jmeter-5.5.zip
- mv apache-jmeter-5.5 jmeter

- sudo mv jmeter /opt
- echo 'export PATH="$PATH:/opt/jmeter/bin"' >> ~/.bashrc
- source ~/.bashrc
- Jmeter

## How to create Test Plan
- CReate a Test plan
- Add ThreadPool, set to 5
- Add Loop, set to 2
- In ThreadPool, add HTTP request
- Set Lisiener --> Visible as Table result
-  
