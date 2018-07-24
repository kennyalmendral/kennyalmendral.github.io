---
layout: post
title: PHP Overview
---

PHP is commonly known as a programming language for the web but technically speaking it is not. It's actually a server-side scripting language. The main differences between the two are:

+ A *Script*

    + Runs in response to an event
    + Performs instructions from top to bottom
    + Little to no user interaction after the initial event, e.g. page load

    **Note:** A PHP script doesn't run until a web page is requested.

 + On the other hand, a *Program* 

    + Runs even when not responding to events, it continues to run and wait for interaction, whether that interaction comes from a user making choices or from other programs making input.
    + Jumps around instructions, so there's no clear start and end point.
    + Lots of user interaction, e.g. Photoshop

    **Note:** As scripts get more complex, they start to resemble programs and the simplest programs are basically scripts thus we can say that it's a distinction without a difference.

###Server-side scripting language

When talking about "server-side" and its opposite, which is "client-side", what we're talking about is where the code does its work. Does the code run on our web server (server-side)? Or on the user's computer which is client-side. The client-side when we are working with web pages is the user's browser.

**Note:** The client-side Javascript code is sent to the user's browser and then it does its work there while PHP code is never sent to the user, it runs entirely on the server and the results of that code is what is sent to the user's browser and that's the big difference right there. Because PHP runs on a web server, that means it cannot run on its own.

###Not a compiled language

PHP doesn't need to be compiled, it's executed by the web server exactly as it's written while compiled languages like Java or C# needs a compiler before it can be executed.

###Designed to be used with HTML

PHP generates HTML and can be embedded in any HTML markup.

**Note:** Think of PHP as the *input* and HTML as the *output*.
    
---
