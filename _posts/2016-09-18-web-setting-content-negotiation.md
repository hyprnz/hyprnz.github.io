---
title: Using weighted preferences in the accept header for hypermedia solutions
description: Settings for a browser to accept weighted preferences
layout: post
author: Hypr
twitter: hyprnz
genre: API
keywords: humble browser hypermedia API
---


The Accept header is part of the [HTTP (RFC 2616)](http://www.w3.org/Protocols/rfc2616/rfc2616.html) spec and gives the browser a chance to tell the server which format it wants for a resource. It can ask for multiple formats in one request and provide the order of preference. Hence the idea of content negotiation. Let’s understand the notation and what preferences we use.

In our scenario we want preferences in this order:

* My greatest preference is JSON (that what I really want!)
* But I will have HTML (I need that for forms)
* Then XML (reluctantly)
* Then, well, whatever you have (because I am being polite)

In RFC 2616, preference is indicated by the [relative quality parameter](https://www.w3.org/Protocols/rfc2616/rfc2616-sec3.html#sec3.9) (q) and its value (qvalue). The value lies between 0-1 akin to a percentage. 0 is low. 1 is high. For example, application/json;q=0.9,text/html;q=0.8. Here JSON is higher (0.9) than HTML (0.8). What you might also notice is that this is a list delimited by commas and each item has a semicolon delimiter.

Here's how the [Accept section in the HTTP spec](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html) defines it:

> Each media-range MAY be followed by one or more accept-params, beginning with the "q" parameter for indicating a relative quality factor. The first "q" parameter (if any) separates the media-range parameter(s) from the accept-params. Quality factors allow the user or user agent to indicate the relative degree of preference for that media-range, using the qvalue scale from 0 to 1 (section 3.9). The default value is q=1.

The spec is a terrible read albeit brilliant. Let’s dissect our scenario.  Here’s what we are wanting and read it in reverse order (right-to-left):

> `*/*;q=0.8,application/xml;q=0.9,application/json;q=0.95,text/html;q=1.0`

--------------------|--------------|---------------
`text/html;`        | `q=1.0`        | The highest priority if you have it is text/html. 1.0 is actually the default level and you can’t get any higher. We set html as the highest because if the server has an HTML representation then give me that first (when I am in a browser). This says that if you have a create or edit form then I will have it in HTML over JSON because we can use the browser to submit form data.
application/json;   | `q=0.95,`      | Otherwise, give me JSON next. See that the 0.95 (or I think of it as 95%) is in between HTML and XML.
`application/xml;`  | `q=0.9,`       | Most of my APIs can serialise to XML or JSON because my corporate customers tend to want XML because, well, it is XML!
`*/*;`              |   `q=0.8,`          | This is a catch all `*/*` wildcard and being polite that I’ll take whatever you can give me. The main issue is not to write */* without q. In that case, the server gets to give you whatever it wants as the highest priority and you’ll find you get indeterminate results.


