---
title: 'Clouds are complex, but simplicity scales; a winning strategy for cloud builders'
link: http://cloudscaling.com/blog/cloud-computing/clouds-are-complex-but-simplicity-scales-a-winning-strategy-for-cloud-builders/
author: Randy Bias
description: 
post_id: 3606
created: 2012/02/29 09:54:25
created_gmt: 2012/02/29 17:54:25
comment_status: open
post_name: clouds-are-complex-but-simplicity-scales-a-winning-strategy-for-cloud-builders
status: publish
post_type: post
layout: post
category: cloud-computing
---

# Clouds are complex, but simplicity scales; a winning strategy for cloud builders

All cloud systems are inherently complex, and complexity is inherently evil. You can’t avoid complexity, since the size and scale that drives efficiency also adds complexity.  However, you can choose how complex to make your basic system.  A winning strategy for any team of cloud builders is to start simple and then get more complex organically over time.  Starting with a complex system means multiplying that complexity as you scale, multiplying the risk of a major failure. This article aims to talk about complexity.  I hope for cloud building teams to understand this issue better.  In particular, I hope for many of the [OpenStack](http://www.openstack.org/) folks to gain some insight into this way of thinking. It will help us all to make a better open source project. **Systems & Complexity** I am no expert on [systems theory](http://en.wikipedia.org/wiki/General_System_Theory).  A lot of what I know is based off of 20+ years of hands-on experience or anecdotes with building ISP backbones, datacenters, security systems, storage systems, and writing automation tools.  (Lots and lots of automation tools. I never could stand doing anything by hand.)  That said, over time I have slowly learned and inferred a number of lessons, the most important being 

a. Complex systems fail.

b. People love to build complex systems.

In particular, many engineers see understanding and developing complex systems as a rite of passage.  In reality, the true test of a great engineer is their ability to make things simpler, not more complex. In software development, this is talked about as “elegance” or “code elegance”.  An excellent definition can be found in [SearchSOA](http://searchsoa.techtarget.com/definition/elegant-solution)[1]: _“The word elegant, in general, is an adjective meaning of fine quality. **Refinement** and **simplicity** are implied, rather than fussiness, or ostentation. An elegant solution, often referred to in relation to problems in disciplines such as mathematics, engineering, and programming, is one in which **the maximum desired effect is achieved with the smallest, or simplest effort**. Engineers, for example, seek the elegant solution as a means of solving a problem with the least possible waste of materials and effort.” [emphasis mine]_ Complexity is the opposite of elegance.  Complexity breeds failures.  Systems [that are not designed for failure](http://it20.info/2012/02/the-cloud-magic-rectangle-tm/), which are complex or sprawling, will fail catastrophically.  Frequently catastrophic failure will turn into a [cascading failure](http://en.wikipedia.org/wiki/Cascading_failure).  “High availability” (HA) as typically implemented in an enterprise datacenter will not protect a system from cascading or catastrophic failures.  More importantly, in my experience, HA is a leading cause of catastrophic failures. Traditional HA stems from the idea of _risk mitigation_, predominant in how enterprise systems are designed today. However, it is simply not possible to ensure robustness by [predicting what could go wrong](http://www.cs.washington.edu/homes/gribble/papers/robust.pdf) and adding complexity to handle a predicted range of failures. Cloud systems must embrace _risk acceptance and planning_, the new emerging approach for building **reliably unreliable** cloud systems. **Failures in Systems** There are a number of works on systems and failures, but my favorite is [Systemantics](http://www.amazon.com/Systemantics-Systems-Work-Especially-They/dp/070450331X/ref=sr_1_1?s=books&ie=UTF8&qid=1330466840&sr=1-1) or the [Systems Bible](http://www.amazon.com/Systems-Bible-Beginners-Guide-Large/dp/0961825170) by John Gall.  Considered somewhat facetious or tongue-in-cheek by many, much of its kernels of wisdom ring true.  The entire body of work is best summarized by “[Gall’s Law](http://en.wikipedia.org/wiki/Gall's_law)”: _“A complex system that works is invariably found to have evolved from a simple system that worked. The inverse proposition also appears to be true: A complex system designed from scratch never works and cannot be made to work. You have to start over, beginning with a working simple system.”_ Gall’s Law is a synopsis of Systemantics ‘laws’ 12-16 listed on the [Wikipedia](http://en.wikipedia.org/wiki/Systemantics)page: 

12\. A complex system cannot be "made" to work. It either works or it doesn't.

13\. A simple system, designed from scratch, sometimes works.

14\. Some complex systems actually work.

15\. A complex system that works is invariably found to have evolved from a simple system that works.

16\. A complex system designed from scratch never works and cannot be patched up to make it work. You have to start over, beginning with a working simple system.

The inherent truth in Gall’s Law should be self-evident, but what’s important to understand is that many of the current approaches to building Infrastructure-as-a-Service (IaaS) clouds are deeply rooted in complexity.  In this regard, they look similar to how enterprise datacenters and applications are constructed today: _heterogeneous, sprawling, multiplicity of silos with no prevailing design patterns or reusability_. These kinds of approaches are difficult to scale, to secure, or to maintain with high levels of uptime. Systemantics talks very specifically about failures.  The subtitle of the book is “How systems work and especially how they fail.”  I want to bring a few of the more interesting, but pithy ‘laws’ to your attention including some brief commentary, particularly in the context of large cloud systems (numbered according to how they are found on the Wikipedia page for reference; will not match original text): 

_#22 - “A system can fail in an infinite number of ways.”_

While infinite is an exaggeration, the larger a system is and the more moving parts it has, the more likely you are to encounter unplanned for [edge cases](http://en.wikipedia.org/wiki/Edge_case).  You cannot plan for all edge cases.  You can only try to reduce the number of edge cases by having simpler systems with fewer moving parts. 

_#2 - The Fundamental Theorem: “New systems generate new problems.”_

Systems are created to solve a problem.  Unfortunately, new systems bring new problems in addition to the ones you are trying to solve for.  People, and particularly engineers, want to solve problems by designing new systems.  Whenever possible, use existing systems to solve a problem.  If you must build a new system to solve a problem, make it the smallest possible solution possible to solve the problem.  Solve it as elegantly as possible.  Minimalism.  Simplicity. 

_Not in WP list - “If a problem seems unsolvable, consider that you may have a metaproblem.”_

If a problem doesn’t look tractable then there is a deeper underlying problem that should be addressed.  A great example of this is that AWS doesn’t guarantee virtual server uptime through ‘HA’ or ‘server HA’.  Rather than trying to make virtual servers automatically recover, they simply addressed the metaproblem: the cloud app should handle server failures itself. 

_#31 - “Loose systems last longer and work better. (Efficient systems are dangerous to themselves and to others)”_

## Comments

**[Chris Swan](#3311 "2012-02-29 14:52:00"):** You might like the work in this area by Roger Sessions of Objectwatch -  http://www.objectwatch.com/ It's also worth noting that AWS borrows a lot from the Unix design paradigm - simple elements that can be joined together to achieve complex things.

**[Ranga](#3312 "2012-02-29 17:06:00"):** Randy, great post. With regard to letting apps handle redundancy and not rely on infrastructure for HA, there are companies out there who want to jump the cloud bandwagon but their apps are not cloudy ready apps. They have mix of home grown and vendor applications they use. Most of them use vendor apps for atleast mail, accounting, crm, HR. The vendor might not be ready to make changes and they are stuck but would like to get the benefits of moving to cloud. All of those guys still rely on infrastructure to provide HA.  I guess it will take a while before all apps build the redundancy part. Funny thing is people think that with live-migration they can live with one instance. Secondly, about the features, totally agree. Like Lydia mentioned in her blog here http://blogs.gartner.com/lydia_leong/2011/12/02/cloud-iaas-feature-sets-and-target-buyers/ , at one point it becomes a rat race.

**[Mark Chmarny](#3313 "2012-02-29 17:23:00"):** Amazon really drove the notion of simple service making a powerful solution today at Strata. They illustrated an integration of S3 storage, Elastic Map Reduce (EMR) and the DynamoDB into a fluent data management solution that was both scalable and cost effective. The one that opened my eyes was the capability to choose consistency model (strong or eventual) on each API call!

**[randybias](#3314 "2012-02-29 17:26:00"):** Yes, there are people who have legacy enterprise apps who want a more efficient infrastructure.  They will require more complex solutions; however, it's more likely that most of this stuff simply migrates to SaaS rather than a hosted solution. There isn't much advantage to moving to cloud for these kinds of apps.  Most of the value is in newer apps or moving to SaaS from existing legacy apps. AWS does not do infrastructure HA.  The rapid growth of apps on AWS is proof that most of the current cloud adoption does not need or want infa HA.

**[Boris Renski](#3315 "2012-02-29 20:03:00"):** While I agree with the notion of migrating to SaaS, rather than building out complex infrastructure to support legacy enterprise apps - this is a bit of a perfectionist view... or rather...service provider-focused view, not enterprise focused view.  We may gradually evolve to SaaS + built-for-failure infra all around over a long period of time. However, if we are talking enterprise clouds (not webscale clouds, as you like to call them) - legacy app workloads is where the money is. And this is exactly where VMWare appears to be shooting with their solutions portfolio...and I think they got it right.  To evangelize a cloud inside an enterprise, one needs to target some useful workload. Few enterprises can justify building a cloud "so that their developers will build cloud ready apps on them." Ultimately, the end game AWS-like clouds for cloud-ready apps, but the starting point will always have to be some particular set of legacy workloads when it comes to enterprise clouds.

**[randybias](#3316 "2012-02-29 20:28:00"):** Hi Boris.  Always useful to hear your perspective, although I'm a little confused.  I am always talking open clouds (nextgen clouds, web scale clouds, whatever you want to call them). Here's my confusion: VMware's legacy product line is squarely focused on legacy app workloads, but their new product lines are clearly on scale-out cloud-ready apps.  vFabric, CloudFoundry, Spring+Hadoop, etc.  Absolutely none of this is for existing enterprise applications.  It's all for new applications and all of these are explicitly technology pieces designed to enable and create cloud-ready apps.  Paul Maritz is no dummy. There are two ways to evangelize a cloud inside an enterprise: #1) through workloads as you suggest.  We'll talk more about how Cloudscaling will do this later this year.  I prefer not to tip my hand. #2) in order to provide enterprise infrastructure IT teams with an enterprise-ready open cloud solution that competes effectively with AWS; current enterprise cloud deployment models do not sufficiently address the needs of existing app-devs or the incredible growth of AWS EC2 would not be what it is. Finally, an enterprise I can't mention that just deployed an open cloud style system to facilitate on boarding of cloud-ready applications has something like 10-20 applications inside their firewalls that have been waiting, in some cases for years, for an appropriate infrastructure.  This same enterprise has plenty of enterprise cloud deployments already inside their business. I'm not confused about our positioning at all.  There is a real need and it's not about 10 year old applications.  The need is around the new emerging application workloads, both inside and outside the firewall.  These apps are different and need different infrastructure.

**[Boris Renski](#3317 "2012-02-29 23:30:00"):** When you refer to VMW legacy product line, are you talking about vSphere and vCloud? If so, I think Paul Maritz might disagree with your characterization =).  Cloud Foundry - true, for developers and for cloud-ready apps.  Rest of vFabric... tcServer, GemFire, Postgress etc... new product lines for cloud-ready apps? I don't know. I think the immediate idea is to consolidate and own the bulk Java/Spring application platform all the way through the stack. Less so to support cloud-ready apps. I am not saying you are confused about your positioning or there isn't a need for open-style clouds....  I just feel that the bulk of cloud-ready apps will live outside the firewall, period. When we are talking inside the firewall - my gut feel is that legacy workloads will be by far the majority of the use cases. I hope I am wrong as it will mean more OpenStack and less VMWare inside the firewall...

**[Dmitri Kalintsev](#3318 "2012-03-01 00:13:00"):** Randy, Perhaps I have a bit of a tunnel vision, but in my eyes the very juice of the discussion is around this: > 1) Features: What is the minimal set of services that you need to provide to your users to be a viable solution? > 2) Options: Do your users really need more than one way to do things, to start? Flexible systems are rarely simple, ask Larry Wall. In fact, I think they are one point, rather than two. And it comes to this: "understand your customer". Really, truly, deeply understand *how* what you can do (build cloud, with these or other features and options) can help them being more efficient in *getting their jobs done*. Only then you can make your decisions about what is the absolutely necessary minimal set of functions that you need to provide, with utmost certainty. And start as simple, as possible. [shameless plug on] If you haven't seen it, I've started a post series that describes how one goes about getting to know their customer in such intimate way. The first instalment is here: http://telecomoccasionally.wordpress.com/2012/02/29/innovators-guide-to-purple-cow-breeding-part-1/ \-- Dmitri

**[randybias](#3319 "2012-03-01 11:11:00"):** I understand.  What I'm seeing is that larger enterprises want to host their cloud-ready apps internally.  A good example of this are AT&T's recent announcements at CES in January and Fidelity's work on OpenStack.  There are others as well.  Open clouds have real traction inside the enterprise for private clouds that host cloud-ready apps.  It's just mostly early adopters. Also, as shadow IT increases it will create further pressure on the enterprise IT infrastructure groups to build infrastructure that can support next gen apps.

**[randybias](#3320 "2012-03-01 11:25:00"):** Dmitri, I agree with your comment.  It mostly reinforces the blog posting.  I think the one piece you are overlooking though is that in some cases, particularly when there is disruptive technology emerging, listening to the customer is dangerous.  This is the classic disruption theory preached by Clayton Christensen in The Innovator's Dilemma.  Often, good companies go wrong when disruptions happen *because* they listen to their customers.  Henry Ford would have built a faster horse and Steve Jobs would have made a phone with a stylus. Cloud computing is a classic disruption and many customers are asking for the wrong things.  A great example of this is the emphasis on VLANs in some clouds.  Most customers demand VLANs while not needing them or understanding the technology.  What they understand is that there is an implicit contract historically with VLANs: I get 'my network' and there is no routing or firewalls in between 'my servers'.  Of course, there are alternate mechanisms to VLANs *and* this implicit contract breaks down with SDNs, but I'll blog more on that in the future. My point simply being that sometimes you follow the customer, sometimes you lead them, and sometimes you need to do both.

**[randybias](#3321 "2012-03-01 11:38:00"):** I would also refer you to @bernardgolden 's recent CIO article:  http://www.cio.com/article/701222/How_Cloud_Computing_Is_Forcing_IT_Evolution We're going to reach a tipping point in the next few years where if you aren't leveraging cloud-ready apps your business will be at a significant competitive disadvantage. It's already happening in the big data space and I expect it to accelerate rapidly.

**[Dmitri Kalintsev](#3322 "2012-03-01 13:52:00"):** Randy, I'm with you on that one. The reason why it is difficult to get things right by listening to the customers is because their input is inevitably skewed by *the way they are doing things now*. For example, if a "job to be done" is "to provide a reliable email service to company's employees", then it's very likely that any discussion around "how can we help you do your job better" will revolve around their current solution (e.g., Exchange), and you'll be given suggestions about how you can help them to get it running smoother or cheaper. The fact that the actual "job" is about email service, rather than Exchange in particular, is likely to be missed. Worse still, the more customers you talk to, the more different opinions of what is important you are likely to get - everybody goes about getting their jobs done slightly differently, at a different level of sophistication, etc., which will further confuse the inputs. So, what the innovator is to do? By refocussing the discussion to mapping out *the actual job* and its associated desired outcomes, it is possible to see past the "solution", and get a deep understanding of the job itself. Then, with the complete understanding of tools and methods at your (the innovator's) disposal, you will be able to come up with solutions that your customer wouldn't ever dream of. Yes, the car vs. the horse type of thing. What's interesting, jobs themselves and their associated desired outcomes are very stable over time. Consider, for example, the job of communicating over distance. The job itself hasn't changed over ages; the means to get it done, however, have developed drastically, and continuing to do so. The post on my blog that I linked to above is about this methodology of "seeing past the solution". As I mentioned, it is a first in series, as the topic is too big for a single post. The methodology I'm discussing there has been developed by Clayton Christensen's colleague at the HBS and a good personal friend, Anthony Ulwick. It is called "Outcome-Driven Innovation", if you're interested. \-- Dmitri

**[randybias](#3323 "2012-03-01 14:35:00"):** I am interested. Other than your blog postings how do I learn more?

**[Dmitri Kalintsev](#3324 "2012-03-01 14:50:00"):** I'll send you something to your @cloudscaling.com address in a few minutes.
