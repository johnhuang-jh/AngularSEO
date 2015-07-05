# What's AngularSEO

AngularSEO Filter is a SEO solution for AJAX frond-end sites with a JavaEE backend. The AJAX frond-end can be AngularJS, ReactJS and other AJAX frameworkd.

# How it works?

## Integrate SEO filter on JEE server
Add a filter into web.xml, and set its URL mapping to '/*'.

## Prerender static page snapshots
When server started, SEO filter will crawl self site and generate static page snapshot for each one with all the dynamic content fully rendered. It will update the snapshots regularly according your config.

## Let crawlers see static content
SEO filter identify the crawl request by checking the User-Agent keyword . If it is Googlebot, bingbot, etc, filter will response with the pre-rendered static page from the snapshot. Other normal reqeusts will be passed to original service.

## All hashbang URLs are well transformed
All hashbang URLs will be transformed to normal format which can be crawled more easily. So, you needn't care any speical rule of hashbang URL crawling specification.

e.g.<br>
http://abc.com/#!/about -> http://abc.com/_23_21/about<br>
http://abc.com/#/about -> http://abc.com/_23/about<br>

When user click the transformed URLs from search engines, the filter will converte them back to the original format.

# Original AngularJS page source VS Rendered static page source

Original AngularJS page source code:
```
<a href="#about"><div ng-bind="message"></div></a>
```
->
Rendered static page source code:
```
<a href="http://host/_23/about"><div ng-bind="message">the true message after binding</div></a>
```
# Features

* Easy setup: configure a filter only
* Zero code change: needn't change any front-end and backend codes
* Fast page loads: snapshot is prerendered & stored on the same server
* Fully automated: it keeps working in the background after setup
* It is FREE!
* It is open source!

# Requirements

The static site is generated by [PhantomJS](http://phantomjs.org/), so it need be installed on the server. 

# More

I built a simple AngularJS site (http://www.angularseo.net) to validate it. After one day, it was carwled by Google and Bing correctly. You can search 'angularseo.net' and check the cache result.

# Guide

[Click here](https://github.com/angular/angular.js/wiki) for more details.

# Contact

http://www.angularseo.net<br>
John Huang: john.h.cn@gmail.com
