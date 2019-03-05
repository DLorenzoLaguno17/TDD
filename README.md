# THE TECHNICAL DESIGN DOCUMENT
I am [Dani Lorenzo](https://www.linkedin.com/in/daniel-lorenzo-laguno-a2ab35180/), student of the [Bachelor’s Degree in Video Games by UPC at CITM](https://www.citm.upc.edu/ing/estudis/graus-videojocs/). This content is generated for the second year’s
subject Project 2, under the supervision of lecturer [Ricard Pillosu](https://es.linkedin.com/in/ricardpillosu).

# Index
* [Introduction](#introduction)
    * [What is a Technical Design Document?](#what-is-a-technical-design-document)
    * [The relation of the TDD with the GDD](#the-relation-of-the-TDD-with-the-GDD)
* [Sections of a Technical Design Document](#sections-of-a-technical-design-document)
    * [Core sections](#core-sections)
       * [Features from the GDD](#features-from-the-GDD)
       * [Technical goals](#technical-goals)
       * [Technical risks](#technical-risks)
       * [Code style guidelines](#code-style-guidelines)
       * [External libraries](#external-libraries)
       * [Code organization overview (UML)](#code-organization-overview-UML)
       * [Branching policy](#branching-policy)
       * [Performance budgets](#performance-budgets)
       * [Build delivery method](#build-delivery-method)
       * [Version list](#version-list)
       * [Delivery platform and requirements](#delivery-platform-and-requirements)
    * [Extra sections](#extra-sections)
       * [Choice of game engine](#choice-of-game-engine)
       * [Art and audio tools](#art-and-audio-tools)
       * [3D Objects, terrain and scene management](#3d-objects-terrain-and-scene-management)
       * [Use of physics engine](#use-of-physics-engine)
       * [Artificial Intelligence](#artificial-intelligence)
       * [Networking](#networking)
* [References used](#references-used)

# Introduction

## What is a Technical Design Document?
A Technical Design Document (TDD) is a **scheme** for the programmers in a team to implement and code the features of their game. It lets the developers of the team specify what are the requirements, how they should be implemented and the tools and technology required for that implementation. Besides, the TDD is also a useful document to show when it comes to find a publisher for your game, considering that they are becoming every time more careful about evaluating the games they may invert in.

## The relation of the TDD with the GDD
Both the GDD and the TDD are video game related living documents, which means they are regularly updated and edited during the development of the product, so which is their relation? The Game Design Document (GDD) is the soul of a videogame, it is equivalent to the [Bible of a television series](https://www.shorescripts.com/what-is-a-tv-series-bible/) (sometimes a GDD is also called Bible). It allows game developers to administrate and organize their ideas in a document which will be followed by all the members of the team and will be used as the base for the development of the game. On the other hand, the TDD is a blueprint for all the technical aspects of the features which are defined in the GDD. In that way, we could declare as [Laura Deng](http://lauradeng.com/eng/?p=187) says that *"while a GDD is derived from the game concept and is a **functional description** of the game from the user’s point of view, a TDD is an **architectural description** of the game from the implementer’s point of view"*.

# Sections of a Technical Design Document
The information contained in a TDD can vary depending on the company or the project. Nevertheless there are sections which are more usual than others, so we will divide them in what I have called **core sections** and **extra sections**.

## Core sections
The core sections are those which tend to be in all the TTDs no matter what the game is about.

### Features from the GDD
Since the TDD is the document that will handle all the technical aspects of the development of the game it is important to summarize the most relevant features of GDD to have them handy. 

<p align="center">
  <img src="https://github.com/DLorenzoLaguno17/TDD/blob/master/docs/doomGDD.JPG?raw=true" alt="Github branches" width="450" height="578">
</p>

*Original DOOM's [bible](http://planetdoom.gamespy.com/classicdoom/doombible.pdf) (GDD).*

### Technical goals
The technical goals are a **list of objectives** set to ensure everyone inside the team knows where to aim when working. They define what is expected to achieve in relation to the code, the game engine or the platform where the game is going to be delivered. Some examples would be immersive ambient sound, complex AI or realistic shadows.

### Technical risks
At the same time a team has its goals there are also risks which must not be overlooked. If the company is planning to make a level like the time-travel level of Dishonored 2 (one where you can go from the past to the future and the scenery changes) one of those risks could be that the fact of having two maps loaded and rendered at the same tame makes the game go incredibly slow. In order to take the risks into account they are written down in the TDD.

<p align="center">
  <img src="https://github.com/DLorenzoLaguno17/TDD/blob/master/docs/dishonored-level.jpg?raw=true" alt="Github branches" width="675" height="380">
</p>

*Time-travel level in [Dishonored 2](https://dishonored.bethesda.net/en). As we can see in the image, the player is in one stage (present) while is looking through its gadget to the other stage (past) in real time.*

### Code style guidelines
Being one of the most important of the TDD, in this section are described the **code conventions** that will be applied during the development of the whole project, in order to have an **organized and homogeneous code** that every programmer of the team is able both to **understand** and to **work with**. The thoroughness of the code style guidelines depends on the programming team and their objectives. Here are some examples of the elements one could find in this section:

* **Naming rules:** Explains in which language the code must be, how variables and functions must be named, the use of signs like parentheses and whitespaces or the need of using comments. For example:
       
       Every #define must be in capital letters:
       #define MAX_HP 300
    
* **Variables:** Explains how to manage the variables, how to declare and initialize them and whether to declare them inside `public`, `protected` or `private` part when using classes or structs. For example:
       
       Every time a pointer is created must be initialized as null:
       int* test = nullptr;

* **Loops:** Mentions which loops are preferred inside the code (`while`, `do-while`, `for`...) and when to use `break` and `continue` keywords. 

* **Conditionals:** Describes how to manage conditionals, whether to separate the `if` line from the functions inside the conditional or to put everything in the same line, when to use scopes `{}` or if it is preferred a conditional with operators or without them. For example:

        We prefer a conditional like if(something) {}
        rather than one like if(something == true) {}

* **Classes & structs:** It is basically a convention of when to use classes and when structs and how to write the elements inside them. 

* **XML:** Outlines the guidelines to write the variables in the XML files of the project and how to name their nodes and attributes. For example:
       
       If a node has just one attribute we'll declare it in their same line:
       <house colour="red"/>

*This list of elements has been made taking [DevCrumb's TDD](https://github.com/DevCrumbs/Warcraft-II/wiki/7.-Tech-Design-Document) as a reference.*

### External libraries
In this section are detailed the external libraries which are going to be used for the development of the project and what are they going to be used for.

### Code organization overview (UML)
The UML offers a **general outlook of the structure the code will have** and the inheritance relation between its classes. UML diagrams show the functions and the variables included in each module. It is a guide used to see the whole picture of the code. Nevertheless, this guide will change as the project goes by and the game evolves, becoming more complex each time and being extended with more specified UML diagrams of the emergent code modules.

<p align="center">
  <img src="https://github.com/DLorenzoLaguno17/TDD/blob/master/docs/generalUML.jpg?raw=true" alt="General UML" width="686" height="677">
</p>

*DevCrumb's general UML for their game [Warcraft II: The Stolen Artifacts](https://devcrumbs.github.io/Warcraft-II/).*

### Branching policy
Branches are very useful during the coding process of the game, but a team needs to have stipulated in which way are they going to use them to ensure this advantage does not turn against them. This is what this section of the TDD is for. It **defines a series of rules and conventions** that are going to be followed **every time a member desires to make a commit**. These rules consist of when should a developer branch, which branch should the developer use, when should the developer commit a merge and to which branch should the developer make the merge commit.

<p align="center">
  <img src="https://github.com/DLorenzoLaguno17/TDD/blob/master/docs/github-branches.jpg?raw=true" alt="Github branches" width="675" height="380">
</p>

*This is an example of a branching system inside a GitHub project. If you are interested and want more information about branching strategies you can check out [this website](https://rollout.io/blog/branching-strategy/)*.

### Performance budgets
Related with the [technical goals](#technical-goals), the performance budgets are a series of **limits imposed on the metrics that affect the game performance**. Those could be the frames per second the game runs, the amount of disk memory is occupied by a certain feature of the game or the time it is expected for a map to be loading. Performance budgets serve as a **point of reference** for making decisions about design, technology and adding features. That enables the team to approach to the game with an established mentality about which standards their final result must accomplish. 

However, they are sometimes difficult to achieve or may change through the game creation process as the TDD evolves, so they are only a guide. As [Ben Garney](https://bengarney.com/) and [Eric Preisz](https://www.linkedin.com/in/eric-preisz-371a8b/) say in their book [Video Game Optimization](https://www.amazon.com/Video-Game-Optimization-Eric-Preisz/dp/1598634356/ref=sr_1_1?__mk_es_US=%C3%85M%C3%85%C5%BD%C3%95%C3%91&keywords=video+game+optimization&qid=1551553868&s=books&sr=1-1) *"the performance budget, much like a financial budget, is typically not perfect. It is a benchmark for measurement and guidance. [...] Use the budget to determine problems and to forecast and manage change"*.

*[Here](https://www.youtube.com/watch?v=yqejmZrtmNg) there is an interesting video about performance budgets in websites.*

### Build delivery method
This section describes the process that will be followed every time a build is delivered. It explains if there will be used an extern program, who will deliver the build and when will it be delivered.

### Version list
Planning beforehand what it is intended to have for each version of the game creates a guideline to follow when it comes to create the releases. In this way the team can identify in which phase of the development they are. For example, a company creating an RTS could decide that they want the fog of war to be for the version `v0.6`. Eventually, when it is implemented it will mean they have achieved that version and that it is time for a new release.

### Delivery platform and requirements
It defines the **target platform** for which the game will be delivered, such as PC, Xbox, PS4 or other consoles. In addition, in this section is specified the minimum and the recommended hardware and software which are required to play it.

<p align="center">
  <img src="https://github.com/DLorenzoLaguno17/TDD/blob/master/docs/platforms.jpg?raw=true" alt="Platforms" width="675" height="380">
</p>

*The consoles of the last generation, considered the 8th.*

## Extra sections
The extra sections of a TDD are those which vary depending on the game or are not as important or necessary as the core sections.

### Choice of game engine
If the game is going to use a game engine this section explains which one has been decided to use and the reasons of this election. It also has a brief description of the features the chosen engine provides to the developers.

### Art and audio tools
In case there is no Art Bible and no Audio Bible, this section will specify which art tools will be used for the game art and audio and which tool will be used for each art or audio area.

### 3D Objects, terrain and scene management
In this section is explained which objects will be in each part of the map, which terrains will be used in the game and how will be the scene management.

### Use of physics engine
This section describes how will be de collision detection, how will be the physics calculated and applied to the game (gravity, friction...) and how will be the interaction of the characters or the other entities with the game world. 

### Artificial Intelligence
If the game will have a complex AI system, it is very important it is conscientiously planned and detailed.

### Networking
In the case the game is multiplayer or has a multiplayer mode this section explains how it will be handled.

# References used
These are all the pages I have checked while doing the research.
* [Studytonight](https://www.studytonight.com/3d-game-engineering-with-unity/tdd-and-gdd).
* DevCrumb's [Concept Discovery](https://github.com/DevCrumbs/Warcraft-II/wiki).
* Computer Games MMU's [TDD](https://computergamesmmu.files.wordpress.com/2012/10/technical-design-document-final.pdf).
* Narbacular Drop's [TDD](http://www.nuclearmonkeysoftware.com/documents/narbacular_drop_technical_design_document.pdf).
* [El documentalista audiovisual](https://eldocumentalistaudiovisual.com/2015/02/06/documentacion-en-videojuegos-documento-de-diseno-gdd/).
* [What is a Branching Strategy?](https://rollout.io/blog/branching-strategy/).
* [What is a GDD?](https://medium.com/@cbrown0510/what-is-a-gdd-ca43e2094995).
* Video Game Optimization's [fragment](https://books.google.es/books?id=MeILAAAAQBAJ&pg=PA27&lpg=PA27&dq=performance+budgets+of+a+video+game&source=bl&ots=-RmRgeg4nn&sig=ACfU3U1BgDCT4alxei4_glK7NOc6BmdtuQ&hl=ca&sa=X&ved=2ahUKEwjpxYSMieTgAhUMyxoKHSk8D1kQ6AEwCHoECAYQAQ#v=onepage&q&f=false).
* [web.dev](https://web.dev/fast/performance-budgets-101).
* [Purpouse of the TDD](https://www.wisdomjobs.com/e-university/game-developing-tutorial-261/purpose-of-the-technical-design-document-6737.html).

Go [back to top](#index).
