The pursuit of simplicity
21/10/2019

> A programmer's competence should be judged by the ability to find simple solutions.
> - Niklaus Wirth 

I worked with quite a few systems that were challenging problems: an Intelligent Character Recognition system, a Recommendation Engine, and an auto-scaling system for ML scientists. And then a few well known problems: reverse proxy, authentication system, school management software. In some of these I have come across systems that were complex monsters or became one. After dealing with such bad systems I pursued simplicity.

Simplicity is difficult to define. So as mathematicians prove theorems using contradictions, I will go about defining it by defining Complexity and hope you would understand its antonym, simplicity.

What is complexity? John Ousterhout defines it well in his book A Philosophy of Software Design[1].

> Complexity is anything related to the structure of a software system that makes it hard to understand and modify the system.

In other terms:

> If a software system is hard to understand and modify, then it is complicated; if it is easy to understand and modify, then it is simple.

I like this definition even though it is a bit subjective. It is easy to understand. Do you need to modify 10 different services[2] to build a simple feature? You system might be complex. In A Plea for Lean Software[3], Niklaus Wirth, writes “the incomprehensible should cause suspicion rather than admiration”. Sometimes magic or smart code is lauded rather than frowned upon. 

Complexity is not limited to code. A lot of it stems from the product trying to satisfy every whim and fancy of the user. We have grown so accustomed to build software that does everything. A note taking application now has AI-suggested content[4]. In the paper[3] Writh tries to explain the reason we try to offer everything:

> Uncontrolled software growth has also been accepted because customers have trouble distinguishing between essential features and those that are just “nice to have”

Instead of limiting the scope of the product, product owners want everything. If you have ever owned an old Nokia phone you might remember the Snake game. This was the most popular game. The game was simple, it didn't have the greatest graphical elements nor did it have an elaborate story. It was built on the constraints that were inherent to the phone. In an interview[5] the engineer who wrote the game says:

> It was simple enough to live with those constraints. There is no point in using complex solutions when simple does the job.


Why then do we build complex software? There are a few I can think of:

1. The Principal Agent Problem[6]. The problem is that agents are motivated to act on their own interests, which are contrary to those of their principals. This problem is observed with politicians and voters, lawyers and clients, and brokers and sellers. At times it can be observed with software engineers(agents) and their employers(principals). By introducing microservices to an organisation that clearly doesn’t need it, the engineer is acting in her own interest; a feather in her cap for the next job.
2. For a highly elusive future. "In the future we might...", "In the future this...", "In the future it will be...". There is always a special case where the software might have to work in a different way. 
3. When the team lacks clarity. When both the Engineers and Product Owners have little clarity in what needs to be built, they try to build everything.


My early days in a new team over the recent years has been to educate them to pursue simplicity. Sometimes the battle has been long and some, pleasantly, have been short; like preaching to a choir. There are numerous ways to keep your software simple and some have even written books on it[1]. I'd like to share a few that I find useful to remind to myself every now and then.

1. Understand the problem that needs to be solved, especially the constraints and tradeoffs that you can make.
   If you were requested to build a bridge the question you should ask is what does building the bridge solve. The answer seems so trivial that even a 8 year old can answer. To cross the river. But that is just one part of the answer. How many people need to cross the river, how often do they need to cross it, do large vehicles need to cross? When answering these questions you might confirm a bridge needs to be built. Or you might settle on building a boat to cross it.
   Building the right software for the given problem and time space. Time can be tricky. It is easy to think of too short or large a lifespan. What if in the future there are several people who want to cross the river in their cars? There is nothing certain about the future, so fix the problem when you absolutely must. “The future problem should be solved once it arrives and you can see its actual shape and requirements in the physical universe.”[1]
	
2. Build in iterations to get quick feedback.
   Waterfall based development still exists today, sometimes even clothed in Agile skins. Not building in iterations to get feedback from the user is an easy way to build complex software. The prompt feature is good to understand if a feature was necessary. If it wasn’t it is easy to scrap it. If there were changes to be made it doesn’t need to be worked around other 20 features that are waiting to be released. The longer the development cycle the longer it takes to get feedback on the software you wrote and the more complex the code tends to be.
	
3. Don’t focus on the technology.
   As programmers I think we have a tendency to be a Magpie[7]. Magpies are birds that pick up shiny things to decorate their nests. Kafka, event-sourcing, microservices, lambda functions etc. All these are great technologies but are they right technology for the problem you are trying to solve. The best technology is the technology you know best. It helps you to get things out quickly and get feedback. It helps you focus on the problem you have to solve rather than the new way of deploying your code. 

4. Better communication.
   Let’s draw lines between the members in your team.
   ![team-communication](/s/images/team-interactions.png)
   The lines represent the communication between team members(defined by letters). I gave up drawing the interactions beyond a 6 member team. Communication overhead increases the more people you have in your team. And when the overhead increases a gulf begins to yawn in the common understanding of the problem. It would be nice to have very small teams to work independently of other teams. But that rarely happens in the real world. The best way is to invest in good communication between teams. The article “Bad Software Architecture is a People Problem”[8] provides a few ways to solve this issue: define how you will work together, when bugs happen work together to solve them, create coding standards.



It is not easy to build simple software. There are several factors that go into the design of software. But if we pursue we might just build software that is a joy to work on.

 
---

1. A Philosophy of Software Design: https://www.goodreads.com/en/book/show/39996759
2. I worked with a team where this was exactly the case. A simple change in the API needed a dozen of services to be modified.
3. A Plea for Lean Software: https://cr.yp.to/bib/1995/wirth.pdf
4. Evernote features list: https://evernote.com/compare-plans
5. https://melmagazine.com/en-us/story/snake-nokia-6110-oral-history-taneli-armanto
6. https://en.m.wikipedia.org/wiki/Principal–agent_problem
7. https://blog.codinghorror.com/the-magpie-developer/
8. Bad Software Architecture is a People Problem: https://queue.acm.org/detail.cfm?id=2974011
