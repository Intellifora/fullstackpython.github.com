title: Logging
category: page
slug: logging
sort-order: 0714
choice1url: /monitoring.html
choice1icon: fa-bar-chart-o fa-inverse
choice1text: How can I monitor my live app with tools other than just logs?
choice2url: /web-analytics.html
choice2icon: fa-dashboard
choice2text: I want to learn more about the users of my application.
choice3url: /web-application-security.html
choice3icon: fa-lock fa-inverse
choice3text: Something in the logs looks strange. How do I learn about security?
choice4url:
choice4icon:
choice4text:


# Logging
Logging saves output such as errors, warnings and event information to 
persistent storage for debugging purposes. 


## Why is logging important?
Runtime exceptions that prevent code from running are important to log to 
investigate and fix the source of the problems. Informational and debugging 
logging also helps to understand how the application is performing even if 
code is working as intended.


## Logging levels
Logging is often grouped into several categories:

1. Information
2. Debug
3. Warning
4. Error

Logging errors that occur while a web framework is running is crucial to
understanding how your application is performing. 


## Logging aggregators
When you are running your application on several servers, it is helpful
to have a monitoring tool called a "logging aggregator". You can configure 
your application to forward your system and application logs to one location 
that provides tools for viewing, searching, and monitoring logging events 
across your cluster. 

Another advantage of log aggregatortion tools is they allow you to set up 
custom alerts and alarms so you can get notified when error rates breach a 
certain threshold.


### Open source log aggregators
* [Sentry](https://github.com/getsentry/sentry) started as a Django-only
  exception handling service but now has separate logging clients to cover 
  almost all major languages and frameworks. It still works really well for 
  Python-powered web applications and is often used in conjunction with other 
  monitoring tools. [Raven](http://raven.readthedocs.org/en/latest/) is open
  source Python client for Sentry.

* [Graylog2](http://graylog2.org/) provides a central server for log 
  aggregation as well as a GUI for browsing and searching through log events. 
  There are libraries for most major languages, including python. Saves data 
  in Elasticache.

* [Logstash](http://logstash.net/) Similar to Graylog2, logstash offers 
  features to programatically configure log data workflows.

* [Scribe](https://github.com/facebook/scribe) A project written by Facebook 
  to aggregate logs. It's designed to run on multiple servers and scale with 
  the rest of your cluster. Uses the Thrift messaging format so it can be 
  used with any language. 


### Hosted logging services
* <a href="https://www.loggly.com/log-management/python-logging/?utm_source=fsp&amp;utm_medium=promo&amp;utm_campaign=march" onclick="trackOutboundLink('https://www.loggly.com/log-management/python-logging/?utm_source=fsp&amp;utm_medium=promo&amp;utm_campaign=march'); return false;">Loggly</a> 
  is a third party cloud based 
  application that aggregates logs. They have instructions for every major 
  language, including python. It includes email alerting on custom searches. 

* [Splunk](http://www.splunk.com/) offers third party cloud and self 
  hosted solutions for event aggregation. It excels at searching and data 
  mining any text based data. 

* [Papertrail](https://papertrailapp.com/) is similar to both 
  Loggly and Splunk and provides integration with S3 for long term storage.

* [Raygun](http://raygun.io/) logs errors and provides immediate notification
  when issues arise.

* [Scalyr](https://www.scalyr.com/) provides log aggregation, dashboards,
  alerts and search in a user interface on top of standard logs.

* There is a [hosted version of Sentry](https://www.getsentry.com/welcome/)
  in case you do not have the time to set up the open source project yourself.


## Logging resources
* This 
  [intro to logging](http://www.blog.pythonlibrary.org/2012/08/02/python-101-an-intro-to-logging/)
  presents the Python logging module and how to use it.

* [Logging as Storytelling](http://www.hybridcluster.com/blog/logging-storytelling/)
  is a multi-part series working the analogy that logs should read like
  a story so you can better understand what's taking place in your web
  application. 
  [Part 2 describes actions](http://www.hybridcluster.com/blog/logging-storytelling-lets-add-action/)
  and 
  [part 3 talks about types](http://www.hybridcluster.com/blog/logging-storytelling-3-types/).

* [A Brief Digression About Logging](https://lukasa.co.uk/2014/05/A_Brief_Digression_About_Logging/)
  is a short post that gets Python logging up and running quickly.

* [Taking the pain out of Python logging](https://hynek.me/articles/taking-some-pain-out-of-python-logging/)
  shows a logging set up with uWSGI.

* Django's 1.3 release brought unified logging into project configurations. 
  This [post shows how to set up logging](http://www.djm.org.uk/how-to-log-file-django-13-and-above/)
  in a project's settings.py file. Caktus Group also has a nice tutorial on
  [central logging with graypy and Graylog2](http://www.caktusgroup.com/blog/2013/09/18/central-logging-django-graylog2-and-graypy/).

* [Django Logging Configuration: How the Default Settings Interfere with Yours](http://www.caktusgroup.com/blog/2015/01/27/Django-Logging-Configuration-logging_config-default-settings-logger/)
  explains a problem with the default Django logging configuration and what
  to do about in your project.


## Logging learning checklist
<i class="fa fa-check-square-o"></i>
Read how to integrate logging into your web application framework. 

<i class="fa fa-check-square-o"></i>
Ensure errors and anomalous results are logged. While these logs can be stored 
in [monitoring](/monitoring.html) solutions, it's best to have your own log
storage location to debug issues as they arise to complement other monitoring 
systems.

<i class="fa fa-check-square-o"></i>
Integrate logging for system events you may need to use for debugging purposes
later. For example, you may want to know the return values on functions when
they are above a certain threshold. 


### Logging isn't enough. How do I analyze more data about the app?
