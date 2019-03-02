You need to create a website under github.com with:
○ Intro to the problem
○ Different approaches by different games (use animated gifs when possible)
○ Description in detail for the selected approach
○ Links to more documentation
○ TODOs and Solution inside the repository as VS projects
○ Optional Homework for practicing
○ Explanation of any other improvements on the system

It defines all technology related items that should be considered.
● Code Style, Platforms supported, code organization overview (UML).
● Branch workflow, code reviews, performance budgets.
● Functionality and limitations expected to communicate to the team.

I am [Dani Lorenzo](https://www.linkedin.com/in/daniel-lorenzo-laguno-a2ab35180/), student of the [Bachelor’s Degree in Video Games by UPC at CITM](https://www.citm.upc.edu/ing/estudis/graus-videojocs/). This content is generated for the second year’s
subject Project 2, under the supervision of lecturer [Ricard Pillosu](https://es.linkedin.com/in/ricardpillosu).

# Index
* [Introduction](#introduction)
* [Sections of a TDD](#sections-of-a-technical-design-document)
* [References used](#references-used)

# Introduction
Modern digital games can be considered as large software projects which run and are made up of thousands of lines of code to millions of lines of code. Object-Oriented Design came into existence to deal with large software projects. The GDD or TDD are made for keeping in mind all the demands of Object-Oriented Programing along with the implementation details (TDD for technical details and GDD for entire Game Details) within it.

## What is a Technical Design Document?
The Technical Design Document provides a blueprint for the software engineers in your team to implement and code the features of your game. The technical design document will let your developers to specify what are the requirements, how they should be implemented, along with the tools and technologies required for the implementation. The connection between structural design of a Software and Technical Design Document is that the technical design document has a broader scope with less details, than a software architecture diagram.

## The relation of the TDD with the GDD
The GDD is the soul of a videogame, it is equivalent to the "Bible" of a television series. This document will be used as the base for the development of the game. It contains a summary of The TDD is a specification for all the technical aspects of the features which are defined in the Game Design Document (GDD).

So, we could say as [Laura Deng](http://lauradeng.com/eng/?p=187) tells us in her website that *"while a GDD is derived from the game concept and is a functional description of the game from the user’s point of view, while a TDD is an architectural description of the game from the implementer’s point of view"*.

# Sections of a Technical Design Document
The information contained in a TDD can vary depending on the company or the game. Nevertheless there are sections which are more usual than others, so we will divide them in what I have called core sections and optional sections.

## Core sections

### Code style guidelines
Being one of the most important of the TDD, in this section are described the code conventions that will be applyed to the code during the development of the whole project, in order to have an organized and homogeneous code that every programmer of the team is able both to understand and to work with. The thoroughness of the code style guidelines depends on the programming team and their objectives. Here are some examples of the elements one could find in this section:

* **Naming rules:** Explains the language of the code, how variables and functions must be named, the use of signs like parentheses and whitespaces or the need of using comments. As an example:
       
       Every #define must be in capital letters:
       #define MAX_HP 300
    
* **Variables:** Explains how to manage the variables, how to declare and initialize them and whether to declare them inside *public*, *protected* or *private* part when using classes or structs.

* **Loops:** Mentions which loops are preferred inside the code (while, do-while, for...) and when to use *break* and *continue* keywords.

* **Conditionals:** Describes how to manage condicionals, whether to separate the *if* line from the  if or to put everything in the same line, when to use scopes {} or if it is preferred a conditional with operators or without them. As an example:

        We prefer a conditional like if(something) 
        rather than one like if(something == true).

* **Classes & structs:** It is basically a convention of when to use classes and when structs and how to write the elements inside them. 

* **XML:** Outlines the guidelines to write the variables in the XML files of the project and how to name their nodes and attributes.

*This list of elements has been made taking [DevCrumb's TDD](https://github.com/DevCrumbs/Warcraft-II/wiki/7.-Tech-Design-Document) as a reference.*

### External libraries used

### Branching policy
Branches are very useful during the programming process of the game, but a team needs to have stipulated in which way are they going to use them in order this advantage does not turn against them. This is what this section of the TDD is for. It defines a set of rules and conventions that are going to be followed every time a member desires to make a commit. These rules consist of when a developer should branch, which branch should the developer use, when should the developer commit a merge and to which branch sould the developer make the merge commit.

<p align="center">
  <img src="https://github.com/DLorenzoLaguno17/TDD/blob/master/docs/github-branches.jpg" alt="Github branches" width="800" height="450">
</p>

*This is an example of a branching system inside a GitHub project. If you are interested and want more information about Branching policy you can check out [this website](https://rollout.io/blog/branching-strategy/)*.

### Performance budgets
The performance budgets are a series of limits imposed on metrics that affect the game or program performance. Those could be the frames per second the game runs, the amount of disk memory is occupied by a certain feature of the game or the time it is expected for a map to be loading. Defining a budget helps get the web performance conversation started. Performance budgets serve as a point of reference for making decisions about design, technology and adding features. That enables the team to approach to the game with an established mentality about which standards their final result must accomplish. 

As [Ben Garney](https://bengarney.com/) and [Eric Preisz](https://www.linkedin.com/in/eric-preisz-371a8b/) say in their book [Video Game Optimization](https://www.amazon.com/Video-Game-Optimization-Eric-Preisz/dp/1598634356/ref=sr_1_1?__mk_es_US=%C3%85M%C3%85%C5%BD%C3%95%C3%91&keywords=video+game+optimization&qid=1551553868&s=books&sr=1-1): *"The performance budget, much like a financial budget, is typically not perfect. It is a benchmark for measurement and guidance. [...] Use the budget to determine problems and to forecast and manage change"*.

### Delivery platform and requirements
It defines the target platform for which the game will be delivered, such as PC, Xbox, PS4 or other consoles. In addition, in this section is specified minimum and the recommended hardware and software which are required to play the game. Minimum requisites are the ones for which the game has been designed and will make the platform run the game. On the other hand, recommended requisites will allow the user to run the game fluidly. We will take the game [Cuphead](http://www.cupheadgame.com/) as an example:

## Optional sections

# References used
These are all the pages I have checked to do the research.
* [Studytonight](https://www.studytonight.com/3d-game-engineering-with-unity/tdd-and-gdd).
* [DevCrumb's Concept Discovery](https://github.com/DevCrumbs/Warcraft-II/wiki).
* [Computer Games MMU](https://computergamesmmu.files.wordpress.com/2012/10/technical-design-document-final.pdf).
* [El documentalista audiovisual](https://eldocumentalistaudiovisual.com/2015/02/06/documentacion-en-videojuegos-documento-de-diseno-gdd/).
* [Básico y Fácil](https://basicoyfacil.wordpress.com/2009/01/02/que-son-requisitos-minimos-y-requisitos-recomendados/).
* [What is a Branching Strategy?](https://rollout.io/blog/branching-strategy/)
* Video Game Optimization's [fragment](https://books.google.es/books?id=MeILAAAAQBAJ&pg=PA27&lpg=PA27&dq=performance+budgets+of+a+video+game&source=bl&ots=-RmRgeg4nn&sig=ACfU3U1BgDCT4alxei4_glK7NOc6BmdtuQ&hl=ca&sa=X&ved=2ahUKEwjpxYSMieTgAhUMyxoKHSk8D1kQ6AEwCHoECAYQAQ#v=onepage&q&f=false).
* [web.dev](https://web.dev/fast/performance-budgets-101).
