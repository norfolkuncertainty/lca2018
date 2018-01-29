# Day 3
## Keynote: Six Years Later, or Hey, did you ever get the source code to that thing in your heart? - Karen Sandler
Karen started by giving a review of her key note 6 years ago
She was diagnosed with an enlarged heard, and needed to have a pace maker/defriblator instaled to shock her heart if it goes into an irregular rhythm.
She wanted the software for her pacemaker, so she could review it for bugs/insecurities
It turns out she was the first person to ask this question.
She didnt end up getting source code after extreme measures to try and get it.
Devices have closed software, but broadcasting remotely
DCMA meant it was criminal to even try to test device

She described her defribulator as a metephor for all of the electronic devices (smart cars, smart coffee machines etc)
This helps people to understand the issue better.
Episodes on NCIS and homeland about pacemaker hacks have raised a lot more awareness around this.
She found it more effective talking about it when people knew she had a pacemaker
Karen has been accused of being a conspiracy theorist, just for asking questions.

More and more vulnerabilites are beign discovered for medical devices (insulin pumps, pacemakers)
Johnson and Johnson worked to fix vuln and communicate it out very well where it has been delt with not so well by other vendors.

When Karen was pregnant her heart did what pregnant womens heats do and started palpatating.
The pacemaker/defribulator noticed this and shocked her
She wasprescribed drugs to slow her heart so she wouldnt get shocked
such a small subset of pacemaker wearers are pregrnant women that this was not anticipated.
Which leads to the question, are pharma companies anticipating of all possible usecases
We need commercial entities to engage. All of our software should be free and open over time 

Because of the shocks during pregnancy, her pacemaker started beeping every day at 1:10pm, the battery was getting low.
Wireless was enabled by default and was unable to disable on all of the new pacemaker/defribulators
This was a major concert for Karen, as she has been threatend by people beacuse of her outreachy work...wtf is wrong with people?
Karen and a nurse called a number of vendors to check if they had a none wireless model
They had a number of different reponses, from Karen not being allowed to listen to the response to "Our device is hack proof"
Luckily they managed to get the one device from Europe that used magnetic coupling
Working with the small european company, so looks promising to get sourcecode

Everyone is using proprietary software wheather they like it or not

## How to run Kubernetes on your spare hardware at home, and save the world - Angus Lees
PCs are falible,  We use distributed software to get around this
We have gone from clever hardware to clever software
From 1 pc for many users to 1 user on many pcs
rpc microservices, hadoop, key/value store, object stores, immutable image based
If its important, its not on 1 server
centrlise services vs federated protocols
kubernetes can be described as "unix process as a service"
pod is 1 or more containers, kubernetes ensures they are created and destroyed together with a shared network (ie localhost is the same on both containers)
human -> api server -> etcd store
scheduler talks to api server and checks if it is as it should be
each node has a subnet allocated from the parent netblock
each pod has an IP allocated
hardware is least important, data is more important now

Example command
kubctl run my-nginx --image=nginx --replicas=2 --port=80

Angus' setup:
masters 3 arm machines
hardware worker nodes old laptops
containOS - his own OS
persistent volumes provided via NFS - dynamically provisioned
keepalived vip 
wildcard dns

github anguslees
github/containos


## More crazy flying machines - CanberraUAV and ArduPilot - Andrew Tridgell
Another excellent presentation from Andrew about his adventures with UAV's
Definitley worth a watch

Skyviper v2450 was mentioned as the cheapest open devices to get into UAVs wit

## XFS: Teaching an Old Dog Old Tricks - Dave Chinner
xfs is the original btree filesystem
effectively everything in xfs is btree
COW file systems require a massive amount of updates for each change
rewrites the tree after each write
COW in XFS is data only
uses defered operations to improve crash recovery
Allows replay of COW operations to ensure consistency
Dave has been investigating adding subvolumes to xfs
definition of a subvolume - can be snapshotted, flexible capacity, fully functioning filesytem
There have been a number of ideas on how these can be implemented
A combination of subvol using bind mount, cp reflink, tar/rsync
Ideally a subvolume needs to be its own vfs entity rather than having to hack it into mount options
ENOSPC is a problem if the parent device runs out of space which can cause filesystem corruption on the child filesystem.
If the layers talk to each other, then this should not be an issue.
The proposal that Dave is working on at the moment is image files on host filesystem
This should resolve all of the above issues and also allowd shared cache between data on disk.
Subvolume encrytion would be trivial with this model too.

## A Brief History of I/O - Benno Rice
Excellent overview of I/O
"Every single component of your computer is internally a packetised switched network"

## Creating open data about Australia’s local councillors: Our Outreachy Internship 2017 - Hisayo Horie, Luke Bacon
Hisayo was the lucky recipient of the outreachy internship in 2017
This talk was an overview of the outreachy program and its entry criteria.
Hisayo went on to summarise her year, which was very interesting.

