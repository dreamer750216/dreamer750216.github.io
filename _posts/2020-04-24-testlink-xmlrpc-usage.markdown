---
layout: post
title:  "testlink usage"
categories: Testlink
author: DreAmeR
description: testlink usage
---

>
require 'xmlrpc/client'  
>
@server = XMLRPC::Client.new2( uri = 'http://testlink_server/testlink/lib/api/xmlrpc/v1/xmlrpc.php')  
@key = "testlink_key"  
>
def doesUserExist(user)  
&nbsp;&nbsp;args = {devKey: @key, user: user}  
&nbsp;&nbsp;r = @server.call('tl.doesUserExist', args)  
&nbsp;&nbsp;r  
end  


<br/>
#### Thanks：
> 
[testlink-code][testlink-code]  

[testlink-code]: https://github.com/TestLinkOpenSourceTRMS/testlink-code/blob/testlink_1_9/lib/api/xmlrpc/v1/xmlrpc.class.php
