[![Build Status](https://travis-ci.org/splink/pagelets-seed.svg?branch=master)](https://travis-ci.org/splink/pagelets-seed)

# Hello Pagelets!

## What?
This demo application shows how a modular and resilient web application can be built using the [Playframework 2](http://www.playframework.com) and the [Play Pagelets Module](https://github.com/splink/pagelets).

The example is a simple multi-language website which is composed of multiple independent pagelets. Each pagelet
obtains it's data, transforms it and eventually renders the data. The complete page is assembled from individual pagelets.
Depending on the selected language, the page is assembled differently and accordingly looks distinct for each language.
If any of the pagelets fail to render, the rest of the page is rendered regardless. Failed pagelets are replaced with
fallbacks. Failure of individual pagelets has no effect on the whole page.

The demo application serves the purpose to
 - showcase the Play Pagelets Module and it's advantages
 - demonstrate how to build a pagelet based application
 - serve as a template for pagelet based projects

## How?
If you have [activator](https://www.lightbend.com/community/core-tools/activator-and-sbt#overview) installed, just enter:

~~~bash
activator new
play-pagelets-seed
~~~

Otherwise open a terminal and

- clone the github repository with
~~~bash
git clone git@github.com:splink/pagelets-seed.git
~~~

- then enter
~~~bash
cd play-pagelets-seed
~~~

- then enter
~~~bash
activator run
~~~

then point your browser to [http://localhost:9000](http://localhost:9000)


## Details

### What's a pagelet?
A pagelet is a self contained (micro)web-site which can be composed with other pagelets into a complex page.

### Why Pagelets?
- Resilient: if one part of the page fails, the rest is unaffected, you can even define fallbacks for your pagelets.
- DRY: because a pagelet is self contained, it can be easily reused on any page.
- Modular: A pagelet can be rendered in isolation. Assets like JavaScript and Stylesheets are defined on a per pagelet
basis so a pagelet is wholly autonomous.
- Flexible: a page can be composed with very little code, and the composition can be easily changed at runtime.
This is quite handy to conduct A/B tests or to serve a different page based on the user's locale, role, ...
- KISS: the scope of a pagelet is limited, thus it is simple to build one.
- Logs: Detailed logs help to gain useful insights on the performance and to find bottlenecks quickly.
- Performance: pagelets are executed in parallel so a page can be served lightning fast. Assets are automatically
concatenated and hashed as well as served with far future expiration dates. Therefore browsers need to make only few
requests, and - as long as the assets haven't changed - can pull them from the local cache.
- Separation of concerns: by embracing pagelets you automagically end up with a clean and flexible application design.
