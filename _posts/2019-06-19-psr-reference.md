---
layout: post
title: PHP Standards Recommendation Reference
---

The PHP Standards Recommendation, also known as "PSR", is about how you should write your PHP code so that it'll be easily readable and usable by others. It covers coding style, file organization, autoloading and standardizes various interfaces.

## PSR-1: Basic Coding Standard

- Files must only use `<?php` and `<?=` tags.
- File must only use UTF-8 without BOM for PHP code.
- Files should either declare symbols or cause side-effects but should not do both.
- Namespaces and classes must follow an "autoloading" PSR (PSR-0, PSR-4).
- Class names must be declared in `StudlyCaps`.
- Class constants must be declared in all uppercase with underscore separators.
- Method names must be declared in `camelCase`.

## PSR-2: Coding Style Guide

- Code must follow a "coding style guide" PSR (PSR-1).
- Code must use 4 spaces for indentation, not tabs.
- There must not be a hard limit on line length; the soft limit must be 120 characters; lines should be 80 characters or less.
- There must be one blank line after the namespace declaration, and there must be one blank line after the block of use declarations.
- Opening braces for classes must go on the next line, and closing braces must go on the next line after the body.
- Opening braces for methods must go on the next line, and closing braces must go on the next line after the body.
- Visibility must be declared on all properties and methods; abstract and final must be declared before the visibility; static must be declared after the visibility.
- Control structure keywords must have one space after them; method and function calls must not.
- Opening braces for control structures must go on the same line, and closing braces must go on the next line after the body.
- Opening parentheses for control structures must not have a space after them, and closing parentheses for control structures must not have a space before.

## PSR-3: Logger Interface

The main goal is to allow libraries to receive a `Psr\Log\LoggerInterface` object and write logs to it in a simple and universal way. Frameworks and CMSs that you have custom needs may extend the interface for their own purpose, but should remain compatible with this reference. This ensures that the third-party libraries an application uses can write to the centralized application logs.

## PSR-4: Autoloader

This PSR describes a specification for autoloading classes from file paths. It is fully interoperable, and can be used in addition to any other autoloading specification, including PSR-0 and also describes where to place files that will be autoloaded according to the specification.

## PSR-6: Caching Interface

Cache-aware libraries that can be integrated into existing frameworks and systems without the need for custom development.

## PSR-7: HTTP Message Interfaces

The first line of a request is the "request line" and contains the following (in order):

- The HTTP request method
- The request target (usually either an absolute URI or a path on the web server)
- The HTTP protocol version

Followed by one or more HTTP headers, an empty line and the message body.

## PSR-11: Container Interface

Standardize how frameworks and libraries make use of a container to obtain objects and parameters.

## PSR-13: Link Definition Interfaces

Serialize a response with hypermedia links into one or more wire formats independent of the process of deciding what those links should be.

## PSR-16: Common Interface for Caching Libraries

Libraries can drop their own caching implementations and easily rely on the one given to them by the framework or another dedicated cache library. It is independent of PSR-6 but has been designed to make compatibility with PSR-6 as straightforward as possible.
