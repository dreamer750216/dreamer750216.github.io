---
layout: post
title:  "add version via REST API"
categories: JIRA
author: DreAmeR
description: Add version via REST API
---

>
require 'rest-client'  
require 'json'  
>
payload = {  
   &nbsp;&nbsp;"name": "<font color=red >new version</font>",  
   &nbsp;&nbsp;"project": "<font color=red >project_key</font>"  
}  
headers = {  
  &nbsp;&nbsp;"Content-Type": "application/json"  
}
response = RestClient.post "https://<font color=red >jira_server</font>/rest/api/2/version", payload.to_json, headers  
puts response  


