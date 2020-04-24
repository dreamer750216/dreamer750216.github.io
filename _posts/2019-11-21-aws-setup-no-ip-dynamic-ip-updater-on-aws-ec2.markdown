---
layout: post
title:  "setup no-ip dynamic ip updater on AWS EC2"
categories: AWS
author: DreAmeR
description: setup noip dynamic ip updater
---

Use [no-ip][no-ip], You can create an easy to remember hostname.

###  **1. Install no-ip dynamic Update Client (DUC)**
>
[download noip][no-ip-dl-link]  
sudo su  
cd /usr/local/src  
tar xzf noip-duc-linux.tar.gz  
cd no-ip-2.1.9  
apt-get update  
apt-get install -y build-essential  
apt-get install -y make  
make  
make install  

###  **2. no-ip run at startup**
>
Run sudo /usr/local/bin/noip2 -C to generate configuration file  
[download noip2.service][NathanGiesbrecht_link]  
Copy this file noip2.service to /etc/systemd/system/  
Execute `sudo systemctl daemon-reload`  
Execute `sudo systemctl enable noip2`  
Execute `sudo systemctl start noip2`  

<br/>
#### Thanks：
>
[noip.com][no-ip]  
[gist.github.com/NathanGiesbrecht][NathanGiesbrecht]  

[no-ip]: https://www.noip.com/
[no-ip-dl-link]: https://www.noip.com/client/linux/noip-duc-linux.tar.gz
[NathanGiesbrecht]: https://gist.github.com/NathanGiesbrecht
[NathanGiesbrecht_link]: https://gist.githubusercontent.com/NathanGiesbrecht/da6560f21e55178bcea7fdd9ca2e39b5/raw/b5594a39e908548f4319294553497d2db3053e0a/noip2.service
