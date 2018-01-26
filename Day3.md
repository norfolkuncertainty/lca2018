# Day 3
## Keynote: Six Years Later, or Hey, did you ever get the source code to that thing in your heart? - Karen Sandler
Pace maker shocks heart if it goes into irregular rhythm
Wanted the software for her pacemaker
first person to ask
didnt end up getting source code after extreme measures to try and get it
defribulator is a metephor for all of the electronic devices (cars etc)
Devices have closed software, but broadcasting remotely
DCMA meant it was criminal to even try to test device
more and more vulns for medical devices (insulin pumps, pacemakers)
accused of being a conspiracy theorist
Johnson and Johnson worked to fix vuln and communicate it out
episodes on NCIS and homeland about pacemaker hacks, a lot more awareness because of this
more effective talking about it when people knew she had a pacemaker
such a small subset of pacemaker wearers are pregrnant women
prescribed drugs to slow heart so she wouldnt get shocked during pregnancy due to heart palpatations
are pharma companies anticipating of all possible usecases
We need commercial entities to engage... All of our software should be free and open over time 
Started beeping every day at 1:10pm - battery was going low
Battery was going flat
wireless was enabled by default, was unable to disable on new pacemakers
gets threatend by people for her outreachy work...wtf is wrong with people?
"Our device is hack proof"
Managed to get the one device from Europe that used magnetic coupling
Everyone is using proprietary software wheather they like it or not
Working with the small european company, so looks promising to get sourcecode

## How to run Kubernetes on your spare hardware at home, and save the world - Angus Lees
PCs are falible, distributed software to get around this
from clever hardware to clever software
rpcmicroservices, hadoop, key/value store, object stores, immutable image basedif its important, its not on 1 server
from 1 pc to many users to 1 user to many pcs
centrlise services vs federated protocols
"unix process as a service"
pod is 1 or more containers, kubernetes ensures they are created and destroyed together with a shared network (ie localhost is the same on both containers)
human -> api sevrer -> etcd store
scheduler talks to api server and checks if it is as it should be
each node has a subnet allocated from the parent netblock
each pod has an IP allocated
hardware is least important, data is more important now
kubctl run my-nginx --image=nginx --replicas=2 --port=80

masters 3 arm machines
hardware worker nodes old laptops
containOS - his own OS
persisten volumes provided via NFS - dynamically provisioned
keepalived vip 
wildcard dns

github anguslees
github/containos


## More crazy flying machines - CanberraUAV and ArduPilot - Andrew Tridgell
Skyviper v2450 - 

## XFS: Teaching an Old Dog Old Tricks - Dave Chinner
origional btree filesystem
btree all the things
COW file systems require a massive amount of updates for each change
rewrites the tree after each write
COW in XFS is data only
uses defered operations to improve crash recovery
Allows replay of COW operations to ensure consistency
Adding subvolumes
definition of a subvolume - can be snapshotted, flexible capacity, fully functioning filesytem
subvol using bind mount, cp reflink, tar/rsync
subvolume needs to be its own vfs entity
ENOSPC is a problem if the parent device runs out of space
layers need to talk to each other
image files on host filesystem
shared cache between data on disk
subvolume encrytion

## A Brief History of I/O - Benno Rice
blocking i/o doesnt return until its done
At this point, Benno Rice’s talk on I/O is basically that every single component of your computer is internally a packetised switched network. #lca2018

## Creating open data about Australia’s local councillors: Our Outreachy Internship 2017 - Hisayo Horie, Luke Bacon

