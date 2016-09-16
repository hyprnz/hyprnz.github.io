---
title: Setting up the browser for a hypermedia API
description: How to setup the browser with two addins to view clickable `application/json` in Chrome and Firefox
layout: post
author: Hypr
twitter: hyprnz
genre: API
keywords: humble browser hypermedia
---

# Setting up the browser for a hypermedia API

This blog outlines the information for setting up content negotiation between the browser and the server for viewing JSON (ATOM-like) representations of the network of data and also for (create and edit) forms in html. Between these two, we can use the humble browser as the first client of the network of data. 

We need to make two changes: one, browsers need to have the headers changed and then, two, a JSON renderer is needed to make clickable URIs. Obviously, the browser already has a HTML renderer so we don’t need that to be added. 

Basic steps:

* Install addons required for your browsers of choice
* Set the Accept header for each browser that will explore the network of data

## Our accept header

See below on how to read this:

> `*/*;q=0.8,application/xml;q=0.9,application/json;q=0.95,text/html;q=1.0`

## Addons Required

Set the request headers and render the JSON content clickable by:

Browser  | Headers     | JSON renderer 
-------- |-------------| -------------
Firefox  | [Modify Header Value (HTTP Headers)](https://addons.mozilla.org/en-US/firefox/addon/modify-header-value/) | [JSONView](https://addons.mozilla.org/en-us/firefox/addon/jsonview/) 
Chrome   | [ModHeaders](https://chrome.google.com/webstore/detail/modheader/idgpnmonknjnojddfkpgkljpfnnfcklj?hl=en)  |   [JSONView](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc?hl=en)   

**Note:**

* Each JSONView across browsers is different and a port of the Chrome version
* JSONView does not support clickable schema-less URIs (ie starting with // instead of http(s))—see [github issues](https://github.com/bhollis/jsonview/issues/124).