# Philly ETE 2010 Talk

Work with Trotter on ideas for the presentation...



## Use Of Open Source in the Enterprise or Financial Industry

Is it ok for me to use this in the Financial Industry?

How do I convince my boss?

Won't the open source gremlins steal our code?  Or: how do I keep the licensing clear between the corporate IP and the open source libraries we use.

Licensing Considerations

Handling Bugs

Handling Contributions, Fixes, Enhancements

Interacting with the Community productively

How much time to spend on the tools / libraries vs your own value adds.

When to ditch the open code and roll your own.

Where did it work for us?

When to open a library to the public. Aka, what is intelluctual property I should protect?


## Scott's Comments:

Thinking out loud... note we originally brought you guys in under the Languages track with this description:

>>
Real world clojure/erlang/functional experiences
<<

My thought of course had been about Clojure - but this was before we got Rich Hickey locked!

We wanted to let you all brainstorm as to what in particular you might present. We thought the real synergy with what you all were doing re: the mission of the conference was that it's enterprise software being built with "emerging tech".

So you have brainstormed and are proposing AMQP versus an "automation" talk. Here is my feedback:

We do have an Infrastructure track and Ezra is already speaking on Chef vs. Puppet. It might be redundant to have another infrastructure automation talk. And there is no other talk on AMQP this year. Does that mean you should do the AMQP talk? You decide! I can't. I want both.

BTW I recommend you specifically name Erlang in the Presentation Two abstract. I don't think we have any other talks touching on Erlang, so it would be good for emerging-buzzword-compliance to at least say "the Erlang based RabbitMQ".

------------

FINAL BRAINSTORM THOUGHT

How about this idea... I know it's not a lot of time, but party with this thought:

How about a Chef/Cucumber/JRuby/Clojure/AMQP/RabbitMQ(ergo Erlang) "in the real world" talk?

Somehow do an end to end walkthrough of the systems you guys work on, and all the touchpoints that emerging technology has in it. All in 45 minutes. Not sure if this is doable, or how much value people would see it. I think it would be a cool talk. The point could just be to illustrate how you can build something big and fast and reliable using all this emerging open source tech.


## Living on the Bleeding Edge: A Case Study in the Financial Industry

## Living on the Bleeding Edge in the Financial Industry: A Case Study in Using Clojure, AMQP, Chef, Cucumber and JRuby

Proposed Summary:

Have you been itching to try emerging technologies like Clojure, AMQP, Chef,
Cucumber or JRuby? We'll cover what happened to us when we proposed these hot
(unproven!) new technologies, management said yes, and we had to deliver by
sharing our story of building a message exchange in the financial industry. We
think hearing our story will help give you the confidence to take these
technologies into your own enterprise.



--------------------

Early in the slides: these technologies won't win on their own.  What they will
do is allow you to attract and retain talent and act as a multiplier for your
resources.

Anticipated Questions:

How did you get to use them?
  Prototype, showed good ROI

How did you get management to agree?
  Prototype, showed good ROI
  Allowed the company to attract good local talent (the technology was attractive)

How did you hire? / How did you find people who knew these things?

How did you show ROI?

How did you integrate between .NET, Linux, Java, in otherwords across all of these technologies?

Why didn't you use standard J2EE technologies?

How did you get this to perform?



## Strategies for Living on the Bleeding Edge in the Financial Industry: A Case Study

We have the feeling that you feel that the title would have more draw if the
specific technologies were mentioned in the title, so we could go with what you
suggested previosuly, or what about something like:




Other titles

 - Leveraging Early Adopter Technologies for high productivity in the Financial Industry
 - Agility with Early Adopter Technologies in the Financial Industry
 - Leveraging Emerging Technologies to Make Your Small Team Seem Big
 - Leveraging Emerging Technologies to Make A Small Team Seem Big in the Financial Industry

Who We Are
 - company
 - team

The World We Operate In
 - the collateral 'industry'
 - "a big fucking enterprise"
 - team / office
 - not "a big fucking enterprise"
 - following on a successful, agile, formerly 'innovator' product (.NET beta circa 2004)

10 Second Overview of Collateral?
 - bilateral agreeemnts: I'll buy your morgtages and pay you X % a day
 - big fucking bank is afraid other fucking bank is going to fail
 - so they demand collateral to back up the agreement
 - the value of the collateral often changes day to day (see also DJIA)

Collateral:
  - 2006:     6 Billion
  - 2009: 1.3   Trillion
  - lots of transactions every day, lots of $ at stake (see also current crisis)
  - Phone + Email
  - ==> Ripe for automation

** This feels like a narrative of our project, need to stay away from that

So Here We are
  - Competitive landscape
  - We needed to move _quickly_
  - Small(ish) budget (at least for this kind of project)
    - team of 4 Devs + 1 Project Manager
      (this certinly colored how we looked at our needs...)
  - Here's what we did / cut out...

Needed QA
 - assert that we conform to requirements
 - reduce / eliminate regressions
 - shorten release cycles

 - :( we had no QA resourcess
 - But we had 4 devs
    "hey, let's automate that" <-- constant theme
    "it'll take weeks to get a PO, lets use open source tool X" <-- constant theme
       (also, our devs work hard to keep abreast of what's out there, all on their own)

Rescuing our Lack of QA Resources
 - Automating Testing
   - BDD with RSpec
     - conformity to api
   - with Cucumber: Feature Driven Development and Integration Testing
     - conformity to requirements
     - testing as a real-world user (through the browser / GUI)
 - Reduce bugs in newly developed code
 - Both serve to reduce regressions

Needed Systems Administration
 - set up workstations
 - set up qa
 - set up beta, alpha, beta environments
 - consistency
 - timelyness (anecdote about the NYC demo)
   - Linnode outage
   - 4hrs, a credit card and 1 bash script later
     and we had a whole new environment

Rescuing our Lack of System Administrator Resources
 - Did we say Automaton yet?
 - First Cut: bash script(s)
   - easy, basic, worked well enough
   - documentation on other solutions was light, so we just used bash
 - Second Cut: Chef
   - realized the bash script wasn't very maintainable / scalable / configurable
   - documentation didn't improve, but our developers worked on a
     side project where they took the time to learn it
   - Easy, Powerful configuration
   - Shared provisioning rules
   - Easy Node and Role division
   - significantly faster than a screen full of remote ssh commands and shell utilities
   - all Ruby, all the way down (libraries, consistent scripting)
   - we folded our application's release into a Chef Recipe
     - way simpler
   - Go with Puppet if it fits better for you
  - Failure to automate:
    - you just signed up for SLOWing down your release cycle / installation process / testing cycle
 - Cloud Providers
   - Linnode, Slicehost, et al
   - NO PO
   - credit card (montly expensed)
   - No lead time: can have it today, in fact right fucking now
   - cuts both ways: didn't involve IT; then again, not to corp standard, not 'certified'
   - automated provisioning / releasing meshed perfectly with this

  - 1st environment: 4d install, creating the automated script (remember: just bash)
  - 2nd environment: 2d install, involved bugfixes
  - 3+: 0.5d (mostly waiting for software to copy / install)
  - After conversion to Chef: ~30min to set up a new environment
    - local workstation; linnode or slicehost
  - no maintaining VMware snapshots? (might not be a good thing)
  - easier transitions and upgrades
  - deployment / provisioning can be versioned in conjunction with the applications (big win)

Needed [More] Resources: Time to Market
  - Competitors are well staffed and funded
  - few business resources assigned to project as well
  - Lmited budget == Small team
  - Decision was to focus on Quality over Quantity
   - leverage HLLs
   - Help figure out the problem domain
   - ability to work with less guidance

Rescuing our Lack of Resources
 - Leverage JVM
   - The Libraries
   - Known deployment, tuning strategies
 - High Level Languages
   - studies indicate that less LOC == teh hawtness
   - imply LOC is directly related to bug count
   - implies that LOC written by dev's is constant regardless of language
   - make each line be all it can be!

Jruby
 - leverage Rails
 - Lots of libraries and Tools
   - RSpec
   - Cucumber
   - nokogiri / hpricot (very easy XML handling)
   - Rake - easy task automation and foreign tool integration (eg: lint:{js,css})
   - AMQP Java Library works well, easily integrate Rails + MQ

Clojure
 - leverage JVM Libraries
    - AMQP Java Lib
    - Trixx - RabbitMQ management library
 - Statelessness reduced bugs
 - High Level concurrency constructs
  - running service threads == easy
  - background task execution == easy
  - service monitoring and recovery was easier (primitive but easy)

Agile Process and Methods
 - Pair Programming
   - no silos
   - very fast knowledge / skill sharing
   - bus factor == size of team
   - highly intense days, pairs keep each other focused and on task
   - quickly recover from unproductive paths
   - team members are inspired to rise to each other's level
     (lots of mutual respect between all team members, this
      made hiring difficult and _very_ important - team fit is more
      crucial than acute technical skill)
 - quickly adapt new ideas that have short term ROI
  - developer helper tools
    - often picked up and used by Project Manager
    - often picked up and used by QA
    - _because they saved time_
  - threw out our wiki
    - too slow
    - wrote small web app to help internal team find
      information, sign in to the various environments
    - easier than the wiki (no one owned the wiki,
      devs would own the code in the helper apps)
 - task cards / backlog
  - ensured that there is always antoher task to do
  - no dev resources sits idle
  - might not be the highest priority
    but not blocked on Business prioritization

Git: DVCS
 - branching


  * QA - Unit tests && Integration tests w/ cucumber
  * System Provisioning - Bash / Chef
  * Coding - High Level Languages - Ruby / Clojure
  * Agile Methods kept us focused - Promiscious Pairing, Task Cards
  * Overall - Hiring top talent that work well together


http://en.wikipedia.org/wiki/Technology_adoption_lifecycle
http://en.wikipedia.org/wiki/File:DiffusionOfInnovation.png

    * innovators - had larger farms, were more educated, more prosperous and more risk-oriented
    * early adopters - younger, more educated, tended to be community leaders
    * early majority - more conservative but open to new ideas, active in community and influence to neighbours
    * late majority - older, less educated, fairly conservative and less socially active
    * laggards - very conservative, had small farms and capital, oldest and least educated


??? Could be: Clojure, Functional Programming

Anectdote about how easy it was to makde the AMQP consumer more robust by using agents.  Going from a simple thread based consumer to one that, in an outer try/catch block sent-off a message to an agent asking to be restarted.  The implementation was very simple.  The simplicity of using Clojure data strcutures for configuratrion; how immutability made for less debugging and runtime errors in the system.

Statelessness leads to far fewer issues.  Functions as first class types allow for the easy creation of DSL-like declarative configurations: we have leveraged this heavily in our messaging code for handling message processing and routing.  These mini-dsls often manifest themselves simply as dispatch tables, keeping the overall shape and concerns of the code in one place.

The JVM is a great platform, Java is an expensive language to perform development in.  Clojure allows us to move nearly as quickly as Ruby, while being a more natural fit on the JVM, allows you to implement much more complex logic with a lot less supporting code.

Deployment: Long running processes: Clojure compiles to class files.  JRuby does support compilation, though as far as we know it is not widely used in this way (should look at warbler and what it does, it may do this!!).  Ruby needs to be open to extension at run-time in ways that Clojure does not.  Clojure still supports macros and first class functions, which puts it inbetween languages like Ruby and Java, it is more dynamic than Java (from a code perspective), but not at runtime (as Ruby is).

Personal Observation: Contemplating writing our messaging code in Ruby (from Clojure) I immediately get the feeling that I'd want a much more comprehensive test suite if it were to be done in JRuby.  The first thing that comes to mind are tests that are not necessary given the types and function signature checking that is done in the clojure compilation process and in the JVM itself when classes are loaded.  These are aspects that are not handled in JRuby as far as I know.

Hiring Resources / Learning Clojure (vs something like Scala):  Clojure is much smaller of a langauge than Scala, but most of you out there refuse to work in a Lisp (look around the room).


## Highly Interactive Applications: Javascript in The Browser

YUI, jQuery, our pretty complex web front end using very small bits of data back and forth with the server, the patterns of interaction we recognized (eg: the url hash / bookmarking feature)...



## Trends in Enterprise Automation

Is your organization dying from an inability to provision systems and move your application through QA quickly enough? The world we live is changing as automated tools make it easier to leverage vast numbers of systems and test code with fewer people. In this talk, we'll discuss what we see as the emerging trends in automated deployment and testing. We'll talk about how tools like Chef and Cucumber allow you to scale your team further.


- Provisioning

  - Setting up multiple boxes by one person is expected

  - Doing it by hand takes too long and is fragile

  - How do you ensure that dev env is the same as prod env

  - We wrote a bash script, not best

  - Chef / Puppet are good techs

  - How do I get my code running on the 10 boxes that I just bought on Slicehost?

  - Past: Commercial tools / doing it your own on a box by box basis

  - Present: Linux distro's tools + custom scripting

  - Future: Chef / Puppet which allow you to treat your configuration and app code as co-dependent

- QA

  - We write unit tests to check quality on the low level

  - Integration tests let us check at the high level

  - Writing integration tests for browsers is now easier due to selenium and others

  - Cucumber can make your integration tests understandable by the business people

  - Two trends: unit testing / integration testing

  - Unit testing didn't really take off until XP and X-Unit style frameworks

  - Past: QA team develops test plans and performs manual regressions (or you used, really just bought and didn't use, expensive commercial apps like Mercury Test Runner)

  - Present: TDD and Unit testing frameworks are well established, automated integration testing is not standardized.

  - Future: Integration testing automation is emerging (for web at least) with tools like cucumber that make browser drivers like selenium easier to use and understand.






## Patterns of Enterprise Messaging with AMQP and RabbitMQ

JMS, (IBM?) MQ, MSMQ or Tibco's days may be numbered, there's a new protocol in town: AMQP.  Open Source, Standardized Asynchronous Messaging is maturing with the release of RabbitMQ and other AMQP implementations.  This highly performant, technology neutral protocol allows you to write your messaging clients in any language you want.  In this talk we'll discuss the AMQP standard, how you can leverege it in your architecture, and RabbitMQ in particular.


- Part I: What is a Message Queuing?

  - Where did AMQP Come from?

- Common Usage Patterns

    - Workload Distribution

    - RPC

      - Asynchronous

      - Synchronous

    - Logging / Event Notification

    - Broadcasting information / Synchronization to multiple consumers

    - Instant Messaging...2 browser based users working with each other

- Less Common Usage Patterns

    - ESB-Like: Service Decomposition Boundaries, Service Discovery, Resource Abstraction (Eg: like REST), Location Decoupling (better term for this?)

    - Time Shifting: 'do this later' or 'tell them, or me, at some point'

    - Bridging / Integration Patterns, Protocol Adapters/ Bridges

- Part II: Working With AMQP

  -  Installing and Configuring RabbitMQ

  -  Messaging Topology

    -  Vhosts, Exchanges and Queues

    -  Message Routing: Bindings

  -  Distributed Transactions

- Part III: Permissions and Security

  -  Users and Permissions

  -  Message Security

    -  Encrypted or Signed message bodies

    -  SSL and TLS

      - Generating Self Signed Certificates

      - Enabling Client SSL (.NET and Java)

      - Client Server Certificate Validation (.NET and Java)

      - Client Side Certificates and Validation

- Part IV: Monitoring and Deployment

- Part V: Clustering, Failover


## notes from the 2010/01/21 Conference Call

"That did make it ok to live on the bleeding edge." - Trotter talking about things like Chef, Cucumber, Rspec and automation



