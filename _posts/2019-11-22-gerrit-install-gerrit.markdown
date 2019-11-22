---
layout: post
title:  "[Gerrit] install gerrit"
categories: Programmer
tags: Gerrit
author: DreAmeR
description: install gerrit on AWS EC2
---

###  **1. Install JAVA**
>
sudo add-apt-repository ppa:openjdk-r/ppa  
sudo apt-get update  
sudo apt-get install openjdk-11-jdk  

###  **2. Install gerrit**
>
download [Gerrit 3.1.0][gerrit-link]  
export GERRIT_SITE=~/gerrit_site  
java -jar gerrit*.war init --batch --dev -d $GERRIT_SITE  


###  **2. Edit gerrit.config**
>
vim ../gerrit_site/etc/gerrit.config  
canonicalWebUrl = http://YOUR_DOMAIN:8081/  
listenUrl = http://*:8081  

###  **4. Restart gerrit**
>
$GERRIT_SITE/bin/gerrit.sh restart

<br/>
#### Thanks：
> 
[gerrit][gerrit]  

[gerrit]: https://gerrit-review.googlesource.com/Documentation/linux-quickstart.html
[gerrit-link]: https://gerrit-releases.storage.googleapis.com/gerrit-3.1.0.war
