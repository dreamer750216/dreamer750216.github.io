---
layout: post
title:  "[Jenkins] github trigger"
categories: Programmer
tags: Jenkins
author: DreAmeR
description: github trigger
---

###  **1. Setup on github**
>
Settings > developer settings > personal access token > create new
![License Badge]({{ site.baseurl }}/assets/images/2019-11-25-jenkins-github-trigger/1.jpg)
![License Badge]({{ site.baseurl }}/assets/images/2019-11-25-jenkins-github-trigger/2.jpg)

###  **2. Setup on repositories**
>
Repositories > setting > WebHooks&Services > add webhook
![License Badge]({{ site.baseurl }}/assets/images/2019-11-25-jenkins-github-trigger/3.jpg)

###  **3. Setup github trigger plugin**
>
Install github trigger plugin
Settings system > GitHub > Add GitHub Sever
Create credentials
![License Badge]({{ site.baseurl }}/assets/images/2019-11-25-jenkins-github-trigger/4.jpg)
![License Badge]({{ site.baseurl }}/assets/images/2019-11-25-jenkins-github-trigger/5.jpg)

###  **3. Jenkins job**
>
github trigger
![License Badge]({{ site.baseurl }}/assets/images/2019-11-25-jenkins-github-trigger/6.jpg)


<br/>
### Thanks：

1，[https://github.com/muyinchen/woker][https://github.com/muyinchen/woker]

[https://github.com/muyinchen/woker]: https://github.com/muyinchen/woker

