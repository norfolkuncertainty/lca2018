# Day 4

## Keynote: Wandering through the Commons - Hugh Blemings

## Panel: Meltdown, Spectre, and the free-software community - Jonathan Corbet, Andrew 'bunnie' Huang, Benno Rice, Jess Frazelle, Katie McLaughlin, Kees Cook

## micro-Linux init (PID1) in Golang - Sven Dowideit
Requires a fast booting minimal immutable microLinux to run containers on
RancherOS - everything is container (ntp, logging etc)
host config driven by cloud-init
benefits
boot times, security footprint, immutable infrastucture, heading to unikernels
linuxkit
A toolkit for building secure, portable and lean operating systems for containers

## Personalisation at Scale: A “Cookie Cutter” Approach -  Jim O'Halloran
App server is cpu bound
full page cache with varnish etc
cache hit vs cache miss - huge difference
cachable requests do not modify state
personalised data cannot be full page cache

Edge side include
mark up to show what is excluded in full page cache
ESI requests are run in series, not parellel
negates benefits of using varnish

ajax request
can be done in paralell
still have to run on each page load
delayed load times for these components, not a good ux

Dont cache
"hard to cache pages" - eg logged in, items in cart

^ hole punching

Cookie cutter
JavaScript uses the conent of a cookie to update the page

How big can a cookie be?
4k of data in 50 cookies per domain
Browsers differ in their cookie size limits
most new brosers are good, buts some older ones limit to 4096b total

Keep cookies small
serve static assets via cdn

ajax requests for cart items, not displayed on every page, just when people click on the cart menu

information leak
url to logged in users in html source
backend still validates customer is loggedin

vary header to split cache based on customer type or country

## Geographically distributed multi-master replication with PostgreSQL and BDR -Craig Ringer
Differenttypes of multimaster
Do not use automatic promote as you will end up with split brain/divergence
Do not use dns based connection redirection
Use a proxy infront
script the repair process
multimaster suitable for some situations, like metrics gatherine
Then divergence can be resolved when connectivity is restored
Not cool if there is the possibility of the same row being updated by two masters
Multimaster requires additional design considerations
*Requirements anaylsis is crucial*
tightly coupled vs loosley coupled
shared storage vs independent
sync vs async

tightly coupled doesnt work very well with high latency

need to be able to handle conflicts in loosley coupled systems
application must be changed if it cant cope 

distributed primary keys

*Things programmers should know about names*

## IPv6 and Containers: Why We Can't Have Nice Things (And How We Can) - Matt Palmer
host portion of IP drived from mac
/64 for edge boxes

router advertisements 
- used to find default router on a network
- can also advertise a route for a subnet
- fundamental feature of ipv6
radv daemon on Linux

DirectConnect advantages
Less config
less state
less moving parts

egg shell security - hard on the outside, soft on the inside
Beyondcorp -  a new approach to enterprise securty

## Insights - solving every problem for good - Paul Wayper
Python based
scrapes logs and files, and runs commands
Scans files for all tokens at once rather than repeatdly searching through files for each token.
http://insights-core.readthedocs.io/en/latest/

https://github.com/RedHatInsights
https://github.com/PaulWay/insights-installer



