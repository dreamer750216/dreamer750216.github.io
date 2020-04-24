---
layout: post
title:  "import issue via REST API"
categories: JIRA
author: DreAmeR
description: import issue via REST API
---

>
require 'rest-client'  
require 'json'  
>
payload =  
{  
  &nbsp;&nbsp;"fields": {  
    &nbsp;&nbsp;&nbsp;&nbsp;"project":{"key": "<font color=red >project_key</font>"},  
    &nbsp;&nbsp;&nbsp;&nbsp;"issuetype": {"name": "<font color=red >Bug</font>"},  
    &nbsp;&nbsp;&nbsp;&nbsp;"summary": <font color=red >summary</font>,  
    &nbsp;&nbsp;&nbsp;&nbsp;"description": <font color=red >description</font>,  
    &nbsp;&nbsp;&nbsp;&nbsp;"components": [{"<font color=red >name": comp</font>}],  
    &nbsp;&nbsp;&nbsp;&nbsp;"reporter": {  
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"name": "<font color=red >jira_user</font>"  
    &nbsp;&nbsp;&nbsp;&nbsp;}  
  &nbsp;&nbsp;}  
}  
>
response = RestClient.post "https://<font color=red >jira_server</font>/rest/api/2/issue", payload.to_json, headers  
puts response  

