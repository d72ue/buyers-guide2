---
layout: post
title: Alpha assessment
desc: This is for services which are in the Alpha stage of development, or moving into private beta
proj-url: https://github.io/buyers-guide2
proj-num: 04
---





This page should outline what the platform offers for those services who are entering thier Alpha stage after Discovery. I would suggest reading this at the beginning of the Alpha stage but also it will have information that you will find useful before you go to your Alpha assessment.

### Infrastructure overview

The taxplatform is currently hosted on a Gcloud infrastructure provider. This allows us to create and scale infrastructure how and when we want to without the long lead times and expense normally associated with physical infrastructure. This infrastruture is built and supported by a central web-operations team in London. 

There are two main infrastructure areas to the tax platform, the internet facing area where we host front-end applications which only deal with transient customer data. The second area is the PSN facing area which is a more secure area which talks to the HMRC head of duty systems and stores some customer data. The seperation of these two areas allow us to keep our customers data secure as well as talking to customers over the internet. These two areas are joined by a secure accredited bridge. 


### Testing and development 

At this stage the tax platform gives you a number of environments to play with, each offering different benefits.

* A [development environment][development environment] 
	* This will allow your developers to push their working code to an environment representative of the real world. The Development environment will contain up to date microservices from other teams, test instances of the Aspire head of duty systems, as well as government gateway and IDA. 
	* You can deploy to this environment whenever you like.   


* A [QA environment][QA environment] 
	* This is where your developers can push code ready for functional testing by your QA. This also has test instances of IDA, government gateway and the aspire back-end head of duty systems. You must test sucessfully here to progress to production. 
	* You can deploy to this environment whenever you like.   


* A [staging environment][staging environment]
	* The staging environment is where we performance test services. Although though it's not essential to performance test before a small private Beta we will demand that you at least have deployed to staging. Be prepared to work with the web-ops team in the week moving up to your first production release. 
	* You need web-ops to help you deploy to staging on your first deployment but after that you can deploy and test here whenever you like.   

### Continuous Deployment
* [Production deployments][step by step guide]
	* This is the customer facing tax platfrom! At this stage this environment can be used to run a small private beta. There are a number of prerequisites before you are allowed to go into this environment. It's worth reading the [step by step guide to production releases][step by step guide] now. Once you have met all these prerequisites you can deploy to production. 
	* For your initial deployment it's best to raise a PRODREL ticket in Jira as a placeholder as soon as possible (you can't be too early!). After this initial deployment you can use the [release form][release form] which will allow you to release with 48 hours notice.
	* Don't forget that you will have to go through a [performance readiness review][PRR].

### Security
While it will be your responsibility as a team to get your service accredited through the standard RMAD process the tax platform is regularly penetration tested and its acrreditation updated. This means if you only have to worry about your application and not about the infrastructure that your service runs on. There are number of proactive security measures we take as a platform team to ensure the protection of our customers.

* The platform infrastrcuture is penetration tested every 6 months or upon any architectual change outside the scope of the existing RMADS
* The platform RMADS are updated every 6 months or upon any functional change which would affect security 
* Akamai is in place to provide DDOS protection.

### Monitoring

The tax platform provides a number of tools and mechanisms that your service can use to monitor your service. These tools range from monitoring performance or customer satisfaction to loggin internal audit events for fraud prevention. Some of these services are free to use if you wish, others we insist on in order to enable us support your service in live. 

* Analytics
	* Google analytics is our primary analytics tools and will tell you much about customer behaviour on your service. 
	* Deskpro, if used to support your pages, will show you which pages are generating the most support tickets, the nature of these tickets and how quickly they are being resolved.
* *Incident Monitoring*
	* Kibana is used to log application audit events and we reply on the team to define what is important.  
	* Sensu alerts can then be set up from the kibana logs to alert the service team and the web-ops team when services are behaving abnormally. 
	* Pagerduty is used to alert the out of hours support team (2 members of web-ops) if anything unusual is happening outside of office hours.
* Transaction monitoring
	* Splunk is used to record and interogate specific business events. It is stored in a more secure area of the tax platform (PSN facing) so that this data can contain information specific to customers. This can be used by enforcement and compliance and other business areas to understand customer behaviour. 

Web-ops use these same tools to monitor the platform infrastructure as your team use to monitor your service. 

### Incident response

Once you have deployed onto the tax platform and you have your monitoring set up your service will be supported both in and out of hours by the web-operations team. We supply a dedicated engineer and on-call service manager 24/7/365 who will respond to any monitoring alerts of esculation from customer support. 

During office hours your team will always be informed and consulted on decisions regarding the production service and we will always endevour to keep your service running. Out hours we may need to take your service down if it risks any of the other platform services but will work with you to get it fixed and back up and running the next day. We communicate these production service decisions through JIRA tickets but also announcements by the [live service announcements email][announcements].

### Customer Support

The tax platform also comes with its own customer support service. This is built using a tool called Deskpro. It allows customers to submit support requests as well as feedback. These tickets are then responded to by a tax platform customer support team and supporting expert tax teams. The responses are delivered by email. 

The tools team in London look after this service and can assist you in understanding how to get the most out of the support model. Contacts can be found below:   
  
  <andrew.sheppard@digital.hmrc.gov.uk> 07979707726

  <alexander.brown@digital.hmrc.gov.uk> 07500789508

#### Remember, if you have a need that they platfrom currently doesn't meet please get in touch...
<tim.britten@digital.hmrc.gov.uk>

<kalbir.sohi@digital.hmrc.gov.uk>





[development environment]:      https://confluence.tools.tax.service.gov.uk/display/DTRG/05+Deploying+to+Dev
[QA environment]:				https://confluence.tools.tax.service.gov.uk/display/DTRG/10+Deploying+to+Web-QA
[staging environment]:			https://confluence.tools.tax.service.gov.uk/pages/viewpage.action?title=11+Deploying+to+Staging&spaceKey=DTRG
[step by step guide]:			https://confluence.tools.tax.service.gov.uk/display/WEBOPS/Step+by+Step+Guide+to+Production+Releases
[release form]:					https://releaseform.tax.service.gov.uk/
[PRR]:							https://confluence.tools.tax.service.gov.uk/display/DTRG/Platform+Readiness+Assessment
[announcements]:				https://groups.google.com/a/digital.hmrc.gov.uk/forum/#!forum/ddc-tax-plat-live-ops-announcements




