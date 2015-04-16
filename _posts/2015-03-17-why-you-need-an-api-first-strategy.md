---
title: Why you need an API first strategy
layout: post
author: Gareth Evans
twitter: gareth__evans
genre: API
keywords: API first, scalepocalypse, R&D lab, composability, private API, trusted API, open API, digital disruption, network of data, Metcalfe’s law, digital resources, internet of things, software architecture
---

Digital disruption is here. One-third of Australia’s economy faces a [‘short fuse, big bang’](http://www2.deloitte.com/content/dam/Deloitte/au/Documents/Building%20Lucky%20Country/deloitte-au-consulting-digital-disruption-whitepaper-0912.pdf) scenario in the near future. Technology is shaping society as fast as society is shaping technology. Application Programming Interfaces (APIs) are emerging as a way to both support rapid change and as a way to create it. 

## So what is an API? 

An API enables one application to talk to another application over the internet.

The term API has been around for a long time, although its most recent incarnation is arguably its most interesting. A modern API is a way to safely share digital resources to be consumed either internally, by trusted partners or through an open API. Exposing digital resources creates many more opportunities than exposing applications that have a single purpose thought up by a single company.

## Why do you need an API strategy?

### The scalepocalypse is near!
There are currently 15B internet connected devices in 2015, there will be [40B in 2020](http://www.slideshare.net/rnewton/scale-freeap-is).

> In terms of phases or eras, the Cisco® Internet Business Solutions Group (IBSG) believes that we are currently experiencing the Internet of Things (IoT), where millions of new devices are regularly being connected to the Internet. As these “things” add capabilities like context awareness, increased processing power, and energy independence, and as more people and new types of information are connected, we will quickly enter the Internet of Everything (IoE), where things that were silent will have a voice. - [Cisco](http://share.cisco.com/IoESocialWhitepaper/#/0/2)

Many companies are struggling to support their existing applications, something has to change in the way we architect for connectivity. APIs that adhere to the principles of a REST based architectural style offer promise in that a single API is capable of supporting many different digital channels at lower cost than other approaches.

### Reduce integration costs
The IoT and IoE is a new opportunity requiring a new way of thinking. Most existing architectures will not solve this problem. With so many devices and operating systems to support, APIs must be designed and developed with the ability to scale when successful. APIs must also be designed with affordance in mind, along with the ability to easily test, deploy and iteratively and incrementally change. 
Having many layers between clients and persistence creates overheads and delays. Cacheability becomes important with many devices and channels. Moving this to the network using HTTP is a well known solution utilised by APIs. Modern APIs move closer to the persistence layer avoiding accidental complexity. Applications developed to replace legacy systems commonly see a 6x to 10x reduction in lines of code for the same functionality, with added benefits including performance and maintainabilty.

> The Internet is no-thing at all. At its base the Internet is a set of agreements, which the geeky among us (long may their names be hallowed) call “protocols,” but which we might, in the temper of the day, call “commandments.” - [Cluetrain](https://medium.com/backchannel/internet-under-fire-gets-new-manifests-207a922b459e)

By building APIs that work the way the internet works we have confidence that we are using patterns and protocols that can be understood by developers, accepted by servers and will perform at scale.

Currently many APIs have their own specific snowflake schemas that reduce ease of use. Standard MIME Media Types such as [Collection+JSON](http://amundsen.com/media-types/collection/) allow clients to reuse code within an API and potentially across APIs. MIME Media Types can be registered with [IANA](http://www.iana.org/assignments/media-types/media-types.xhtml) for others to understand and reuse.

Application semantics are the domain specific data fields that may still exist in a standard MIME Media Type. Whilst we only need to write one parser for a standard MIME Media Type, application semantics are unique to the application. This is the semantic gap. Well designed APIs reduce the semantic gap through the use of standard MIME Media Type which reduces complexity and cost.

### An API can be an R&D lab for your organisation
Safely exposing digital resources with an API, creates an [R&D lab](http://apievangelist.com/2014/07/07/apis-can-open-up-your-company-to-outside-ideas/) for your organisation. This can be a lab that you use to experiment with different applications, testing new ideas in the market, or it can be used as an indirect channel for innovation. Open APIs allow individuals and other companies to innovate on your behalf. Many large companies struggle to innovate due to slow internal processes and lack of an innovation mindset, where more nimble startups may excel. One way to join the digital disrupters is to create an open API and let others innovate on your behalf. This allows larger companies with valuable digital resources to share risk and reward with smaller more innovative companies in a way that benefits everyone. Invite others to build something with your API, then call them if it starts getting popular.

### Composability is the key to speed

According to the ProgrammableWeb, the number of publicly available APIs is [growing exponentially](http://www.programmableweb.com/api-research). 

![Graph showing growth of Web APIs since 2005](/assets/20150317/chart-of-web-api-growth-from-2005-through-2013-source-programmablewebcom-2-638.jpg)

As the number of APIs grows so does the opportunity to combine them in different ways. This could be inter industry combinations or intra industry.  

>Five key drivers of digital disruption – wastage of resources, redundancy, complexity, limited access and broken trust. - [Rachael Botsman](http://www.slideshare.net/capgemini/igital-transformation-review-7)

APIs are one of the vehicles entrepreneurs are using to create digital disruption by reducing waste, cutting out the middle person, opening access to data and improving customer experience and trust through innovative products. APIs can be a foundation for innovation, as companies are able to share their digital resources for others to combine in diverse and innovative ways.

APIs don’t have to be shared externally to be of benefit. Sharing digital resources internally through an API allows for the development of small focused internal applications with less expense and greater speed. They may also combine digital resources from different internal APIs or mash them up with external APIs from other companies to solve internal business problems.

### The value of exposing digital resources outweighs the risks

APIs can be private, shared with trusted partners or completely open. Private APIs offer many benefits, yet open APIs have the added benefit of indirect innovation. For risk averse companies this is a dilemma. How do you expose your most valuable assets, your digital resources, in a way that is safe?

REST based architectural styles promote having a single front door to the API. Rather than exposing a number of URLs as endpoints that must all be secured, a single front door is easier to defend than many side doors. Even though all access comes through the front door, the first room you see may be different depending on who or what you are.

Companies that do not consider sharing digital resources are at greater risk of a short fuse big bang scenario happening to them and if it does they will be less prepared to respond.

## Summary

An API should be like a network of digital resources, where the power of the network is in the number of connections. [Metcalfe’s law](http://en.wikipedia.org/wiki/Metcalfe%27s_law) states that the value of a network increases proportionately to the square of the number of users. If companies continue to act like hubs then they can not exploit the additional connectivity and value available through APIs. 

![Interconnected nodes versus an isolated hub](/assets/20150317/node-not-hub.png)

>Be a node not a hub - [Mike Amundsen](http://www.slideshare.net/rnewton/scale-freeap-is)
