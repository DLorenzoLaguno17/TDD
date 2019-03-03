● code reviews.
● Functionality and limitations expected to communicate to the team.

I am [Dani Lorenzo](https://www.linkedin.com/in/daniel-lorenzo-laguno-a2ab35180/), student of the [Bachelor’s Degree in Video Games by UPC at CITM](https://www.citm.upc.edu/ing/estudis/graus-videojocs/). This content is generated for the second year’s
subject Project 2, under the supervision of lecturer [Ricard Pillosu](https://es.linkedin.com/in/ricardpillosu).

# Index
* [Introduction](#introduction)
    * [What is a Technical Design Document?](#what-is-a-technical-design-document?)
    * [The relation of the TDD with the GDD](#the-relation-of-the-TDD-with-the-GDD)
* [Sections of a TDD](#sections-of-a-technical-design-document)
    * [Core sections](#core-sections)
       * [Technical goals](#technical-goals)
       * [Technical risks](#technical-risks)
       * [Code style guidelines](#code-style-guidelines)
       * [External libraries](#external-libraries)
       * [Code organization overview (UML)](#code-organization-overview-UML)
       * [Branching policy](#branching-policy)
       * [Performance budgets](#performance-budgets)
       * [Delivery platform and requirements](#delivery-platform-and-requirements)
    * [Optional sections](#optional-sections)
* [References used](#references-used)

# Introduction
Modern digital games can be considered as large software projects which run and are made up of thousands of lines of code to millions of lines of code. Object-Oriented Design came into existence to deal with large software projects. The GDD or TDD are made for keeping in mind all the demands of Object-Oriented Programing along with the implementation details (TDD for technical details and GDD for entire Game Details) within it.

## What is a Technical Design Document?
The Technical Design Document provides a blueprint for the software engineers in your team to implement and code the features of your game. The technical design document will let your developers to specify what are the requirements, how they should be implemented, along with the tools and technologies required for the implementation. The connection between structural design of a Software and Technical Design Document is that the technical design document has a broader scope with less details, than a software architecture diagram.

## The relation of the TDD with the GDD
The GDD is the soul of a videogame, it is equivalent to [the "Bible" of a television series](https://www.shorescripts.com/what-is-a-tv-series-bible/). This document will be used as the base for the development of the game. It contains a summary of The TDD is a specification for all the technical aspects of the features which are defined in the Game Design Document (GDD).

So, we could say as [Laura Deng](http://lauradeng.com/eng/?p=187) tells us in her website that *"while a GDD is derived from the game concept and is a functional description of the game from the user’s point of view, while a TDD is an architectural description of the game from the implementer’s point of view"*.

# Sections of a Technical Design Document
The information contained in a TDD can vary depending on the company or the project. Nevertheless there are sections which are more usual than others, so we will divide them in what I have called **core sections** and **optional sections**.

## Core sections

### Technical goals
The tehcnical goals are seat to ensure everyone inside the team knows where to aim when working. They are what is expected to acheive in relation to the code, the game engine or the platform where the game is going to be delivered. Some examples would be immersive ambient sound, complex AI or realistic shadows.

### Technical risks
At the same time a team has its goals there are also risks which must not be overlooked. If the company is making the time-travel level of Dishonored 2 (a level where you can go from the past to the future and the scenary changes) one of those riks could be that the fact of having two maps rendered at the same tame makes the game go incredibly slower. In order to take the risks into account they are written down in the TDD.

<p align="center">
  <img src="https://github.com/DLorenzoLaguno17/TDD/blob/master/docs/dishonored-level.jpg?raw=true" alt="Github branches" width="675" height="380">
</p>

*Time-travel level in [Dishonored 2](https://dishonored.bethesda.net/en). As we can see in the image, the player is in one stage (present) while is looking through its gadget to the other stage (past) in real time.*

### Code style guidelines
Being one of the most important of the TDD, in this section are described the code conventions that will be applyed during the development of the whole project, in order to have an organized and homogeneous code that every programmer of the team is able both to understand and to work with. The thoroughness of the code style guidelines depends on the programming team and their objectives. Here are some examples of the elements one could find in this section:

* **Naming rules:** Explains the language of the code, how variables and functions must be named, the use of signs like parentheses and whitespaces or the need of using comments. For example:
       
       Every #define must be in capital letters:
       #define MAX_HP 300
    
* **Variables:** Explains how to manage the variables, how to declare and initialize them and whether to declare them inside `public`, `protected` or `private` part when using classes or structs. For example:
       
       Every time a pointer is created must be initialized as null:
       int* test = nullptr;

* **Loops:** Mentions which loops are preferred inside the code (`while`, `do-while`, `for`...) and when to use `break` and `continue` keywords. 

* **Conditionals:** Describes how to manage condicionals, whether to separate the `if` line from the  if or to put everything in the same line, when to use scopes `{}` or if it is preferred a conditional with operators or without them. For example:

        We prefer a conditional like if(something) {}
        rather than one like if(something == true) {}

* **Classes & structs:** It is basically a convention of when to use classes and when structs and how to write the elements inside them. 

* **XML:** Outlines the guidelines to write the variables in the XML files of the project and how to name their nodes and attributes. For example:
       
       If a node has one attribute we will declare it in their same line:
       <house colour="red"/>

*This list of elements has been made taking [DevCrumb's TDD](https://github.com/DevCrumbs/Warcraft-II/wiki/7.-Tech-Design-Document) as a reference.*

### External libraries
In this section are detailed the external libraries which are going to be used for the development of the project and what are they going to be used for.

### Code organization overview (UML)
The UML offers a general outlook of the structure the code will have and the inheritance relation between its classes. UML diagrams show the functions and the variables included in each module. It is a guide used to see the whole picture of the code. Nevertheless, this guide will change as the project goes by and the game evolves, becoming more complex each time and being extended with more specified UML diagrams of the emergent code modules.

<p align="center">
  <img src="https://github.com/DLorenzoLaguno17/TDD/blob/master/docs/general_UML.png" alt="General UML" width="686" height="677">
</p>

*DevCrumb's general UML for their game [Warcraft II: The Stolen Artifacts](https://devcrumbs.github.io/Warcraft-II/).*

### Branching policy
Branches are very useful during the programming process of the game, but a team needs to have stipulated in which way are they going to use them to ensure this advantage does not turn against them. This is what this section of the TDD is for. It defines a set of rules and conventions that are going to be followed every time a member desires to make a commit. These rules consist of when a developer should branch, which branch should the developer use, when should the developer commit a merge and to which branch sould the developer make the merge commit.

<p align="center">
  <img src="https://github.com/DLorenzoLaguno17/TDD/blob/master/docs/github-branches.jpg?raw=true" alt="Github branches" width="675" height="380">
</p>

*This is an example of a branching system inside a GitHub project. If you are interested and want more information about Branching policy you can check out [this website](https://rollout.io/blog/branching-strategy/)*.

### Performance budgets
Related with the [technical goals](#technical-goals), the performance budgets are a series of limits imposed on metrics that affect the game or program performance. Those could be the frames per second the game runs, the amount of disk memory is occupied by a certain feature of the game or the time it is expected for a map to be loading. Defining a budget helps get the web performance conversation started. Performance budgets serve as a point of reference for making decisions about design, technology and adding features. That enables the team to approach to the game with an established mentality about which standards their final result must accomplish. 

However, they are sometimes difficult to achieve or might change through the game creation process, so they are only a guide. As [Ben Garney](https://bengarney.com/) and [Eric Preisz](https://www.linkedin.com/in/eric-preisz-371a8b/) say in their book [Video Game Optimization](https://www.amazon.com/Video-Game-Optimization-Eric-Preisz/dp/1598634356/ref=sr_1_1?__mk_es_US=%C3%85M%C3%85%C5%BD%C3%95%C3%91&keywords=video+game+optimization&qid=1551553868&s=books&sr=1-1) *"the performance budget, much like a financial budget, is typically not perfect. It is a benchmark for measurement and guidance. [...] Use the budget to determine problems and to forecast and manage change"*.

### Delivery platform and requirements
It defines the target platform for which the game will be delivered, such as PC, Xbox, PS4 or other consoles. In addition, in this section is specified minimum and the recommended hardware and software which are required to play it. Minimum requisites are the ones for which the game has been designed and will make the platform run it. On the other hand, recommended requisites will allow the user to run the game fluidly. We will take [Cuphead](http://www.cupheadgame.com/) as an example:

## Optional sections

### Choice of game engine
If the game uses a game engine it will explain which one has been decided to use and the reasons of this election. This section also has a brief description of the features the chosen engine provides to the developers.

### Art tools
In case there is no art bible, this section will detail which art tools will be used for the game and where will they be applied.

### 3D Objects, terrain and scene management

### Use of physics engine
This section describes how will be de collision detection, how will be the physics calculated and applied to the game (gravity, friction...) and how will be the interaction of the charaters or the other entities with the game world. 

### AI
It is very im ------------------

### Networking
In the case the game is multiplayer or has a multiplayer mode this section explains how it will be handled.

### Audio and visual effects

# References used
These are all the pages I have checked to do the research.
* [Studytonight](https://www.studytonight.com/3d-game-engineering-with-unity/tdd-and-gdd).
* DevCrumb's [Concept Discovery](https://github.com/DevCrumbs/Warcraft-II/wiki).
* Computer Games MMU's [TDD](https://computergamesmmu.files.wordpress.com/2012/10/technical-design-document-final.pdf).
* Narbacular Drop's [TDD](http://www.nuclearmonkeysoftware.com/documents/narbacular_drop_technical_design_document.pdf).
* [El documentalista audiovisual](https://eldocumentalistaudiovisual.com/2015/02/06/documentacion-en-videojuegos-documento-de-diseno-gdd/).
* [Básico y Fácil](https://basicoyfacil.wordpress.com/2009/01/02/que-son-requisitos-minimos-y-requisitos-recomendados/).
* [What is a Branching Strategy?](https://rollout.io/blog/branching-strategy/)
* Video Game Optimization's [fragment](https://books.google.es/books?id=MeILAAAAQBAJ&pg=PA27&lpg=PA27&dq=performance+budgets+of+a+video+game&source=bl&ots=-RmRgeg4nn&sig=ACfU3U1BgDCT4alxei4_glK7NOc6BmdtuQ&hl=ca&sa=X&ved=2ahUKEwjpxYSMieTgAhUMyxoKHSk8D1kQ6AEwCHoECAYQAQ#v=onepage&q&f=false).
* [web.dev](https://web.dev/fast/performance-budgets-101).

Go [back to top](#index).
