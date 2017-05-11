
# Testing and work review  #

**Testing**

To build better and more reliable applications, whenever you write a new line of code, you should test your code using both functional and unit tests.
Symfony integrates with an independent library - called PHPUnit - to give you a rich testing framework.

All test are automatically saved in the tests/

![Test details. \label{choice_list}](./03_figures/07_figures/fig_07_01.png)

A unit test is a test against a single PHP class, when functional tests check the integration of the different layers of an application

A function test have a very specific workflow:
                
*   Make a request;
*   Test the response;
*   Click on a link or submit a form;
*   Test the response;
*   Rinse and repeat.

Each application has its own PHPUnit configuration, stored in the phpunit.xml.dist file. only the tests stored in /tests are run via the phpunit command. You can add more directory to be tested in phpunit.xml.dist

The tests run for this application used PHAR (PHp ARchive). To run those tests was need it to be downland from Codeception page the file 
and the root of the project.

![Codeception setup into the project. \label{choice_list}](./03_figures/07_figures/fig_07_03.png)

Once we run the bootstrap codeception we will have install, you need to create your  

![Codeception setup into the project. \label{choice_list}](./03_figures/07_figures/fig_07_02.png)

## PHPunit testing 

Installing thought composer: 

    composer require --dev phpunit/phpunit 

![PHPunit setup into the project. \label{choice_list}](./03_figures/07_figures/fig_07_04.png)

 DbUnit port for PHP/PHPUnit to support database interaction testing. 
    
    composer require --dev phpunit/dbunit 

























**Review**

Our   main   focus   was to   identify a method to save information about suppliers and  products details,
which will give to all employ from the company a easy way to access the same information in real time.
 
The first step to complete the minion was to spend time with Accounts Team to identified which kind of information would need to be stored in database. 
 
Once the information was collected, the next logical step was to create data model for the database and create a Normalised Relational Database Structure (Convert to Third Normal Form ).

Using our ER Diagram as a guide, was created the database and the tables, and populate with data.
 
The purpose of creating generic query result class is to be able to convert SQL queries. Objects are far easier to work with and allow us to use properties instead of array keys.

Even in the beginning I start to create the classes in PHP I found difficult to make sure that classes correspond to each table. 
  
This was the time when I decide to move from PHP to Symfony. This thesis illustrates on the development chapter the different between. 
  
PHP (PHP: Hypertext Preprocessor) is a computer scripting language, originally designed for producing dynamic web pages.
 
Symfony is a web application framework written in PHP which follows the model-view-controller (MVC) paradigm. 

Symfony is written in PHP and builds on it with a set of classes specially designed for the web. So you need to know PHP before you can use Symfony.
 
Symfony adds custom extensions on top of Twig to integrate some components into the Twig templates. 

To be able to complete this project I spend some time learning twig and Symfony.  