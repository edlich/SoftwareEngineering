# INTRODUCTION TO SOFTWARE ENGINEERING

(C) Prof. Dr. Stefan Edlich

---

Requirements Engineering (RE) is a specialist area that deals with the collection of requirements - that is, with the requirements for the software system to be created.

**LEARNING GOALS**

The aim of this learning unit is to familiarize you with requirements engineering, to know all the properties, to learn procedures and to get an idea of how a project manager deals with requirements. Every student should have used a tool to record requirements themselves and received feedback from the mentor or project.

After working through it, you should know why requirements engineering makes sense. You will know the main problems of software development and analysis as well as the most important requirement characteristics. You should become aware of the problem of linguistic fuzziness and the degree of commitment.

**STRUCTURE**

This lesson contains the following chapters:

* Introduction
* Problems and tasks of the RES
* Examples and formalities
* Requirements Engineering II
* RE tasks for you to practice
* Finally, you will get an insight into the prioritization of tasks and the "Eisenhower scheme" that can be used here.

**TIME NEEDED**

You will need approximately 120 minutes to work through the learning unit and approximately 270 minutes to complete the exercises.

**LITERATURE**

* Chris Rupp und Klaus Pohl, "Requirements Engineering Fundamentals: A Study Guide for the Certified Professional for Requirements Engineering Exam - Foundation Level - IREB compliant", Rocky Nook, ISBN-13 978-1937538774
* Ru07 Chris Rupp (2007): "Requirements-Engineering und -Management. Professionelle, iterative Anforderungsanalyse für die Praxis" (in German)
* Po07 Klaus Pohl (2007): "Requirements Engineering. Grundlagen, Prinzipien, Techniken"  (in German)
* Eb05 Christof Ebert (2005): "Systematisches Requirements Management"  (in German)

---

## Motivation and Background

Usually you start with small projects. Usually, most software developers have also heard of UML and use cases. And so - when it comes to defining requirements - you start drawing a use case diagram and storing it in a document.

Later there are larger projects and you realize that this topic is much more complicated and that drawing doesn't work that way. Typically, you then have such a large project that rows of initial "use cases" images fly around your ears - and the whole project at the same time. At this point at the latest, it becomes certain that the requirements should have been dealt with much earlier: much more precisely and much more extensively.

That is exactly the purpose of this lesson. As a responsible software engineer, you should have your own concept of how to approach the topic of requirements and implement them as a project manager.

Please take a look at the following picture:

![Golden Tap](RESSOURCES/02-GoldenHahn.gif)

**Pic**: Three problem areas of software development

Every beginning is easy. You can define, get started and the classes grow and everything is a beautiful playground with not that much connection to reality.

However, over time - with more serious or larger projects - three problems will arise:

1. The stakeholder (client) wants more features, he wants the developed differently. If there isn't regular communication here, it's usually a shocking surprise to the team. See the example "The Fall of the Vasa".
2. The source code becomes much more complex. Troubleshooting is getting harder and harder. There are too many dependencies. Server startup and debugging itself takes too much time. The developers then work neither qualitatively / productively nor creatively.
3. The source code becomes so complex that most of the time even the architects or chief developers hardly understand it. In addition, there is often no documented architecture, architecture guidelines or mechanisms for dealing with complexity.
In this lesson, we want to address the first problem. The other two problems are dealt with in their own learning units - such as *"Object-Oriented Testing"* or *"Dependency Injection"*.

**The Fall of the Vasa**

(excerpt from the book *Productive Programming* by Neil Ford)

In 1625, King Gustav II Adolf of Sweden commissioned the proudest warship the world had ever seen. He hired the best shipbuilders, had a forest with the mightiest oak trees raised and began work on the »Vasa«. Again and again the king made new demands that were supposed to make the ship even grander, lavishly decorated all over. Eventually, he decided that the ship - unlike any ship ever built in the world - should be armed with two gun decks so that it would become the most powerful warship on the high seas. And with an emerging diplomatic conflict, he needed it as soon as possible. Of course, the shipbuilder only intended one gun deck when designing the ship, but since the king wanted it that way, he also got his second gun deck.

Because speed was of the essence, there was no time for the usual *"lurch tests,"* in which a group of sailors run from one side of the ship to the other to make sure the ship isn't rocking too much (in other words: that it's not too top-heavy).

On her maiden voyage, the Vasa sank within a few hours. With all the *"features"* added to the ship, it had lost its seaworthiness. The Vasa lay at the bottom of the North Sea until the early 20th century, when the well-preserved ship was raised and placed in a museum.

And here an interesting question arises:

* whose fault was that the Vasa sank?
* The king because he kept asking for new features?
* Or the shipbuilders who built what they wanted without voicing their concerns loud enough?
* Take a look around the project you're working on: are you about to build a Vasa?

**Background**

Requirements engineering consists of the words requirement and engineering, i. H. the engineering approach to the subject of requirements. The requirements are the wishes / services that a certain group of people (usually the customer) places on the software system to be developed or that it has to fulfill. In this context, one speaks of raising requirements.

This topic overlaps with the general analysis activity in the software life cycle. So there is:

* general (IT) requirements
* the concrete software requirements specification
* parts of the (specifications and especially the) specifications must contain requirements
* and requirements management (i.e. RM aka requirements management)

All of these areas will be explored in more detail throughout this unit.

As is so often the case, it is important to avoid mistakes at an early stage, so the initial phase of a project is also very important. Correcting mistakes made when setting the course initially costs much more money and time later. This is often repressed or forgotten at the beginning. According to studies, 65% of all gross errors in software projects are due to errors in the analysis phase. See also the statistics in the lesson: Introduction to software engineering.

Unfortunately, requirement definitions are far too often saved in some Word document by the project manager or get rotten in some use case diagrams. To prevent this from happening, an RE concept should be integrated into the entire project. So the:

* correct,
* complete,
* of high quality

collection and management of requirement characteristics.

Missing requirements in the project are often replaced by assumptions. Furthermore, there is often the case that the client changes his opinion (or his requirements). It is not uncommon for many of the customer's employees to have very different ideas about what the system should do.

GOAL: The aim should therefore also be to establish a procedure in which requirements are managed and documented in a comprehensible manner.

---

## Tasks and Problems

Very good requirements have many advantages for the project. They serve to fix clear objectives and to make ideas more concrete in the early phase - keyword functional specification / specifications / tender / contract. The requirements themselves have a direct and strong influence on the design and architecture of the system. And finally, RE experts also throw in that good, fixed requirements improve the communication of everyone involved in the project. With an overall understanding of requirements, mistakes, bad assumptions and wrong assumptions are avoided.

![7 Problems](RESSOURCES/02-SevenProblems.gif)

**Pic**: Seven essential problems

According to RUPP there are seven main problems that play a role in the analysis of the future system:

**1) Unclear objectives**

The group of people who ultimately use it often differs from the people who commissioned the system. Collecting the requirements of all representatives (stakeholders) and bringing them under one roof is difficult, but important.

Worse still, there can be different levels and categories of goals, such as:

* product goals
* project goals
* process goals
* business goals
and these can sometimes even be contradictory or conflicting.

**2) High complexity of the system**

Today's software systems are becoming increasingly complex. There are more and more interactions and dependencies, which makes it more and more difficult to take them into account.

**3) communication problems**

Everyone involved in the project has a different knowledge background and also different wishes. In addition, there is a distributed product development in different languages.

**4) Changing goals and requirements**

These are well known as **moving targets or creeping requirements**. Unfortunately or fortunately, both the people and the project change over time. Good requirements management can help here to record, discuss and adequately consider the really important changes. Without a good RE, it often happens that decision-makers simply change their minds when they feel like it. And reimplementing a system at will is poison for any project.

**5) Poor quality of requirements**

Here, according to RUPP, the following problems can be found in the requirements descriptions: ambiguities, redundancies, contradictions and inaccuracies. The effects of these problems in the requirements are easy to imagine.

**6) Gold edge solutions (gold plating)**

In XP parlance, “golden taps” are often used here. This means features that are mostly added by enthusiastic developers, but which are not really necessary and relevant.

**7) Inaccurate planning and tracking of the project**

Based on imprecise requirements, projects are planned too optimistically and then turn out to be too expensive and take too long to develop. So far, for example, performance has not been a requirement; but if this is the case towards the end of the project, it becomes apparent that – e.g. B. from the architecture - a completely different system should have been built.