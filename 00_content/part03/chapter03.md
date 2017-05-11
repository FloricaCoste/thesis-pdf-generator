
# Literature review #

Materials control is a definition of a systematic control over purchasing and dealing with suppliers. 
Materials control helps to maintain a regular and timely supply of materials by avoiding over and under-stocking. 
Materials control ensures that the right quality and quantity of materials is available to the company 
at the right time. Materials control helps to reduce the losses and wastage of materials by maintaining their efficient purchase.

On the market they are some application that provide this facilities, but they are expensive due to the fact that they are build by the big Company.
    
## Overview of Technical Resources Consulted ##
 
 This chapter will present the technical resources used to achieve the goal of project:
  
 *  MVC - Model-View-Controller; 
 *  Object Oriented in PHP extend to Symfony;
 *  Twig;
 *  Java Script;
 *  AJAX
 *  Symfony;
 
1. MVC - Model-View-Controller 
 
 Model View Controller (MVC) is used to implement user interfaces: it is therefore a popular choice for architecting web page.
 In general, it separates out the application logic into three separate parts, promoting modularity and ease of collaboration and reuse.
 It also makes applications more flexible and welcoming to iterations.
 
 For a better understanding we can look to the MVC apply for a Basket list - a concept used in this application.
 The list of items will store: names, quantities and price of each items which we need to have in stock.
 Below we'll describe how we could implement some of this functionality using MVC.
 
 ![Model-View-Controller. \label{choice_list}](./03_figures/03_figures/fig_03_01.png)

*   Model

The model defines what data should be contain. If the state of this data changes, then the model will usually notify the view (so the display can change as needed) and sometimes the controller (if different logic is needed to control the updated view).
  
In our case the model would specify what data the list items should contain — items, price, name.
   
*   View
    
The view defines how data should be displayed.

In our Basket list, the view would define how the list is presented to the user, and receive the data to display from the model.

*   Controller

The controller contains logic that updates the model and/or view in response to input from the users of the interface.

Basket list could have input forms and buttons that allow to add or delete items. These actions require the model to be updated,
so the input is sent to the controller, which then manipulates the model as appropriate, which then sends updated data to the view.

It may be need it just the update of view display for data in a different format, as an example change the item order to alphabetical or lowest to highest price. 
In this case the controller could handle this directly without needing to update the model. 

2. Object Oriented;

Object can be anything including physical and conceptual. Like suppliers, products are of physical type of objects and conceptual like user, software.

Class is a collection of similar types of objects and also includes attributes (properties of objects) and operations (methods) those are used to define actions that can be performed with the help of objects.

In object oriented approach, following main features are included:

*   Encapsulation

Encapsulation is a feature of object oriented approach, which indicates data hiding. 
We can hide data that we don’t want to make accessible. Objects can be grouped into classes. Classes represent a set of objects that must have a certain common attributes and behaviours. All these attributes and behaviours are bounded in a class.

*   Abstraction

Abstraction is a feature of object oriented approach, in which we can provide accessibility of some specific variables and method for users according to their relevancy. If we want to provide accessibility to user to fetch personal details of theirs only, we can do it by using the concept of abstraction.

*   Inheritance

Inheritance allows inheriting a class in other subclasses. A derived or subclass can inherit the attributes and methods of parent class. This makes our code reusable, which is the most important advantage of an object oriented approach. This concept creates relationship between parent and child classes.

In PHP when we inherit one class in another, we have to use the keyword extends.

*   Polymorphism

In object oriented approach polymorphism represents different behaviour for the same operation. Polymorphism can be static and dynamic.

In static polymorphism more than one function having same name but different number of arguments, type of arguments and sequence of arguments 

Polymorphism can be dynamic also, in which functions with same function signature present in both parent and child class. In this process it will decided at the run time

3. Twig

Twig is a template engine for the PHP programming language.
Its syntax originates from Jinja and Django templates. The initial version was created by Armin Ronacher. 
It's an open source product licensed under a BSD License and maintained by Fabien Potencier.
Symfony PHP framework comes with a bundled support for Twig as its default template engine.


4.  JavaScript 

JavaScript is a programming language that adds interactivity to the website (for example: responses when buttons are pressed or data entered in forms in a dynamic style).

5.  AJAX 

AJAX is a set of Web development techniques using many Web technologies on the client side to create asynchronous Web applications.

6.  Symfony 

Symfony is a Model-View-Controller (MVC) framework written in PHP that’s aimed at building web applications. 

Symfony an MVC implementation in PHP, it also integrates a lot of objects that facilitate the development of web applications — and integrates them all with a coherent syntax. 
It is a code generation, easy templating, internationalization, caching, automated form validation, and Ajax, are among the most appreciated symfony features. Developing an application with symfony is slightly different than building it with any other framework, or without any framework at all.
It’s faster and more productive.