# REFACTORING

(C) Prof. Dr. Stefan Edlich

---

![Martin Fowler](RESSOURCES/09-MartinFowler.jpg)

## INTRODUCTION

In this learning unit, the improving refactoring of code, “refactoring”; presented theoretically and practically.

We start with the history of refactoring and deal with program code / source code and its improvement. More important than learning about specific refactorings is developing a feeling for when code can be improved.

If this feeling has been developed through a lot of reading and practical work, then you should know the tools provided by modern development environments. Without this, even simple refactorings (such as renaming classes) can become a nightmare.

In a highly advanced stage of refactoring, you are then able to improve existing code so that design patterns can be integrated.

**LEARNING GOALS**

* Understand refactoring theory
* Identify bad code smells
* Apply refactorings under Eclipse or other IDE
* Know the refactoring catalog
* Know the limits of refactoring

**OUTLINE**
* Introduction to the topic of refactoring
* Literature REF
* Definitions and terms used
* Refactoring theory
* Refactorings
* Refactoring patterns

> Time needed: You will need approximately 120 minutes to complete this learning unit and 60 minutes to complete the exercises.

---

## REFACTORING

The term *refactoring* was first used in this context in 1990 in a paper by PALPH JOHNSON and WILLIAM OPDYKE: 

> QUOTE: “Refactoring: An aid in designing application frameworks and evolving object-oriented systems” Palph Johnson and William Opdyke

OPDYKE received his doctorate in 1992 on the subject of refactoring.

Back then, JOHNSON and OPDYKE wrote about a software refactory that makes it easier to redesign software programs. So the “re-factoring”.

“Factoring” means “factoring” and comes from mathematics (polynomial factorization) and economics, in which it is also understood as the purchase of receivables. But the term in software technology has nothing to do with that.

> NOTICE: In this learning unit, the term will be defined in more detail, but it can already be said that refactoring redesigns and improves the existing program code, but the functionality remains unchanged.

![Refactoring](RESSOURCES/09-Refactoring0.gif)

Pic: Refactoring transformation

If you are curious and would like to see a concrete refactoring, we recommend reading the “Refactorings” chapter in the back. A short hop back and forth is definitely welcome!

---

## REFERENCES

The research area of refactoring is still quite young, so there is not a lot of literature on this topic. However, this topic has received a boost (also thanks to MARTIN FOWLER), so that some good quality publications are available:

> Annotated bibliography http://www.refactoring.com

The refactoring page initiated by FOWLER is something like the central information page about refactoring. There is a ton of information and links to be found here. The most important is the “Catalog” subpage, which we will refer to several times.

 > Refactoring techniques https://refactoring.guru/refactoring/techniques

Similar in structure and also interesting.

> Fowler, Martin, Kent Beck, John Brant, William Opdyke, Don Roberts (1999): **Refactoring: Improving the Design of Existing Code**, Addison-Wesley Professional, ISBN 0201485672

A highly recommended classic. Any serious software engineer or software developer should definitely consider purchasing this book. Even when you browse around, you can always find good information, even after years. This book is also available in German under ISBN 3827316308.

> Kerievsky, Joshua (2004): Refactoring to Patterns, Addison-Wesley Professional, ISBN 0321213351

Also a highly recommended classic and standard work for serious software engineers or software developers.

> Wake, William C. (2003): Refactoring Workbook, Addison-Wesley Professional, ISBN 0321109295

The workbook on the topic of refactoring.

> Martin, Robert C. (2008): Clean Code: A Handbook of Agile Software;
Craftsmanship. Prentice Hall, ISBN-13: 978-0132350884

> Roock; Lippert; Stockfleth (2006): Refactoring in Large Software Projects:
Performing Complex Restructurings Successfully. Wiley & Sons, ISBN-13: 978-0470858929

Other literature

> Scott W. Ambler, Pramod J. Sandalage “Refactoring Databases,” Addison-Wesley 2006

---

## DEFINITIONS AND TERMS USED

Important goals are usually pursued when redesigning the program code:

**Readability**

The readability of the source text should be improved.
The programmer or other people who have to work their way into the source code should understand the source code better. This means that the code becomes more maintainable and can be handled more quickly overall. Changes regarding readability affect e.g. B. naming or hiding details.

**Understandability**

The reference to readability implies that the code becomes understandable more quickly. Even with perfect variable names and method names, the code can be far too long and disorganized. Understandability also implies that, in addition to the pure readability of the code, the developer's entire intention becomes transparent.

**Clarity**

For example, code that is broken down into meaningful code fragments and contains clear and unambiguous methods contributes to the clarity of the project.

***Redundancies***

These can be avoided by, for example, storing the same code fragments in just one method. This can also be moved to the super class. Freedom from redundancy is an important requirement of efficient programming, as changes to different code locations easily cause errors.

**Extensibility**

Code that has been cleanly improved according to the principles of refactoring is easier to extend. For example, if the strategy pattern has been incorporated into a chess program via refactoring, the code can easily be expanded to include a new chess engine that calculates differently.

**Modularity**

Long spaghetti code is known from the old Basic days. Refactoring also comes into play here and tries to optimally modularize the code. This also has an impact on expandability and testability.

**Testability**

> Important: In general, this is about being able to perform better tests. Specifically, these are usually unit tests. Of course, regression tests play an important role in these tests, as they prove that the code behaves in the same way afterwards. It would be fatal if a refactoring were carried out with good intentions but the behavior changed in an undesirable direction!

Object-oriented programming paradigms are very important for professional refactoring. Many refactorings work with patterns, superclasses and polymorphism, all concepts that are inconceivable without a modern object-oriented programming language.

It is also very interesting to see that many refactorings can be extremely complex and change-intensive. Therefore, support from IDEs is essential. Modern Java IDEs such as intelliJ IDEA (which were and are pioneers in the area of refactoring), Eclipse or JBuilder therefore provide good refactoring support.

In conclusion, refactoring is an extremely important part of software redesign these days. All too often, source code has to be rewritten in projects. In this case, the developer should have experience with refactorings and know the corresponding “refactoring patterns” well. Refactoring is often part of the development cycle like in test-driven development (Kent Beck) or can even be found in many process models. This used to be part of a code-remote “re-design”. Today, “refactoring” is an established procedure for code-related improvements.

---

## REFACTORING THEORY

In times of lean project budgets and project margins, it is important to be able to react quickly to changes. This includes both design changes and code changes, such as new features. If the refactoring is professionally supported by the know-how and the IDE used, these are important competitive advantages.

Another goal of refactoring is to integrate design patterns into the code. This topic will be discussed in more detail in the later chapters. The need for the use of patterns often only arises during development and cannot always be foreseen in the design. The need for a facade (class accesses too complex), a proxy (tasks have to be placed in front of them) or observer (here even more classes are interested in changing the state of the GUI variables) often arises during coding when architectural changes need to be made. However, integrating these requires a lot of experience.

> **NOTICE**: The term refactoring mostly applies to OO code, but not always. When it comes to targeted and scientifically based changes, we now don't talk about OO code fragments but rather about refactoring. In principle, everything can of course be refactored (script languages, XML code, etc.). However, practice and literature almost always refer to OO languages.

The best-known examples in the literature where refactoring is mentioned or even IDE support is present are Ant files and database schemas.

![](RESSOURCES/09-Ant.png)

Pic: Extract of the Ant file

![](RESSOURCES/09-Relational.png)

Pic: Extract from the DB schema

Ant build scripts can become large and confusing and database schemas are often inefficient. In many projects, DB schemas get a redesign/refactoring from a professional and the application is suddenly much faster.
ancient tools [JRefactory](https://jrefactory.sourceforge.net/) (Sourceforge project) and [RefactorIT](https://www.refactorit.eu/), there are two IDE-independent Java tools that support refactoring. Some can be integrated into IDEs and offer interesting additional features such as code analysis and refactoring suggestions.

The key point of the extremely important tool support is that A) many refactorings are almost impossible without tools and B) the IDE is important to simply be careful with certain refactorings.

> EXAMPLE A) One of the simplest refactorings is renaming names in the code. Imagine it's about a class that is referenced 42 times in the project. Manual work is impossible here!

> EXAMPLE B) Many refactorings redesign things in a class. Modern IDEs think for themselves and also change the interface!

---

## RISKS AND HANDLING

The refactoring itself is not without risk and should therefore be evaluated critically. Refactoring can cause errors. Another problem is the scope of refactoring, which will be discussed again at the end.

In order to avoid errors during refactoring, the literature often emphasizes that refactorings are only applied to error-free code. Only then is there a proper cycle: correct code → refactoring → (still) correct code. This is the only way to always be on the safe side.

However, it is not clear why refactorings cannot also transform incorrect code into correct code.

> **IMPORTANT**: It is extremely important that unit tests prove the correctness of the refactoring. A series of unit tests should be integrated into the general build cycle (see also the “Continuous Integration” chapter from the “BUI – Build Management” learning unit) and these should ensure correctness before and after refactoring.

A good tip is also to proceed in small steps. This means that even small changes must always be secured via JUnit. This results in less destruction and an easier fallback. Complex refactorings, e.g. B. the design or patterns can also be broken down into smaller units.

> NOTICE: Finally, it should be noted that when refactoring it is important to have solid ground under your feet! This means, for example, the use of UnDo and a version control system. These two tools provide best security when refactoring!

Many IDEs can apply an UnDo to every refactoring (which can sometimes be a very complex operation). Can your IDE do this?

A version control system as git makes it possible to eliminate refactoring errors that are discovered late. So make sure you always work with a version control system. Installing a Subversion server locally and installing Subclipse takes less than half an hour.

---

## THE REFACTORING “SMELL” 

> Question: What exactly is the problem that refactoring solves?

> Answer: "So far it has been said that refactoring improves code. So it's usually the case that the code may not be directly broken, but it is bad in some way. Maybe it's poorly designed. The definition of this bad code will be discussed below. The term “smell” has become established in English-language literature. So source code has a “bad smell”. Our aim is therefore to define and recognize this. We will get to know many “refactoring patterns” later on, which is of course important. However, it is almost even more important to identify the problems in the code, i.e. H. recognizing the “bad smell” than memorizing hundreds of patterns!"

The refactoring “smell” is present when the following situations exist:

**Duplicated code**

Duplicated code is usually caused by copy and paste and is therefore one of the main sources of errors in development. There are therefore tools that search for copy and paste code! Even if the code wasn't copied, it's usually a problem if it occurs multiple times. Changes in this code must then also be carried out in the other code location. It is not very likely that all code fragments will always be edited correctly.

**Long methods**

The problem is known to developers: What was previously in comments in the method is now being programmed out, so that the method becomes longer and longer. And the more you write, the clearer it becomes that an outsider would be less and less likely to understand this method. Is it possible to test the large number of code fragments that are addressed in this method in a more meaningful way?

**Large classes**

This also applies to large classes that become too cumbersome and thus hinder work. Typical representatives here are also GUI classes, which can successfully destroy any UML diagram with their hundreds of meaningless attributes.

**Long parameter lists**

Methods that are overcrowded with parameters also leave a questionable impression. In addition to the bad smell of this signature, you can also usually smell a possible solution, such as encapsulating the transfer data in a transfer object. More on solving such problems later.

> EXAMPLE => **Divergent changes**: MARTIN FOWLER describes in [Fo99] a phenomenon that arises when you introduce variations into a program: you integrate access to a new database or a new financial instrument and each time you have to change a lot of methods in different classes, which is cumbersome. As time goes on, you come to the conclusion that it would be better to handle variations in just one class so that changes can be treated as parameters.

**envy**

This apt term describes the condition in which, for example, a method X of class A is more interested in the data M of class B than in its own data (of class A). Apparently the division of methods and attributes is not very well chosen and requires some changes.

**Too many elementary data types**

Elementary data types are used too often when using encapsulating objects would be more appropriate.

Other possible causes for the “smell” can be clumps of data, switch commands (better polymorphism) and incorrect inheritance hierarchies. The examples presented here and other detailed examples can be found in Fowlers book.

---

## SEARCH AND REFERENCES TO REFACTORING NEEDS

What occurs when the code is poorly designed and what can be done to get more clues about refactorings?

* If more and more time is spent worrying about code that has already been written, it may be an indication that it is not well designed and needs to be refactored.

* In all somewhat extensive projects, you should take a look at the current UML diagram at regular intervals - it's best to print it out regularly and stick it on the wall! As you gain more experience, you notice special things, such as classes that are too full or strange inheritance hierarchies.

* Code analysis **metrics** such as JDepend, described in later lessons, provide clear evidence of poor design. JDepend shows class dependencies, cycles and measures of the abstractness of the code, etc., which can be improved by the following refactoring methods or by introducing design patterns.

---

## REFACTORINGS

> DEFINITION => **Refactoring patterns** The core element of refactoring are so-called refactoring patterns. These are used similarly to design patterns to improve the code. A refactoring pattern is the transformation of the code described at the beginning and usually consists of several work steps. The work steps are often carried out by the IDE. The developer therefore only has to decide which code fragments he wants to apply the pattern to.

MARTIN FOWLER did the work of cataloging the refactorings. He was supported by the community, so many refactorings came from other developers. This catalog can be found at http://www.refactoring.com/catalog and contains all listed refactorings!

Many of the refactorings listed there are deliberately kept **independent** of programming languages. However, if code needs to be used for illustration, it will be in a Java or C# dialect.

> IMPORTANT NOTE: A catalog always has the right to be complete. This also means that many refactorings don't make much sense subjectively. It could just as well be that the interested reader cannot understand some refactorings at all or will never want to use them. This is completely fine. It is important to know the spectrum. Maybe you're more likely to embrace the 10-20 most important refactorings and let his IDE help you with that.

In the following, IDE support is often discussed and Eclipse's refactoring capabilities are explained as an old example. Fortunately, the catalog of refactoring support is sufficiently abstract that IDEs such as Eclipse, JBuilder, Netbeans or IntelliJ IDEA do not differ much.

> NOTICE: Eclipse 3.1 has 31 refactorings. Here are the most important ones:

* `Rename, Move, Change Method Signature, (Undo, Redo)`
* `Convert Anonymous Class to Nested, Convert Nested Type to Top Level`
* `Push down, pull up`
* `Extract interface`
* `Use Supertype Where Possible`
* `Inline,Extract Method`
* `Extract Local Variable, Extract Constant`
* `Convert Local Variable to Field, Encapsulate Field`

Since the refactorings mentioned are among the most important, the following procedure is recommended:

* Please read through and understand how it works on the following pages or in the **Fowler catalogue**.
* Then try it out with your own IDE and test the refactoring pattern, i.e. H. to “warm up” with him.

---

## PROBLEM AND CURE

Before some examples of refactorings (also under Eclipse) are presented in more detail, it is helpful to have a guide to hand that names the “smell” and the associated possible “cure”. This last reference from [Fo99] can only serve as a rough guide here. Without a detailed description of the smell from [Fo99] it is not easy to identify the problems listed below on the left.

In any case, it is helpful to be able to imagine the problems listed on the left in advance. As a result, the solutions on the right side of the previous refactoring overview page can be quickly found and opened.

![Smell](RESSOURCES/09-Smell.gif)


|odor / “smell”|refactoring / possible solution|
|--------|--------|
|Rename alternative classes with different interfaces|rename method, move method|
|rejected inheritance|replace inheritance with delegation|
|data classes|encapsulate collection, encapsulate field, ove method|
|Chunk of data|pass entire object, extract class, introduce parameter object|
|diverging changes|extract class|
|duplicate code|extract class, extract method, move method up, form template method|
|lazy class|flatten hierarchy, integrate class|
|large class|extract class, extract interface, extract subclass, replace value with object
|comments|extract method, introduce assurance|
|long method|decompose condition, replace method with method object, extract method, replace temporary variable with query|
|long parameter list|pass entire object, replace parameter with method, introduce parameter object|
|message chains|hide delegation|
|envy|move field, extract method, move method|
|bias for elementary types|replace array with object, extract class, introduce parameter object, replace type code with class, replace type keys with subclasses, replace type code with status/strategy, replace value with object|
|parallel inheritance hierarchies|move field, move method|
|Remove shotgun pellets (*1)|move field, integrate class, move method|
|speculative generality|flatten hierarchy, integrate class, rename method, remove parameters|
|switch commands|replace conditional expression with polymorphism, introduce null object, replace parameters with explicit methods, replace type keys with subclasses, replace type code with status/strategy|
|temporary fields|extract class, introduce null object|
|inappropriate intimacy|replace bidirectional association with directional one, hide delegation, move field, move method, replace inheritance with delegation|
|incomplete library class|introduce foreign method, introduce local extension|
|intermediaries|replace delegation with inheritance, integrate method, remove intermediaries|

What is quite interesting about this table is that **comments** (or too many comments) can also have a negative “smell” and in this case can be replaced by a simpler, explanatory method or by a clearly readable assurance. Comments can therefore also be part of a refactoring improvement.

It is always interesting and almost a sport for software engineers to examine the **switch** commands. Since many switch commands can be replaced by more elegant constructs - such as exploiting **polymorphism** - there is something disreputable about the switch command. The sport now is to find a better variant.

What did FOWLER mean by shotgun pellets?

> NOTICE (*1): **Shotgun pellets**

> Suppose you make a change (D1) somewhere in the code. As a result of this change - which you have already done several times - you also have to make changes / adjustments in other places in other classes (D2 to DN).

> The suspicion arises that you could group all the places where you make changes (D1...DN) into one class. The places where further changes are required were described by MARTIN FOWLER as shotgun pellets, which sit “painfully” in the body.

![Pellets](RESSOURCES/09-Schrot.gif)

---

## REFACTORING UNDER ECLIPSE

With Eclipse, refactoring support is easily accessible via the right-click menu. It should be noted that the menu is context-sensitive - that is, it depends on what is currently selected (class, method, attributes, code fragment, etc.).

> NOTICE: It is therefore always worthwhile to mark different areas with the right mouse button and have a look what is offered!

![Eclipse](RESSOURCES/09-Eclipse.png)

Pic: EclipseRefactoring.png

---

## REFACTORING PATTERNS
