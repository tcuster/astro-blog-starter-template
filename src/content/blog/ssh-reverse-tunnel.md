---
title: "Gotta learn Reverse SSH tunnel"
description: "or set up https and a local server for code repos"
pubDate: "May 31 2026"
heroImage: "/blog-placeholder-2.jpg"
---

The issue: Some coffee shops have closed ports for their networks. 
I like to get work done at coffee shops.

The solution(s): If possible, I will need to reach my home PC. But without having done this before, I'm not sure if this is the best solution.
So, if it fails... I learn. Learning is important even if it is learning that this was never a useful solution to this issue.
Option 2. According to a certain other person, there is an option to be able to use https to access a code repo on a home server. 
Similar but different. Truth be told it would be more obvious that port 8080 would absolutely be open. 

For now, I'll just rest and recover and slap some potentially useless instructions like the ones I found for using Typescript with mdx
Oh, and the instructions for adding a darkmode toggle to the page. That definitely broke the build. I'll have to reverse those when I post this. 

The SSH tunnel/reverse tunnel --whichever one it actually is matters little until and only if I get it working.

>On Computer A (behind the closed ports), run the following command in your terminal:
>
>ssh -R <port_on_B>:localhost:<local_web_port> user@<IP_of_B>
>
><port_on_B>: The open port on Computer B that external users will connect to.
>
><local_web_port>: The port your local website/service is actually running on (e.g., \(80\) or \(8080\)).
>
><IP_of_B>: The public IP address or domain name of Computer B.Essential Configurations
>
>For this to work smoothly, you need to adjust one setting on Computer B so that it listens to external connections, not just local ones.
>
>On Computer B, open the SSH daemon configuration file:sudo nano /etc/ssh/sshd_config
>
>Find and uncomment (or add) the following line:GatewayPorts yes
>
>Save the file and restart the SSH service:sudo systemctl restart ssh

A third option appeared, less of a on-prem system solution (option 2, leaving that to my dev friend), and more of a token (classic) solution. I don't want to start over-engineering until my environment is functional regardless of geography.

>Log into your account on the GitHub Website.
>
>Click your profile photo, then select Settings.
>
>In the left sidebar, click Developer settings.
>
>Select Personal access tokens -> Tokens (classic).
>
>Click Generate new token -> Generate new token (classic).
>
>Give your token a descriptive name and check the repo scope.
>
>Click Generate token and copy it immediately. You will not be able to see it again.
>
>git remote -v
>
>git remote set-url origin https://github.com
>
>git config --global credential.helper cache