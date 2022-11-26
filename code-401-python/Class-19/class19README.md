## What is the Django?

Django is a Python-based web framework used by millions of developers and billions of consumers through popular apps like Instagram. It is open source, meaning the 
code is available for free on Github and can be downloaded onto any developer’s computer and used alongside the official documentation. However, I find that even 
professional Django developers have little insight into “how” Django is actually run, both technically and legally/financially, so this post is my attempt to provide 
a concise overview of it all.


### As with all open source projects, the two major issues that crop up are funding and control.


There are a host of decidedly less fun tasks needed to maintain and sustain an open source project rather than writing a code, This includes handling any legal/trademark issues, triaging tickets, guiding community discussions, organizing conferences, managing releases, and so on. As a result, almost all popular open source packages have some degree of funding involved, typically in one of three forms:


#### 1.Corporate Sponsor

A group of engineers within a larger, for-profit company decide to open-source internal code. This is how React (Facebook) and Angular (Google) emerged.

#### 2.Solo

An individual developer initially creates code, open sources it, and retains default control. This is the case for VueJS, Tailwind CSS, and Laravel, among others.


#### 3.Non-profit 

This was Django’s approach early on, in 2008, when the Django Software Foundation was formed to promote, support, and advance Django.


## Django Software Foundation (DSF)

The DSF supports and maintains Django in a number of capacities. The largest expense, by far, is the Fellows Program, paid contractors who triage tickets, manage releases, and generally perform the unsexy but necessary work needed to keep Django on track.
The Django Fellows do incredible, behind-the-scenes work for the community. 


The DSF also supports projects related to Django such as the Kickstarters for Django REST Framework 3, improved PostgreSQL support, among others. It supports related conferences that promote Django and provides funding to extend access to a diverse group of developers. Manages things such as the recent redesign of the main Django website, and more. You can see a 2014 roundup for a broader sense.

The majority of any Django professionally used should goes to the Django Fellows who ensure the project remains on track and the rest helps promote Django and expand its community. The total budget for the DSF in 2019 is around $200,000, or less than the cost of a single Bay Area Django engineer.




## Technical Organization

Django followed Python’s model of having a Benevolent Dictator for Life, that is, a project founder who retained final say for disputes/arguments within the community.


Django has a small, core team of trusted volunteers who work alongside the Django Fellows to manage technical side of the Django Project. Django Core members are divided into teams that have authority over the Django Project infrastructure, including the Django Project website itself, the official issue tracker, official mailing lists, IRC channels, and more. There is currently ongoing discussion around potentially dissolving Django core or updating it in a meaningful way.


 
