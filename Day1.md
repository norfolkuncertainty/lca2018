# Day 1

## Opening

## Hw Miniconf

## Turning stories into software - Donna Benjamin

User Story:
As a user, I require XXX so i can XXX

Where do they come from?
-Workshops
Lots of sticky notes
-Interviews
1 on 1s
Use the 5 Why's to get to the real reason behind the requirements
-Surveys
Broaden target group to get a consensus/trend
-Competitive analysis
Compare a whole bunch to find common features
-Prototype and iterate
Fast feedback

Invest pnemonic
Independant - No depedencies, can we release the by itsself
Negotiable - 
Valuable - Does it add value
Estimable 
Small -
Testable - 

A couple of books
User stories Applied
User story mapping - Jeff Patton

Group dynamics
Forming storming norming performing -check online for correct this

Cynefin (welsh word)
The habitat
Obivious - stuff you know and understand
Complicated - need experts/analysis
Complex - May require a spike
Chaotic - Emergency

The agile manifesto condensed:
People collaborate, Product evolves

## Next Generation Config Mgmt: Resources - James Shubin
purpleidea.com/blog
DO reinvnet the wheel
mgmtconfig
Engine and language
paralelle execution
event driven
distributed topology
Reactive tool, sees files being delete and fixed them up immeditly. file created before you can ls it
safe 
powerful 
easy to reason with

Written in golang


## Manage all your tasks with TaskWarrior - Paul '@pjf' Fenwick

Can add features
Command line based
Most task systems dont work for most people
Work flow agnostic
Steep learing curve
task add
task 1 done
task numbers change as they get ticked off
can add tags to tasks
Meta tags autonattical added
+YEAR, +WEEK +TODAY  (is it due by x)
Negative tage searching 
Heirachical - many tasks per project
project:travel.stuff.thing

Contexts can we used to split work/home, switch between projects

Taking notes on tasks is called annotation 

Can hide tasks until certain dates
Schedule tasks  urgency boosted after duedate
until - delete task after date
Can schedule relative to other tasks
Urgency score calculated by deadlines,tags etc
Totally configurable
Priority - high medium low none
taskwarrior.rc to set defaults

plugins
can annotate with urls and it will open with browser

Bug warrior - access to github,trello,jira,gmail
Set tags on trello takss based on board/who its assigned to

Shell prompt integration
Get a copy of his psa, looks pretty amazing

burn down graph reporting
calendar
yaml export
Build your own reports
Recurring tasks
android app
inthe.am - web version

Dependency support

Not written in perl

https://github.com/pjf/talks/tree/master/taskwarrior

## Love thy future self: making your systems ops-friendly - Matt Palmer

Metrics are key

Add guages/metrics to everything so you can see what "magic" is happening
Instrumentation: The first four things to measure
Incoming requetss
count the number/type
how many responses success/error
Measure timings success/error
How many you arehandling right now

Whats does it mean?
Drop in requests recieved
- upstream issues
Increase request rate
- Getting hammered - why?

Responses sent
-Increase error rate - issue here, or downstream
Increase in time - issue here or downstream

Inprogress
Increase  - weird
Inprogressdoesnt match recieved vs responses

outgoing requests
Requests sent/recieved success/error
How long to get response error/success
Outstanding requets

Drop in incoming/outgoing - we are not making the requests

responses recieved
error rate - downstream
time taken increase - Downstream has slowed down

Where ^

Why - Logs
Three log priorities that really matter
ERROR
INFO
DEBUG

Error
Full stacktrace on Errors
Add info, dont replace
Capture all relevant variables, envrionment etc
Stuctured log data, not huge lines of txt

INFO
Startup

DEBUG
printf debugging
Tag with module and method
Create uniq id for each top level request
Late-bind the log data
Allow selective activation

Make it Visibility
Instrument it
Logerrors all the time
Allow runtime collection of debug logs

## Using "old skool" Free tools to easily publish API documentation - Alec Clews

https://github.com/alecthegeek/doc-api-old-skool

People want to use yoiur API

Make it useful, easy with great docs
Keep doco up to date

Users may not have English as a firsh language

Users are not familiar with your api and may not have the same technical skills as you

Use pictures and show real full code examples

Dont use complex english and dont make your doco busy

Treat your documentation as code

Pandoc can generate pdfs from markdown files

Plantuml to generate a digram, you can then reference this diagram in your markdown
Uses sed to extract lines from the code, and then inset this into his doc

## Lightening talks
### To alt or not to alt
Alt attribute allows you put a text desciption of the image
For instance blind people using a screen reader will only hear "Image" where you have your pic. 
Need to decide if the picture is informative or decorative as to whether to include it or not

### lua
Better then javascript
http://fengari.io
Can be used in the browser
Can do everything Javascript can do
Learn lua in 15mins - http://tylerneylon.com/a/learn-lua/

### How not to docker
Do not run privelidged - Can own machine
Dont expose docker socket - Can mount host filesystem
Dont use host network mode - container can have complete control over host network
Know where your code is From - dont use random images
Dont forget your host - Ensure host has a secure kernel



