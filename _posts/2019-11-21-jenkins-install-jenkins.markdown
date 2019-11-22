---
layout: post
title:  "[Jenkins] install jenkins"
categories: Programmer
tags: Jenkins
author: DreAmeR
description: install jenkins on AWS EC2
---

###  **1. Install JAVA**
>
sudo add-apt-repository ppa:openjdk-r/ppa  
sudo apt-get update  
sudo apt-get install openjdk-11-jdk  


###  **2. Install Jenkins**
>
wget -q -O - https://jenkins-ci.org/debian/jenkins-ci.org.key | sudo apt-key add -  
sudo sh -c 'echo deb http://pkg.jenkins-ci.org/debian binary/ > /etc/apt/sources.list.d/jenkins.list'  
sudo apt-get update  
sudo apt-get install jenkins  

###  **3. Change jenkins port**
>
sudo vim /etc/default/jenkins  
set JENKINS_PORT=8081  

###  **4. Auto start jenkins on startup**
>
sudo systemctl enable jenkins  

###  **5. Restart jenkins**
>
sudo service jenkins restart  

<br/>
#### Thanks：
> 
[jenkins][jenkins]  

[jenkins]: https://jenkins.io
