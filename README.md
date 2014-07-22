# Postmaster

Postmaster is a simple API for shipping packages. To sign up for a free account, go to
[https://www.postmaster.io/](https://www.postmaster.io/).

## Overview

The Postmaster API follows REST principles. Our API is resource-oriented and returns 
HTTP response codes to indicate errors.	HTTP verbs and authentication are supported, 
which allows most common HTTP clients to communicate with our API easily.	 We 
support CORS which makes client-side application programming straightforward. JSON 
is used for all responses and can also be used for POST requests (along with form-encoding).

## Authentication

You authenticate to the Postmaster API by adding your API key to the HTTP Authorization 
header.	We use basic auth and your key is considered the "username" portion of the auth.

## Client Libraries

We have client libraries written in Python, Ruby, PHP, Java, Go and .Net, and node.js. Check them out at Github. Let us know which languages are important to you on the issue tracker:

 * Python: [Github](https://github.com/postmaster/postmaster-python) - [tar.gz](https://github.com/postmaster/postmaster-python/archive/master.tar.gz)
 * PHP: [Github](https://github.com/postmaster/postmaster-php) - [tar.gz](https://github.com/postmaster/postmaster-python/archive/master.tar.gz)
 * Ruby: [Github](https://github.com/postmaster/postmaster-ruby) - [tar.gz](https://github.com/postmaster/postmaster-python/archive/master.tar.gz)
 * Java: [Github](https://github.com/postmaster/postmaster-java) - [tar.gz](https://github.com/postmaster/postmaster-python/archive/master.tar.gz)
 * Go: [Github](https://github.com/postmaster/postmaster-go) - [tar.gz](https://github.com/postmaster/postmaster-python/archive/master.tar.gz)
 * iOS: [Github](https://github.com/postmaster/postmaster-ios) - [tar.gz](https://github.com/postmaster/postmaster-python/archive/master.tar.gz)
 * .Net: [Github](https://github.com/postmaster/postmaster-csharp) - [DLL](https://github.com/MorbidZach/postmaster-csharp/archive/master.zip)
 * node.js: [Github](https://github.com/postmaster/postmaster-nodejs) - ```npm install postmaster-shipping```