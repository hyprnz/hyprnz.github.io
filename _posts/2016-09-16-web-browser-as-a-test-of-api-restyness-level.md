---
title: Web browser as a test of API RESTy-ness level
description: How to quickly assess the REST level of an API
layout: post
author: Hypr
twitter: hyprnz
genre: API
keywords: humble browser hypermedia API
---

I have made the argument that we should be able to explore our API using a humble browser. Our criteria for this is below. First setup your browser of choice with headers and a renderer for the API. I use both Firefox and Chrome. Unfortunately, they both still need tweeks! 

To test these we use browser plugins for specialising content negotiation.

We think a good hypermedia API should:

* Be able to do GET and POSTs on a web browser with only a mouse and keyboard (and setup as above). This means that we can GET throughout the network, including searches. In practice, DELETE and PUT are not needed but could be included, in which case a little javascript can be added into the HTML representations. (Also, once you’ve got past this you’ll be developing a client anyway that requires all the verbs.)
* Be able to traverse the network of data really easily and intuitively at the speed of our thinking so that we can explore the network and start to understand the underlying domain, not just the link semantics
* Always be able to find the current page the same way each and every time (aka self)—preferably by clicking the same spot (for example, traversing back up should be a matter of click-click-click rather than locate-move mouse-click—make self first and up or parent or collection second as a matter of course and the links section always at the top). Another way to think about this is that keep the ordering of attributes in the representation consistent
* Be able to bookmark any resource and cut-and-paste in a chat window or email to share with others
* Ensure that it is secure (across all points above which includes diving back into the middle) and that the current user can get to it with the correct credentials
* Keep representations sparse. For example, metadata should be orthogonal such that the media types the server is likely to provide us should not be in the representation; avoid empty attributes across the wire
* Be able to do content-negotiation (the client must be able to express their weighted preferences across a combination of factors—for example, content type may be returned based on accept type and others headers such as the presence of headers making it a machine request rather than a human request)
* Ideally, I would like to be able to “peek” ahead before I get the full payload—this relates to size of payload and the difference in designing by-value and by-reference—that’s why ATOM is so appealing
* See what version of the API we are on
* Documents should strive to fit into one TCP segment (assuming you are compressed)


**Note**: while the use of schema-less URIs is RFC valid (ie starting with // instead of http(s)) it is not something that the author of JSONView is going to support, making links unclickable. See github issues.