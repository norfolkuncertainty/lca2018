# Day 4

## Keynote: Wandering through the Commons - Hugh Blemings
A history of Hugh's career and some very sound advise on job hunting

## Panel: Meltdown, Spectre, and the free-software community - Jonathan Corbet, Andrew 'bunnie' Huang, Benno Rice, Jess Frazelle, Katie McLaughlin, Kees Cook
An inside view of how the embargo was handled and what affects it had on people/companies.
Really nice to hear the views of senior technical leaders.

## micro-Linux init (PID1) in Golang - Sven Dowideit
Requires a fast booting minimal immutable microLinux to run containers on
RancherOS - everything is container (ntp, logging etc)
host config driven by cloud-init
benefits
boot times, security footprint, immutable infrastucture, heading to unikernels
linuxkit
A toolkit for building secure, portable and lean operating systems for containers

## Personalisation at Scale: A “Cookie Cutter” Approach -  Jim O'Halloran
App servers are generally cpu bound
this can be helped with full page cache with varnish etc
cache hit vs cache miss - huge difference in response times
cachable requests do not modify state
personalised data cannot be part of full page cache

Edge side include
View mark up to see what is excluded in full page cache
ESI requests are run in series, not parellel
negates benefits of using varnish

ajax request
can be done in paralell
still have to run on each page load
There will be delayed load times for these components, not a good ux

Dont cache
"hard to cache pages" - eg logged in, items in cart

excluding specific parts from the cache is referred to as hole punching

Cookie cutter approach
JavaScript uses the conent of a cookie to update the page

How big can a cookie be?
4k of data in 50 cookies per domain
Browsers differ in their cookie size limits
most new brosers are good, buts some older ones limit to 4k total

Keep cookies small
serve static assets via cdn

Use ajax requests for cart items, not displayed on every page, just when people click on the cart menu

There is some information leak with this approach
The url to logged in users is in the html source
However, the backend still validates whether the customer is logged in

Another technique that can be used is to vary the header to split cache based on customer type or country

## Geographically distributed multi-master replication with PostgreSQL and BDR -Craig Ringer
There are different types of multimaster
Do not use automatic promote unless you regularaly test this in production, as you will end up with split brain/divergence
Do not use dns based connection redirection, different clients will take different time to pick up the DNS change which could cause issues.
Using a proxy infront like HAproxy is a better idea
script the repair process for divergence/split brain if possible.
Multimaster suitable for some situations, like metrics gathering where these is less likelyhood of two different servers updating the same item with different values
In these cases divergence can be resolved when connectivity is restored
Not cool if there is the possibility of the same row being updated by two masters
Multimaster requires additional design considerations
*Requirements anaylsis is crucial*
tightly coupled vs loosley coupled
shared storage vs independent
sync vs async

tightly coupled doesnt work very well with high latency

The application needs to be able to handle conflicts in loosley coupled systems
The application must be changed if it cant cope 


## IPv6 and Containers: Why We Can't Have Nice Things (And How We Can) - Matt Palmer
router advertisements 
- used to find default router on a network
- can also advertise a route for a subnet
- fundamental feature of ipv6
radv daemon can perform this action on Linux

ipv6 is ideal for containers, but not ready for prod yet.
Their current setup is a home rolled solutions, not really supported on kubernetes yet.

For people that are concerned with having the internet connect to your container directly, he recommended reading:
Beyondcorp -  a new approach to enterprise securty
https://research.google.com/pubs/pub43231.html

Traditional layered security model is "egg shell security" - hard on the outside, soft on the inside

## Insights - solving every problem for good - Paul Wayper
Python based
scrapes logs and files, and runs commands
Scans files for all tokens at once rather than repeatdly searching through files for each token.

Produces suggestions to fix known errors.

Very keen to get community involvment and have people writing their own plugins

http://insights-core.readthedocs.io/en/latest/
https://github.com/RedHatInsights
https://github.com/PaulWay/insights-installer



