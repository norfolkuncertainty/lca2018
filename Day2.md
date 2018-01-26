# Day 2

## Keynote
Matthew Todd - Opensoure drug discovery
Matthew talked about Open source malaria

Matthew discussed  possible names for opensource drug discovery, "Opensoure pharma" was a possibility, "free drugs" might have the wrong connitations

There was a pill in 
Awful arasite trying to create pil,chucked it up online
grant from govt and who, featured in magazine
Private sector contributed
Private company was working on it at the same time
Open innovation - problem is only publicdomain
Open source - solution is also ublic domain

hit -> lead
gsk releasing molecules that kill malaria

electronic lab notebook, people still using paper and pens

github.com/opensourcemalaria

Suspecting that the oucule restricts the ion pump of the malaria

crowd sourced competition to figure out whihc molecule is going to work
Unfortunately none were predictive.

Big pharama cant do open source, but the scientists want to do it.

toxoplasmosis drug, massive price increase overnihgt
school kids replicated it 

need all info in machine digstable format

trust and transparancy - open kitchen, open symphony

Next steps
Clinical trials
first ever open molecule if they get to clinical trials

scindr 
competitor to tinder to find scientist collaboration possiblities
SCINDR - Tindr for scientists.  Automatically find possible collaborations based on who's working on same/similar molecules

Mycetoma, fungus that grows in the same place as tatoo ink goes
They are starting a new opensource compaign for this

Huge money goes into opensource, but none of this stuff is happening in pharma
He would like to see similar to the law society where you have to do probono work to be a member

Dont have to patent the drug, you can get data exclusivity which allows you to see it exclusively for 6 years.

# Sysadmin miniconf

## Day 2 Operations with Containers: Myth vs. Reality - Elizabeth K. Joseph
Containers are not as simple as they sound
Lots of layers, networks etc to worry about
Myth 1  Containers will solve all of your problems
Does give you HA out of the box
Reality - You still have to maintain
upgrades, backups, debugging (ensure logs are captured)

Myth 2 - Green fields
Reality Legacy tooling/infrastructure
Focus ona  standards base imolementaton

Myth 3 Everything is automated for you already
Relaity you need loging, metrics and monitoring
centralised logging
Using collectd 
Sysdig - tool for integrated metrics
 
Myth4 No more planning
Reality
Thing will go wrong, you need to plan ahead
capacity, logging
Ensure these are included in phase1, not left till phase 2

Checklist

Plan
- host, container, application
- upgrade stretegy
- backups
- DR - Ensure this is tested
- metics, collections, monitoring
- centralised logging

## Designing scalable production Kubernetes clusters on AWS - Nick Young
ltlassian running 12 factor apps on AWS
Design out the biggest problems you know about so you can find the new and interesting ones later on
Strong isolation between layers
-Flag
AWS config, VPC, Security groups
-Karr
Computer and etcd
-Goliath
All configs that run Kubernetes

Cattle not pets
Controller nodes - completely replacable
etcd nodes - Petty Cattle
Can burn down to FLAG and rebuild in 30mins

Manage dependencies
Secrets stored in private s3 bucket
Image store - ECR (AWS) as dont want to rely on anything outside of AWS

Service Meshes - What is this?
tl;dr: A service mesh is a dedicated infrastructure layer for making service-to-service communication safe, fast, and reliable. If you’re building a cloud native application, you need a service mesh!

## Becoming the Admiral: mastering Docker orchestration - Alistair Chapman
Need to manage container sprawl
Hard to be able to managing logging monlith and containers
combination of service logging for containers
Dokly - https://github.com/lirantal/dockly
docker top <container name>
Dont trust the internet - Dont download random containers off the internet
Flaco - https://www.sysdig.org/falco/
Analyse container behaviour
capsule8 - https://capsule8.com/

YOu need to integrate containers with your exisitng infrastructure
Build stack around both side of your infra

## Migrating to the cloud - Devdas Bhagat


## Puppet in the cloud - Jethro Carr
using ec2 tags to set role
auto signing can lead to information leekage
policy base auto signer
use a single use token
No reference implementation
jwt tokens?
facts are not trusted s they can be chaned
So could use the role fact to steal information from other roles
Trusted facts are baked into the cert
Carnival r10k webhook
Share config to all puppet masters, use efs
certificates need to be distributed across all puppet masters

## User Session Recording for the Enterprise - Fraser Tweedale
Record shell sessions
Record terminal IO
Propmpt secure centralised logging
log kernel audit events
Search and play back
Centralised control

tlog
session initated goes through tlog and stream to location
tlog-play allows you to play back

Stored in json format

aushape turns audit events into json for easier readibility/processing

possibly integration with cockpit webui for playback

Will be attached to HBAC rules in IPA

scribery.github.io

## Monitoring All the Things! on your Linux system with the Elastic Stack - Josh Rich
Kibana, Elasticsearch, Beats, Logstash

Metric beat
reads local data sources
sends to ES
Can consume many local services
binary + a few configs

Elastci search has been enhanced to store numbers/metrics better

TSVB is a metrics visualiser in kibana - time series visual builder

More beats, packetbeats, file beat, heartbeat, audit beat

Prebuilt dashboards

https://github.com/elastic/examples/tree/master/Miscellaneous/docker/full_stack_example

elastalert can do alerting

## Icinga 2 in a 24/7 Television Broadcast Environment - Dave Kempe
json config 
can add variables to hosts
monitoring overview dashboard
Maps plugin

## Principles Of Good Monitoring - Troy Lea
Active - Monitoring system checks
Passive - Clinet sends info
active - YOull find out when next check occurs
passive - alert is sent to monitoring systme

Nagios core can do both

extensible through plugins, easy to write

Moniroing your monitoing system

Backup your moniutoring system

how does monitiung git into 


