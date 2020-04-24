---
layout: post
title:  "nextcloud usage"
categories: Nextcloud
author: DreAmeR
description: nextcloud usage
---

>
require 'nextcloud'  
require 'net/ftp'  
>
nextcloud = Nextcloud.new(url: "http://file_server", username: "username",  password: "password")  
@webdav = nextcloud.webdav  
>
@webdav.directory.find(nextcloud_folder).instance_of?(Nextcloud::Models::Directory)  
@webdav.directory.create(nextcloud_folder)  
nextcloud_file_size = @webdav.directory.find(nextcloud_file).size.to_s  
