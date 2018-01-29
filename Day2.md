# Day 2

## Keynote
Matthew Todd - Opensoure drug discovery
Matthew talked about openly reasearching drugs to find a cure for malaria
Coming up with a name for this approach was difficult, "free drugs" might have the wrong connitations

Open innovation - problem is only publicdomain
Open source - solution is also public domain

gsk releasing their lists of molecules that kill malaria
All need to be tested to see if they are toxic, or are processed by the human body before they reach the virus.

Scientists are still using paper and pens
electronic lab notebook is helping them get their research online so its available for others to use

github.com/opensourcemalaria

One very promising molecule
Suspecting that the moucule restricts the ion pump of the malaria which it uses to regulate its environments in the red blood cell

They launched a crowd sourcing competition to predict which molecule is going to work
Unfortunately none were predictive.

Big pharama cant do open source as it doesnt fit their business model, but the scientists want to do it.

The toxoplasmosis drug Daraprim had a massive price increase overnight and made the news.
A group from a school managed to create a small amount of the drug in their lab
This proved that it was not hard to make the drug, and that the price hike was just in the name of money making
Matthew mentioned that it was a "Primo" version of the moecule, they had done an excellent job.

For all of the research, they really need the information in a machine digstable format

trust and transparancy - open kitchen, open symphony

Next steps
Clinical trials
It will be the first ever open molecule if they get to clinical trials

SCINDR - Tindr for scientists.  Automatically find possible collaborations based on who's working on same/similar molecules

Mycetoma, fungus that grows in the same place as tatoo ink goes
Probably dont do an image search unless you are feeling brave
They are starting a new opensource compaign for this

Huge money goes into opensource, but nothing similar is happening in pharma
He would like to see similar to the law society where you have to do probono work to be a member

Drug patents are not as important as they are made out to be, you can get data exclusivity which allows you to sell it exclusively for 6 years.
This is reward for doing the clinical trials.

# Sysadmin miniconf

## Day 2 Operations with Containers: Myth vs. Reality - Elizabeth K. Joseph
Containers are not as simple as they sound
Lots of layers, networks etc to worry about

Myth 1 - Containers will solve all of your problems
Reality - You still have to maintain upgrades, backups, debugging (ensure logs are captured)

Myth 2 - Green fields
Reality Legacy tooling/infrastructure
Focus on a standards based implementaton

Myth 3 - Everything is automated for you already
Reality you need logging, metrics and monitoring
centralised logging
Using collectd 
Sysdig - tool for integrated metrics
 
Myth4 - No more planning
Reality Thing will go wrong, you need to plan ahead for capacity, logging
Ensure these are included in phase 1, not left till phase 2

Container planning Checklist
- host, container, application
- upgrade stretegy
- backups
- DR - Ensure this is tested
- metics, collections, monitoring
- centralised logging

## Designing scalable production Kubernetes clusters on AWS - Nick Young
atlassian running 12 factor apps on AWS
Design out the biggest problems you know about so you can find the new and interesting ones later on
Strong isolation between layers
3 layers
-Flag
AWS config, VPC, Security groups
-Karr
Computer and etcd
-Goliath
All configs that run Kubernetes

Cattle not pets
Controller nodes - completely replacable
etcd nodes - Petty Cattle, controled replacement is possible
Can burn down to FLAG and rebuild in 30mins

Manage dependencies
Secrets stored in private s3 bucket (not external to aws)
Image store - ECR (AWS) as dont want to rely on anything outside of AWS

Service Meshes - What is this?
tl;dr: A service mesh is a dedicated infrastructure layer for making service-to-service communication safe, fast, and reliable. If you’re building a cloud native application, you need a service mesh!

## Becoming the Admiral: mastering Docker orchestration - Alistair Chapman
Need to manage container sprawl
Hard to be able to managing logging monlith and containers
combination of service logging for containers and standard logging for monolith
Dokly - https://github.com/lirantal/dockly
Troubleshooting docker requires new tools
docker top <container name>
Dont trust the internet - Dont download random containers off the internet
Flaco - https://www.sysdig.org/falco/
Analyse container behaviour
capsule8 - https://capsule8.com/

You need to integrate containers with your exisitng infrastructure
Build stack around both sides of your infra

## Migrating to the cloud - Devdas Bhagat


## Puppet in the cloud - Jethro Carr
using ec2 tags to set role
auto signing can lead to information leekage
Use of policy base auto signing is an option
Could use a single use token
There is no reference implementation from Puppet around this
jwt tokens were mentioned as another option.
facts should not trusted as they can be chaned
So could use the role fact to steal information from other roles
Trusted facts are baked into the cert and are relitively unknown feature.
Carnival r10k webhook
Share config to all puppet masters, use efs
certificates need to be distributed across all puppet masters

## User Session Recording for the Enterprise - Fraser Tweedale
Record shell sessions
Record terminal IO
Prompt secure centralised logging
log kernel audit events
Search and play back
Centralised control

tlog
pam session initated, goes through tlog and stream to location (journald, rsyslog)
From there it can be pushed into centralised logging for analysis

It has a number of features including rate limiting when people cat large files.
Could this be abused to hide commands?

tlog-play allows you to play back a session

Stored in json format

aushape turns audit events into json for easier readibility/processing

possibly integration with cockpit webui for playback

Will be attached to HBAC rules in IPA

scribery.github.io

Will potentially be released

## Monitoring All the Things! on your Linux system with the Elastic Stack - Josh Rich
Kibana, Elasticsearch, Beats, Logstash

Metric beat
reads local data sources
sends to ES
Can consume many local services
binary + a few configs

Elastic search has been enhanced to store numbers/metrics better
TSVB is a metrics visualiser in kibana - time series visual builder

More beats, packetbeats, file beat, heartbeat, audit beat

Prebuilt dashboards

https://github.com/elastic/examples/tree/master/Miscellaneous/docker/full_stack_example

elastalert can do alerting with dynamic threshholds and parent child relationships to avoid alerting storms

Quick local example
docker run -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" --name elasticsearch docker.elastic.co/elasticsearch/elasticsearch-oss:6.1.1
docker run -p 5601:5601 --name kibana --link elasticsearch docker.elastic.co/kibana/kibana-oss:6.1.1
docker run --volume="/proc:/hostfs/proc:ro" --volume="/sys/fs/cgroup:/hostfs/sys/fs/cgroup:ro" --volume="/:/hostfs:ro" --net=host --name metricbeat docker.elastic.co/beats/metricbeat:6.1.1 -system.hostfs=/hostfs -E output.elasticsearch.hosts="[http://localhost:9200]" -setup
Only need to run the setup the first time

## Icinga 2 in a 24/7 Television Broadcast Environment - Dave Kempe
json config 
can add variables to hosts
monitoring overview dashboard
Maps plugin

## Principles Of Good Monitoring - Troy Lea
Active - Monitoring system checks, Youll find out when next check occurs
Passive - Client sends info, alert is sent to monitoring system

Nagios core can do both

extensible through plugins, easy to write

Ensure you monitor your monitoring system

Backup your monitoring system
