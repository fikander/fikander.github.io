---
layout: project
title: Atlassian JIRA add-on - Retrospective Tools for JIRA
category: software
tags:
  - jira
  - atlassian
  - 
technologies:
  - JavaScript
  - Python
  - Java
  - AppEngine
  - jQuery
published: true
active: true
size: large
---
[Atlassian JIRA add-ons](http://kanbanalytics.com) to animate flow of work on Kanban boards.
Inspired by retrospective meetings, where the teams wanted to see how the project unfolded.

<iframe width="560" height="315" src="https://www.youtube.com/embed/p50TSf82rYc" frameborder="0" allowfullscreen></iframe>

## Motivation

JIRA stores history of status transitions for each work item, so it is possible to determine their status (as well as other parameters, e.g. assignee) at any point in the past.  
This created very tempting possibility to visualise history in a dynamic way, as opposed to static diagrams like Cumulative Flow Diagram:

![CFD]({{ site.baseurl }}/images/projects/cfd.jpg)

Team retrospective meetings gave me further motivation as analysing history of iteration would become much easier if you could just use slider to navigate timeline of the project.  
My goal became providing simple to use tool that would make this possible.

## Atlassian Marketplace

The product is available at Atlassian Marketplace. There are 2 versions:

* [JIRA Cloud version - Retrospective Tools for JIRA](https://marketplace.atlassian.com/plugins/com.sngtec.jira.cloud.kanbanalytics/cloud/overview)
* [JIRA Server version - JIRA Replay](https://marketplace.atlassian.com/plugins/com.sngtec.jira.plugins.kanbanalytics/server/overview)

Dedicated website with more detailed descriptions at **[kanbanalytics.com](http://kanbanalytics.com)**.

## Awards
 
Retrospective Tools for JIRA (JIRA Cloud add-on) has been selected as  
**[Atlassian Codegeist 2015 Best Cloud Add-on winner](http://devpost.com/software/retrospective-tools-for-jira)**

![Winner]({{ site.baseurl }}/images/projects/codegeist2015_winner.png)

## Challenges

* Performance optimisation for JavaScript + jQuery animation of large number of work items.
* Limitations of [Atlassian Connect APIs](https://connect.atlassian.com/) (this might have changed now):
  * JIRA Server version of the plugin has playback controls that are affixed to the bottom of the screen. That makes it easier to operate with large number of issues as you see the controls at all times. This is not possible to achieve in Cloud add-on as it's rendered in an iframe.
  * You cannot impersonate any JIRA user when calling JIRA REST API from the server. Because of that, searching for issues has to take place in the client. This is not how I originally imagined it working.

## Lessons learned

* This was one of the **largest personal projects** I worked on. It takes a lot more effort to get it done and release than it initially looks like. It took about 3 months from inception until all the assets and copy for Atlassian Marketplace release were ready.
* Atlassian Connect API
