---
layout: post
title:  "[Gerrit] setup google oauth"
categories: Programmer
tags: Gerrit
author: DreAmeR
description: setup google oauth on AWS EC2
---

###  **1. Setup Google APIs**
>
go to [Google APIs][google-apis]  
go to OAuth consent screen  
setup Authorized domains ex.xxxxxx.ddns.net  
go to credentials  
setup Authorized redirect URIs ex.http://xxxxxxx:8080/oauth  

###  **2. Setup google login plugin**
>
download [gerrit-oauth-provider.jar][gettir-google-oauth-link]  
puts gerrit-oauth-provider.jar to $gerrit_site/plugin  
export GERRIT_SITE=~/gerrit_site  
java -jar gerrit*.war init -d $GERRIT_SITE  


[google-apis]: https://console.developers.google.com/apis/dashboard?authuser=0&project=plucky-hue-224009
[gettir-google-oauth-link]: https://github.com/davido/gerrit-oauth-provider/releases/download/v3.0.0/gerrit-oauth-provider.jar

