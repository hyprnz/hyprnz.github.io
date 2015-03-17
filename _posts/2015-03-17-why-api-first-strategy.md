---
title: Why you need an API first strategy
layout: post
author: Gareth Evans
---

Digital disruption is here, one-third of Australia’s economy faces a [‘short fuse, big bang’](http://www2.deloitte.com/content/dam/Deloitte/au/Documents/Building%20Lucky%20Country/deloitte-au-consulting-digital-disruption-whitepaper-0912.pdf) scenario in the near future. Technology is shaping society as fast as society is shaping technology. Application Programming Interfaces (APIs) are emerging as a way to both support rapid change and as a way to create it. 

## So what is an API?

An API enables one application to talk to another application over the internet.

The term API has been around for a long time, although its most recent incarnation is arguably its most interesting. A modern API is a way to safely expose digital resources to be consumed internally, by trusted partners or as an open API. Exposing data creates many more opportunities than exposing applications which have a single purpose created by the imagination of a single company.

## Why do you need an API strategy?

### The scalepocalypse is near!
There are currently 15B internet connected devices in 2015, there will be 40B in 2020.

> In terms of phases or eras, the Cisco® Internet Business Solutions Group (IBSG) believes that we are currently experiencing the Internet of Things (IoT), where millions of new devices are regularly being connected to the Internet. As these “things” add capabilities like context awareness, increased processing power, and energy independence, and as more people and new types of information are connected, we will quickly enter the Internet of Everything (IoE), where things that were silent will have a voice. - [Cisco](http://share.cisco.com/IoESocialWhitepaper/#/0/2)

Many companies are struggling to support their existing applications, something has to change in the way we architect for connectivity. APIs that adhere to the principles of a REST based architectural style offer promise in that a single API is capable of supporting many different digital channels.

### Reduce integration costs
The IoT and IoE is a new problem requiring a new way of thinking. Existing architectures will not solve this problem. With so many devices and operating systems to support APIs must be designed and developed with the ability to scale, be fast to change and encourage adoption and reuse. Cacheability becomes important with many devices and channels, moving this to the network using HTTP is a well known solution utilised by APIs. Having many layers between clients and persistence creates overheads and delays. Modern APIs move closer to the persistence layer avoiding accidental complexity and minimising essential complexity. Applications developed to replace legacy systems commonly see a 10x order of magnitude reduction in lines of code for the same functionality, with added benefits including performance and maintainabilty.

> The Internet is no-thing at all. At its base the Internet is a set of agreements, which the geeky among us (long may their names be hallowed) call “protocols,” but which we might, in the temper of the day, call “commandments.” - [Cluetrain](https://medium.com/backchannel/internet-under-fire-gets-new-manifests-207a922b459e)

By building APIs that work the way the internet works we can leverage many of its advantages.

Currently many APIs have their own special snowflake schemas that are specific to just that one API. Standard MIME Media Types such as Collection+JSON allow clients to reuse code within an API and potentially across APIs. MIME Media Types can be registered with [IANA](http://www.iana.org/assignments/media-types/media-types.xhtml) for others to understand and reuse. 

Application semantics are the domain specific data fields within a standard MIME Media Type such as Collection+JSON. Whilst we can write one parser for all Collection+JSON data, application semantics are unique to the application. This is the semantic gap. Well designed APIs attempt to reduce the semantic gap which leads to less code having to be written.

### An API can be an R&D lab for your organisation
Safely exposing data with an API can turn your API into an R&D lab. This can be a lab that you use to experiment with different applications, testing new ideas in the market, or it can be used as an indirect channel for innovation. By exposing an API externally, individuals and other companies can innovate on your behalf. Many large companies struggle to innovate due to slow internal processes and lack of an innovation mindset, where more nimble startups may excel. One way to combat digital disruption is to expose an API and let others innovate on your behalf. This allows companies to share risk and reward with smaller companies in a very controlled way. Invite others to build something with your API, then call them if it starts getting popular.

### Composability is the key to speed

According to the ProgrammableWeb, the number of publicly available APIs is growing exponentially. 

![Growth of APIs]({{ site.url }}/assets/chart-of-web-api-growth-from-2005-through-2013-source-programmablewebcom-2-638.jpg)

As the number of APIs grows so does the opportunity to combine them in different ways. This could be inter industry combinations or intra industry.  

>Five key drivers of digital disruption – wastage of resources, redundancy, complexity, limited access and broken trust. - [Rachael Botsman](http://www.slideshare.net/capgemini/igital-transformation-review-7)

APIs are one of the vehicles entrepreneurs are using to exploit these drivers by reducing waste, cutting out the middle person, opening access to data and improving customer experience and trust. APIs can be a foundation for innovation, as companies are able to expose their data for others to combine in diverse and innovative ways.

APIs don’t have to be exposed externally to be of benefit. Trusted and open APIs allow businesses to expose their data to other companies. Proprietary APIs allow businesses to expose data internally. Both can reduce the semantic gap by using media types that can be consumed by many clients rather than traditionally exposing each bit of data with a unique interface requiring more code to be written.

### The value of exposing data outweighs the risks

APIs can be private, exposed to trusted partners or completely open. Private APIs offer many benefits, yet open APIs have the added benefit of indirect innovation. For risk averse companies this is a dilemma. How do you expose your most valuable asset, your data, in a way that is safe? 

REST based architectural styles promote having a single front door to the API. Rather than exposing a number of URLs as endpoints that must all be secured, a single front door is easier to defend than many side doors. Even though all access comes through the front door, the first room you see may be different depending on who or what you are.

## Summary

An API is like a network of data. The power of networks is in the number of connections. Metcalfe’s law states that the value of a network increases proportionately to the square of the number of users. If companies continue to act like hubs then they do not exploit the additional connectivity that is possible. As Mike Amundsen said at APIDays in Sydney recently - Be a node not a hub. Data without an API is like a computer without the Internet.
