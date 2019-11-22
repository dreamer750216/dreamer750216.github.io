---
layout: post
title:  "[Jenkins] setup google oauth"
categories: Programmer
tags: Jenkins
author: DreAmeR
description: setup google oauth on AWS EC2
---

###  **1. Install jenkins plugin**
>
manage Jenkins  
pluginManager  
install"Google Login"  

###  **2. Setup Google APIs**
>
go to [Google APIs][google-apis]  
go to OAuth consent screen  
setup Authorized domains ex.xxxxxx.ddns.net  
go to credentials  
setup Authorized redirect URIs ex.http://xxxxxxx:8080/securityRealm/finishLogin  

###  **3. Setup google login plugin**
>
manage Jenkins  
configureSecurity 
Login with Google  
setup "Client Id" & "Client Secret"  

[google-apis]: https://console.developers.google.com/apis/dashboard?authuser=0&project=plucky-hue-224009
