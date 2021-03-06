# A few thoughts (about programming)
__James Fuller, 05/02/2021__

Sending a few short thoughts about programming to my younger programming self.
 
Most of the following is far from original eg. advice plucked from the flotsam and jetsam observed over the years of a yeoman's career in the trenches. Its composition here is my own personal opinion which others (more knowledgeable) may take umbrage with.

This is not an attempt to define an all encompassing set of rules (there are plenty of good ones already in existence). No high church hymns or rituals to preach -  just a few simple home truths or practical katas to inspire one's current practice.

The intended reader is 'younger me' just entering the craft but I hope experts will see value in being reminded of consistent truths and chime in with their own advice/observations/corrections.

## No > Yes

Early on in our careers we tend to say 'yes' more then 'no' - eager to demonstrate our mastery of programming. Now I see the word 'yes' as something mounted on the wall in a glass box with a hammer saying 'break in case of emergency'.

The main problem with saying 'yes' is that it tends to conclude a discussion when actually what we need to do is continue asking questions.

This applies up and down the stack and cross cutting across all activities we may do as a programmer.

If you are just starting as a junior programmer my advice is always to use the word 'no' more then the word 'yes' and ask a lot of questions.

FWIW I've never lost a job, contract or commercial relationship by saying the word 'no' but I have created software unfit for purpose whenever I've been too cavelier with using the word 'yes'.

## This code makes me feel stupid
We've all been there ... either having to ramp into an unknown code base or revisit something one has written in the past. Some moments of confusion later and we feel 'stupid'.

My own stupidity and [Imposter syndrome](https://en.wikipedia.org/wiki/Impostor_syndrome) aside, if code makes one feel inadequate it is probably a sign of problems.

Well written code, even to the casual non programmer, should convey their top level purpose.

A code base that makes you jump around and puzzle out what it does probably has problems. If its an unknown codebase try to find and use tools to help comprehend and qualify the code, at least to the point where you have a diagram understanding the roles and responsibilities of each part. 

Another way of understanding code is to read, run and write a few more tests.

As a junior (and senior) programmer more often then not you are going to be asked to dive into someone elses previous work - try to understand the context which the code was written first before making quick judgements. Conversely do not be afraid to present well reasoned arguments why it maybe incorrect, got it wrong or is a complete disaster (dont use those words though!).

Try to arrange and write your code so that a layperson (or [psychopath](https://blog.codinghorror.com/coding-for-violent-psychopaths/)) will get a general sense of what is going on. Indicate in the code where things may get complex and try to marshal that complexity into the smallest logical space.

Ultimately reading one's code should make the reader feel smarter. 
Thats what good writers do when presenting complex topics and programmers should view their code as prose that communicates to humans to what it is doing.


## Accidental Architecture
One of the benefits of modern distributed programming is that 'apparent work' can be achieved in parallel by groups of people. That is I can work on a code module and you can work on another code module and we can expect some convergence to work happily together - as a side effect of modern SCM, programming language modularity and common protocols between components.

From plan view this means architecture and design of each individual component can proceed with little communication between each other eg. well defined interfaces between components should mean we can just focus on our own 'black box'.

The lack of coordination between components means that we can get an overall **architecture of convenience** where testers doing end to end integration tests are often the first to discover/assert architectural problems well past the design phase.

This late discovery of 'accidental architecture' can be the death knell of a project eg. so many decisions have already been made that its impossible to do a refactor of architecture. 

Often the cause of this is that we said **Yes** to something early on in the project (ex. we use a framework, we use microservices, we are agile, we write tests first, we  ...insert here ...) and never actively checked that everyone is marching forward together. Entropy, bitrot, changing requirements, new team members, and time all conspire to obscure initial assumptions so that they become myth ... not real but worshipped and given lip service from time to time but never actively managed. 

Existing approaches espousing ['minimal viable product'](https://en.wikipedia.org/wiki/Minimum_viable_product) help ... though what is most important is getting everyone working serially together as a preamble to working in a more distributed fashion. Having teams work closely together in the early phases of a project will help with creating an end to end integration proof of concept as early as possible. This project boostrap phase also allows various teams to discuss and agree on common 'songs'/'rituals' eg. conventions across process and components.

At the code level there are several **A**rchitecture with a small '**a**' type concerns:

* Do we understand data model ?
* Do we understand dependencies ?
* Do we understand coupling between components/data/systems ?

If there are ambiguities or confusion with any of the above then there will be problems.

As a young programmer one should fight for well defined interfaces between components, ask questions about how things work in all the 'black boxes' and ensure everyone has a single defined truth of the entire system operating ... that can take the form of a diagram (though like any artifact a diagram can get [stale](https://structurizr.com/help/code)).

I agree that most of the above may sound like responsibilities of those more senior in the team - but if even a simple up to date [diagram](https://en.wikipedia.org/wiki/C4_model) of the project does not exist then it has to become your responsibility otherwise your part of the project will be more likely to fail. Trust me others (including senior members) will thank and remember you positively for it.

## Let your code prose be more Hemingway, less Faulkner and name things like Dickens

At the individual level writing code should also be about communicating to humans eg. not just a series of instructions to a machine.

Having short concise statements, code blocks and functions is much better then creating ['god' objects](https://en.wikipedia.org/wiki/God_object) which attain a sort of inescapable gravity where all new work must get done in.

[SCAR](https://www.linkedin.com/pulse/architecture-clues-heuristics-part-i-scars-ruth-malan/) helps here as well as fearless refactoring, refactoring, did I mention you need to refactor ?

If you find yourself fearful of refactoring that is a clear signal of problems eg. perhaps not enough tests, cohesion or understanding of 
how the system should operate. Address the inability to refactor first before proceeding to the next game level ;)

[Naming things is hard](https://www.martinfowler.com/bliki/TwoHardThings.html) ... what is most important is to take advantage of your modern IDE ability to easily update names to more reflect what they are/do as you learn more over the lifetime of a project.

Over time codebases resemble archeological digs with each layer introducing different, inconsistent naming ... slavish consistency for consistency sake is not what I am advocating. Do not let names be written in stone, spend a little time on it often with the goal of names being clear, consistent and convey the right meaning.

## Learn how to manage and deploy code and the REST shall follow

Because many programmers today tend to be specialists instead of generalists they miss 
out learning some of the basic tools of the trade.

Simply put:
 
* Spend some time learning a source control system (ex. [git](https://git-scm.com/book/en/v2) or otherwise)
* Spend some time learning how to [deploy code](https://en.wikipedia.org/wiki/DevOps)
* Spend some time learning network protocol (ex. [HTTP](https://www.manning.com/books/http2-in-action) and REST)

Not understanding any of the above will be a serious handicap. 

Being 'autodidatic by default' means trying to learn first before writing odd programmatic 'end runs' around gaps in your knowledge. 

Now that I've said 'learn by yourself' I should probably also mention never to underestimate the efficiency of learning from others more wiser eg. ask for help. Its a credit to the quality of people I have worked with that whenever I asked for help I always got it and more (and always kicked myself for not having asked sooner).

Be quick to say if you don't know something (refer to aforementioned liberal use of the word **No**).

## Don't just push 'bits'

Clearly coding has a mathematical basis but humans use your code and you work with others in crafting code.

One brutish way to put this - if you do not understand the most important component of the system (eg. humans) you are going to encounter difficulties. Learning how to program better is probably not going to help you understand humans better.

* Learn a little [philosphy](https://en.wikipedia.org/wiki/Outline_of_philosophy) 
* Learn a little [ethics](https://en.wikipedia.org/wiki/Programming_ethics)
* Learn a little [psychology](https://en.wikipedia.org/wiki/Psychology)

I often find myself seeking inspiration from [other fields](https://berthub.eu/articles/posts/reverse-engineering-source-code-of-the-biontech-pfizer-vaccine/) - rifling through treasure chests in their high towers bringing back nuggets of wisdom to be applied in programming. 
