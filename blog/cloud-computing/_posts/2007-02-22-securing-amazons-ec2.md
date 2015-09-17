---
title: 'Securing Your Data on Amazon’s EC2'
link: http://cloudscaling.com/blog/cloud-computing/securing-amazons-ec2/
author: Randy Bias
description: 
post_id: 23
created: 2007/02/22 07:02:04
created_gmt: 2007/02/22 07:02:04
comment_status: open
post_name: securing-amazons-ec2
status: publish
post_type: post
layout: post
category: cloud-computing
---

# Securing Your Data on Amazon’s EC2

As a proof of concept, we've released a new Amazon EC2 'AMI' (ami-34ba5f5d) that uses filesystem encryption ([dm-crypt](http://www.saout.de/misc/dm-crypt/)) for the 'ephemeral store'. This image is available to the general public and we hope you get some good use from it. If you were holding back testing because of concerns around the security of your data, this should alleviate those concerns somewhat. We're using the default AES-256 encryption of dm-crypt and the bits on disk should be well and good scrambled. Note that this AMI is not designed to persist the data between reboots as we're using a random key generated at boot time to do the encrypting. It's just designed to alleviate concerns around your data possibly [being snooped by someone else](http://sa.muel.org/go/index.php/2006/10/02/24-whose-turn-is-it-to-clean-up-the-bits). And although it looks like Amazon has taken to heart encrypting the bits on disk sometimes it doesn't hurt to be extra paranoid. ;-)