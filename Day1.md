# Day 1

## Opening

## Hw Miniconf

Assisted with building the lollibot, great kit to put together.

## Turning stories into software - Donna Benjamin

User Story:
As a user, I require XXX so i can XXX

Where do they come from?

* Workshops
  * Lots of sticky notes
* Interviews
  * 1 on 1s
  * Use the 5 Why's to get to the real reason behind the requirements
* Surveys
  * Broaden target group to get a consensus/trend
* Competitive analysis
  * Compare a whole bunch to find common features
* Prototype and iterate
  * Fast feedback

Invest mnemonic

* Independent - No dependencies, can we release the by its self
* Negotiable -
* Valuable - Does it add value
* Estimable
* Small -
* Testable -

A couple of books

[User stories Applied](https://www.mountaingoatsoftware.com/books/user-stories-applied)

[User story mapping - Jeff Patton](http://shop.oreilly.com/product/0636920033851.do)

Group dynamics

[Forming storming norming performing](https://www.mindtools.com/pages/article/newLDR_86.htm)

[Cynefin framework](https://en.wikipedia.org/wiki/Cynefin_framework)

The habitat

* Obvious - stuff you know and understand
* Complicated - need experts/analysis
* Complex - May require a spike
* Chaotic - Emergency

The agile manifesto condensed:
People collaborate, Product evolves

## Next Generation Config Mgmt: Resources - James Shubin

[James' Blog](https://purpleidea.com/blog/)

DO reinvent the wheel

mgmtconfig 

* parallel execution
* event driven
* distributed topology
* Reactive tool, sees files being delete and fixed them up immediately. file created before you can ls it
* safe 
* powerful 
* easy to reason with
* Written in Golan

Looks interesting, but will be hard to get people on board without the ecosystem to support it.

## Manage all your tasks with TaskWarrior - Paul '@pjf' Fenwick

Most task systems don't work for most people

[slides](https://github.com/pjf/talks/tree/master/taskwarrior)

* Task warrior is open source , so you can add features
* Command line based
* Work flow agnostic
* Steep learning curve
* can add tags to tasks
* Meta tags automatically added
* Supports native+YEAR, +WEEK +TODAY  (is it due by x)
* Negative tag searching 
* Hierarchical - many tasks per project
  * project:travel.stuff.thing
* task numbers change as they get ticked off
* Contexts can be used to split work/home, switch between projects
* Taking notes on tasks is called annotation 
* Can hide tasks until certain dates
* You can Schedule tasks, and the urgency boosted after due date
* If you set an "until", the task will be deleted after the date
* Can schedule relative to other tasks
* Urgency score calculated by deadlines,tags etc
* Totally configurable
* Priority - high medium low none
* taskwarrior.rc to set defaults
* Dependency support

Plugins

* can annotate with URLs and it will open with browser
* Bug warrior - access to GitHub,trello,jira,gmail
  * Set tags on trello tasks based on board/who its assigned to
* Shell prompt integration
  * Pauls PS1 looked pretty awesome, keen to get a copy
* burn down graph reporting
* calendar
* yaml export
* Build your own reports
* Recurring tasks

android app

[Web version](http://inthe.am)

Not written in Perl


## Love thy future self: making your systems ops-friendly - Matt Palmer

Metrics are key

Add gauges/metrics to everything so you can see what "magic" is happening

Instrumentation: The first four things to measure 

* Incoming requests
* Responses sent
* Outgoing requests
* Responses received

These will show you WHERE the issue is

* count the number/type
* how many responses success/error
* Measure timings success/error
* How many you are handling right now

To find out WHY logs are your friend

Three log priorities that really matter

* ERROR
* INFO
* DEBUG

Error requirements

* Full stack trace on Errors
* Add info, don't replace
* Capture all relevant variables, environment etc
* Structured log data, not huge lines of txt

INFO

* Startup

DEBUG

* printf debugging
* Tag with module and method
* Create unique id for each top level request
* Late-bind the log data
* Allow selective activation

Make it Visibility
* Instrument it
* Log errors all the time
* Allow run time collection of debug logs

## Using "old skool" Free tools to easily publish API documentation - Alec Clews

[slides](https://github.com/alecthegeek/doc-api-old-skool)

People want to use your API

Make it useful, easy with great docs
* Keep doco up to date
* Users may not have English as a first language
* Users are not familiar with your API and may not have the same technical skills as you
* Use pictures and show real full code examples
* Don't use complex English and don't make your doco busy
* Treat your documentation as code
* Pandoc can generate pdfs from markdown files
* Plantuml to generate a diagram, you can then reference this diagram in your markdown
* Uses sed to extract lines from the code, and then insert this into his doc

## Lightening talks
### To alt or not to alt

Alt attribute allows you put a text description of the image

For instance blind people using a screen reader will only hear "Image" where you have your pic. 

Need to decide if the picture is informative or decorative as to whether to include it or not

### lua

Better then javascript

[fengari project website](http://fengari.io)

Can be used in the browser

Can do everything Javascript can do

[Learn lua in 15mins](http://tylerneylon.com/a/learn-lua/)

### How not to docker

* Do not run privileged - Can own machine
* Don't expose docker socket - Can mount host file-system
* Don't use host network mode - container can have complete control over host network
* Know where your code is From - don't use random images
* Don't forget your host - Ensure host has a secure kernel



