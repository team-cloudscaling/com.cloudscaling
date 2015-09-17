---
title: 'Cloud Computing Came to a Head in 2011'
link: http://cloudscaling.com/blog/cloud-computing/cloud-computing-came-to-a-head-in-2011/
author: Randy Bias
description: 
post_id: 2637
created: 2011/12/30 16:42:39
created_gmt: 2011/12/31 00:42:39
comment_status: open
post_name: cloud-computing-came-to-a-head-in-2011
status: publish
post_type: post
layout: post
category: cloud-computing
---

# Cloud Computing Came to a Head in 2011

Happy New Year! I hope you are all having a fantastic holiday. This is a year end posting that I think you will find particularly compelling. Rather than predicting the future I thought I would take a look back at five long years of ‘cloud computing’. The Cloudscaling blog has a loyal following as can be seen from the website and RSS feed stats. As many of you long time readers know, I’ve been ‘in the game’ working on cloud computing technology or blogging about as long as anyone except perhaps those at AWS. In all of that time, my thinking and assessment of what’s happening and how it’s evolving has changed continuously. What was interesting for me this year is that this continuously changing perspective slowed to a crawl or perhaps even stopped. 2011 is the year that much of my thinking and perspective on cloud computing, particularly infrastructure clouds (aka “IaaS”) hardened. That sounds tough. “Hardened.” I don’t mean hardened in the sense of rigid, but rather in the notion of wet cement drying. Many things that have seemed up in the air now seem settled and my doubts about the future of infrastructure clouds are gone. They are not only here to stay, but the shape and direction of them seem very clear. I’m not certain everyone else is clear, but I am. Perhaps I will be wrong, but I doubt it. Let’s take a look back at the arc of my thinking and how things did NOT change in 2011. That will tell us what 2012 is likely to look like. **The Evolution of My Cloud Thinking** My thinking evolved through three clear phases: 

> Automation -> VMs & Virtual Datacenters -> New IT Paradigm

_Phase 1: Automation_ About this time of year, in late 2006, a short time after Amazon EC2 launched, myself and others prototyped a cloud application management framework similar to RightScale. At that time RightScale was named something else and had not been funded or publicly launched. These were early days. As someone with a deep passion for automation, I remember thinking then that a lot of my lifetime interests (networking, storage, security, and systems management) were all converging and being managed by automation. For me, what was happening was all about automation … and lots of it. _Phase 2: Virtual Machines & Virtual Datacenters_ Roughly summer of 2008, the first “[CloudCamp](http://en.wikipedia.org/wiki/CloudCamp)” was thrown where a number of the cloud bloggers and thought leaders came together for the first time. Unknowingly we all centered about using the term ‘cloud computing’ to explain what this new emerging phenomena was. It was right after this event and over the summer of 2008 that the term “[cloud computing](http://www.google.com/trends?q=%22cloud+computing%22&ctab=0&geo=all&date=2008&sort=0)” really took hold. This also led to the formation of the “[clouderati](http://twitter.com/clouderati)”  and I simultaneously [joined GoGrid](/blog/cloud-computing/what-i-did-in-2008) as the VP Technology Strategy. Perhaps GoGrid biased my thinking, but I started to move from a perspective that was cloud application centric back into my sweet spot of physical infrastructure and a focus on virtual datacenters or what I called at the time, “[cloud centers](http://blog.gogrid.com/2009/01/08/cloudcenters-are-datacenters-in-the-sky/)”. In this view, virtual machines were king and inevitably, the question was: “how will we model existing datacenter environments?” _Phase 3: Cloud Computing is a new kind of IT_ After leaving GoGrid in the summer of 2009 I had the opportunity to step back and take a fresh look at how things had evolved. I wanted to build my own cloud business again, but I wanted to skate to where the puck would be, not where it was today. I also could see that most everyone involved in the cloud computing space was spending time trying to retrofit the notion of ‘cloud computing’ to their existing business models and technology. Simultaneously, I still didn’t see any serious competitors to AWS. **What** were they doing that was so different?? It’s not well known, but in the beginning of Cloudscaling’s (re)formation in fall of 2009 into mid 2010, I did a number of strategic and due diligence engagements on various IaaS vendors for VC firms, Platform-as-a-Service startups, enterprises, and enterprise vendors. During that time I was involved in deep technical dives on the technology and business models for these IaaS vendors. They ranged from GoGrid competitors to more of an enterprise cloud model. By late 2010 Cloudscaling, collectively, had deep architectural and business model understanding of roughly 10 different Infrastructure-as-a-Service (IaaS) players, not including the IaaS clouds that we helped build [1]. I am not sure anyone else had or has that understanding today. What we saw, was telling. My primary takeaway was that even when it came to startups and direct AWS competitors, absolutely none of the infrastructure cloud players were developing their clouds like AWS. For the most part, they were simply integrating common-off-the-shelf (COTS) components to mimic an AWS-like environment. None of them had [AWS velocity](http://cloudscaling.com/blog/cloud-computing/amazon-web-services-rapid-release-cycle) [2], nor were they paying attention to what made AWS special [3]. All too often, they identified ‘flaws’ in AWS that were instead unrecognized strengths. Examples of this include: 

  * [Constrained feature set](/blog/cloud-computing/what-is-amazons-secret-for-success-and-why-is-ec2-a-runaway-train)
  * Standardized instance sizes
  * Lack of VLANs [4]
  * Ephemeral storage
  * Generic load balancing service without fancy vendor lock-in features [5]
That’s when I began to understand that ‘cloud computing’ had less to do with automation or virtual machines/datacenters on demand and more to do with *how* AWS was building their infrastructure cloud. Ask yourself these questions: 
  * Why isn’t VMware more successful in the public cloud space if it’s just VMs and VDCs?
  * Why isn’t there a VMware-based competitor at similar scale to AWS? Or even close?
  * There are now 100+ “VMs on demand” competitors, but almost none have the same growth rate as AWS … why not?
  * What do the largest Internet giants (Amazon, Google, Facebook, SFDC) all have in common from an architectural standpoint and how is that different from a typical enterprise datacenter?
**Cloud Computing vs. Enterprise Computing** I gave the [third opening keynote at Cloud Connect 2011](http://vimeo.com/21372341), behind Werner Vogels of Amazon and Lew Tucker of Cisco. That keynote drove much of the discussion during the first day around ‘enterprise clouds’ and their viability. In that talk was also the initial crystallization of my infrastructure cloud thinking: _We didn’t have one way to build infrastructure clouds … we had two._ One was rooted in the old modalities and thinking around existing datacenters and enterprise applications. The other was rooted in a new way of thinking about Information Technology (IT) that uprooted every approach that had gone before. Enterprise Computing applied to ‘infrastructure cloud’ [6]: 

  * How do I virtualize and manage my existing datacenter apps?
  * How do I achieve bottom line cost savings and extend server consolidation?
  * How can my existing vendors help me create a ‘private cloud’?
  * How can I be compatible with everything I own today?
Cloud Computing applied to ‘infrastructure cloud’: 
  * What can we do to allow application developers to experience ‘infinite scalability’?
  * How can we simplify the allocation of traditional IT resources of networking, storage, and compute?

## Comments

**[Gary Jay Brooks](#3115 "2011-12-30 22:38:00"):** Randy I'm putting my dollars on the PaaS companies and memory based HA clouds. The idea would be Paxos *like* consensus based file systems with ACID/NOSQL structures ready to go. Deploy your data center aware framework from a GIT repo and forget the VM. People will figure out that the hyper-visor is the breaking point and come back around to raw metal and better logic in the application framework. This is why Amazon wins. They provide a easy way for you to deploy apps in a cluster multi-data center arrangement with very little effort. The Virtual Machine seems to be a passage for many into cloud but the true cloud is not about Virtual Machine. The CIO and the CEO will soon save the dollars and invest money into the PaaS to bypass having to pay $100,000 payrolls to DevOps folks and the per core fees. @garyjaybrooks

**[randybias](#3116 "2011-12-30 23:06:00"):** I think that is a legitimate viewpoint. I think what is missing though is an acknowledgement of the differing constraints in each environment which lead to a variety of use cases. At the top most tier, applications ("SaaS") make all of your choices for you. You are "fully constrained" and your selection is based purely on end-user features. Stepping down to the next tier, platforms ("PaaS"), less choices are made for you, but you are still "partially constrained". Ultimately, your selection is based on what features your developers can create for your end-users on that particular platform. It is finite. At the bottom is raw infrastructure where you have "little constraint". You have little or no restraint on what you can build. You can build your own custom PaaS for your own needs for example. Right now what is happening is that large apps are being selectively decomposed. A modern app has many pieces. Some will be on SaaS, some components on PaaS, and some on IaaS depending on the need for customization and specialization. I think it's going too far suggesting one model will win. It's a "right tool for the job" issue ultimately and PaaS is one of the tools.

**[Gary Jay Brooks](#3117 "2011-12-30 23:57:00"):** Legacy app owners will always be around.  I do understand that we will not live and die PaaS. My shared vision is that the PaaS is the future evolution of what cloud will become.  PaaS companies have a long way to go to catch-up with Google like setups as-a-service.  What I see is people are still confused about Google type setups and think that the VM is the way to the holy cloud grail and fail to understand that Google has not a single VM in its platform. SaaS has been around for decades and will never go away. How we serve our SaaS apps will be determined by companies that build PaaS style companies.  Amazon created it own IaaS that smells like a PaaS.  They keep the network open to many languages but companies like Oracle / CloudAccess.net are thinking with a 1 application framework mind with the same access to the DC and fiber as Amazon has built. These 1 framework systems will provide IaaS like Amazon but will add a layer of both PaaS and SaaS in the same bucket that will make it pretty attractive to new startup's and legacy app owners looking to come to the cloud. The year of the API is 2012/13.  2012 will also be the year that we will have to concern yourselves with HIPAA type compliance and easy to deploy and manage "google" like clouds. The CIO is still guessing what it means to build in the Cloud. The right company could easily bend the future.  What is great about Amazon is you can put the Google puzzle together with very few dollars and build a solid -as-a-service company.   What I would like to see is some-one grow up and show customers that 7,200 disk are fine for toys but the new cloud will be built of 320,000 IOP Systems in 1U.  :-D  Facebook is case in point, way to many writes to work with Amazon style systems. Legacy based owners will trust flash and 10 year old code before they trust new memory asynchronous SQL storage engines. my 2 cents.  Love the post.  Been following you lately and I am impressed with what you have in your brain.   Happy New Year!

**[Shaloo Shalini](#3118 "2012-01-01 23:06:00"):** Intrigued by this post, thought provoking. Thanks for sharing. In 2012, do you think the following will take shape wrt cloud computing? * Everyone is familiar with individual's public cloud usage pattern more or less - be it through IaaS, PaaS or SaaS services. Well,  will there be a Cloud usage pattern guide for the enterprise - say based on so far successful (if any) private cloud deployments? NIST next gen doc kind? * Real TCO Analysis - Enterprise $$$ saved with private cloud usage vs Amazon kind of public cloud usage?  * How far would we be as 2012 closes from the turning point when startup/new venture usage of cloud (public or private) exceeds the total cloud usage by legacy enterprises?  Will the demand for 'cloud' based services and economic considerations force enterprises with legacy IT to embrace clouds (private or public) in large numbers making 'legacy IT' a small piece of the overall IT pie? a la mainframe? Do you perceive an 'Amazon' like (or from Amazon services) entity that are IaaS cloud experts - help enterprises weave their own private cloud using their 'on-premise' IT and may be link-up or borrow IT resources from similar private clouds of sister institutions/ friend-corporations, if need arises to scale beyond on-premise IT on demand.  Not a public cloud per se, but a private cloud consortium of sorts? Shaloo

**[Vijay](#3119 "2012-01-01 23:11:00"):** Love the Post and comments from Gary and yourself. I have been following you for few months and impressed with your thoughts. Gary, I am still not sure how far can the 1 framework system go to help since companies like Oracle would price those very high for start-ups. I agree 2012 would be year for APIs and analytic around those.

**[Gary Jay Brooks](#3120 "2012-01-02 00:27:00"):** Vijay, I see is a motion of evolved frameworks like, DJango(Python), Ruby, Joomla(PHP), Drupal (PHP), Java, Node.js (Server side Java Script) and a few other languages now focus on the future of how the framework will work in Cloud multi-data center N+1 consensus-based PaaS setups. We are getting a spawning effect of PaaS companies and nobody is fully mature. It's not only Oracle that is building these types of PaaS companies, PaaS companies are being built from basement nerds. We will see many more come to life this next year. The idea is that you can call a engineer on the phone and or open a ticket and someone will answer your framework question with no worry of IaaS or how it will scale will be freedom for many coders that do not understand how to assemble such a setup in the Amazon cloud or much less be able to afford the bill to hire that staff. The PaaS will "just do it" and it will fail-safe as long as you follow the object oriented languages MVC rules. You simply push your GIT repo and the platform does the scale and HA with your credit card. The 1 framework systems become popular because programmers find a family to work with and someone that understands what they are doing and building. The PaaS that tries to do all languages scares me. I do not know a CTO that can lead a team with every language you can find in the market place. I see companies trying this route. They automate the install of Drupal,Joomla on a VPS and they call themselves a PaaS. Uummm No - These companies are glorified wanna-be-framework hackers with no skills in the application framework. I could see a PHP shop working with Node.js but not a PHP shop trying to do Django, Java, and everything in open source world just because they can compile it into the kernel. I know many people that want to build SaaS apps but they have Zero clue how to build a system in the amazon cloud much less do they have the money to it right. Here is a list of PaaS companies I would keep my eye on. They will enable SaaS companies of the future. http://djangozoom.com/ http://www.cloudaccess.net this is my company so I'm biased. http://www.phpfog.com http://cloud.oracle.com https://openshift.redhat.com http://www.joyentcloud.com/ The key to this puzzle will be that the PaaS learns how to build web services, and layer 2 networking in one single unit and not forget about a object store like the S3 and Elastic *like* Load balancing but it will not be called load balancing, rather apps will use a mix of;file system, anycast, asynchronous environments that see the data center in the framework. I call these apps "Data Center Aware apps". If you study the Cassandra data store you can see some of this code. Google solved this problem long ago with it's mega store system. AKA "Google File system. Megastore is a storage system developed to meet the re-quirements of interactive online services. Megas-store blends scalability of a NoSQL datastore with the convenience of a traditional RDBMS in a novel way, and provides both strong consistency guarantees and high avail-ability. What every PaaS provider should dream to provide to future SaaS companies or Enterprises looking to re-make legacy apps in the cloud. To me it will be the PaaS that solves the puzzle for the coders of writing across a wide area net-work with reasonable latency and support seamless failover between datacenters with ACID like setups will really be a HUGE hit. One of the players could give users a ready to go GUI with point and click type editors to build SaaS applications, with acceptability to the source code to extend the app. We will see what happens this next year. It might take longer and several iterations. I see companies taking a stance and raising fist. Some have bigger check books others. I like to see is that Open Source is giving the basement buy a chance. Anyone has a chance to be the Genghis Kahn of the cloud world. Let's see what happens and who maneuver into position. @garyjaybrooks

**[Vijay](#3121 "2012-01-03 01:44:00"):** Interesting questions, I do get asked on the TCO at most of my meetings with CxOs. But I am not sure if Ent would share the data for anybody to compare with public Cloud usage and hence could make this task difficult. On your last question are you thinking of a Hybrid-cloud setup between private cloud and that happens the challenges on adoption may not change.

**[Vijay](#3122 "2012-01-03 07:07:00"):** Gary, My fear is that "PaaS would just do it" may just be a dream. The way I look at the PaaS market, it is fragmented into whom we can call as developers who would need a development framework and there is where I see likes of "openshit" fitting into. They would provide 1 framework and these would surely be popular. But I understand likes of Oracle are providing a IaaS+PaaS on an appliance so that application do not have to worry on scaling, load balancing and also provide memory/data grid. From your reply I do  understand the reason why the 1 framework system could become popular and using the same maybe folks making appliances can ride on.

**[rstrad1](#3124 "2012-01-04 18:18:00"):** Nice article, you can't know where you're going if you don't know where you've been.  Also, nice mention of Geoffrey Moore.  I've been following him since Crossing the Chasm and I thoroughly enjoyed Escape Velocity. Happy New Year! http://www.stradecis.com

**[Dan Callahan](#3126 "2012-01-06 15:05:00"):** Randy: Excellent analysis.  Posing the question, "why aren't there (any|more) competitors to AWS? really opened up some great insights. I've seen (not surprisingly) that most CIO's are focused on "private clouds" and on cloud services as cost-saving moves.  That reflects the "looking back" point of view you've described... not surprising given the conservative nature of many CIO's. But focusing on how clouds can enable/drive top-line revenue means answering the question, "how can IT become a cost of goods sold, or a variable vs. fixed cost?" that has bedeviled CIO's for some time.  It seems like unless someone can unlock this answer, most enterprise cloud adoption will continue to be driven from a cost-saving basis rather than a revenue-generating one. Dan

**[randybias](#3127 "2012-01-06 15:37:00"):** Dan, That's a great observation. I agree. However I would suggest that as shadow IT adoption accelerates and internal IT departments fail to deliver internal services in a compelling enough manner that urgency will rise. Infrastructure teams, in particular, will be forced, existentially, to compete with external services. This is very similar to how Salesforce adoption evolved. This time however I think internal infrastructure IT has an opportunity to compete successfully if they can overcome their cultural challenges and if they look at solutions from new disruptors rather legacy enterprise vendors who don't understand how the landscape is changing. Big ifs.

**[Egenesky](#3131 "2012-01-24 15:58:00"):** Randy, I just read through this post and thought you might like to expand your readership by having it reposted at in the Cloud Zone at DZone.com.  Let me know if you're interested. Best, Eric Genesky DZone, Inc. egenesky@dzone.com

**[Nils Palmu](#3387 "2012-08-17 02:30:00"):** Last year of 2011 cloud computing really did a very good job for all business in fact in some place like Helsinki Finland most of the IT companies offer cloud computing which put them to a good result.
