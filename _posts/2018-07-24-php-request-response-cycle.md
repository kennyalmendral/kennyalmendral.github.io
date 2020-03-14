---
layout: post
title: PHP Request-Response Cycle
---

This cycle in PHP describes the way that a browser and a web server communicate to process user requests. It may seem simple, but it's important to keep it in mind while developing with PHP because things like header redirection, output buffering and setting cookies are all affected by this cycle.

![PHP Request-Response Cycle](https://raw.githubusercontent.com/kennyalmendral/kennyalmendral.github.io/master/images/request-response-cycle.png "PHP Request-Response Cycle")

1. To start with, we have our browser and the web server.
2. The browser makes a request to the web server, e.g. you typed in the domain of a site.
3. On that web server, a software will need to intercept that request and that software is called "Apache".
4. Apache then sees the request and will search the file that corresponds to it.
5. Afterwards, it then goes to the file system and looks for that file. When found, it checks if that file has a `.php` extension and if there is, the PHP code in that file will be processed.
6. During the processing, Apache may need to go back and forth to the database a couple of times, it may be to request some information from the database, store information in the database, etc.
7. Once the processing is done, there's one final step in which it assembles the HTML markup that's going to be returned and then sends that back to the browser and that's the response that the user sees.

**Previous Post:** [PHP Overview]({{ site.url }}/php-overview/)

**Next Post:** [PHP Variables and Comments]({{ site.url }}/php-variables-comments/)

_This is part 2 of the [PHP Basics]({{ site.url }}/php-basics/){:target="_blank"} series._

---
