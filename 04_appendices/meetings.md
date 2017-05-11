\appendix

# Appendix 

## Creating Applications with Composer in Symfony

in this project was used the command line to create a new project:
    
          $   composer create-project symfony/framework-standard-edition pro
          
![Initialize a symphony project. \label{choice_list}](./03_figures/09_figures/fig_09_01.png)
  
When creating the project, the DB connections are to be setup. On the same time this can be done later, so you need to change it, got to { parameters.yml } file and modify them

![Initialize DB connections for project. \label{choice_list}](./03_figures/09_figures/fig_09_02.png)

To be able to work on the project and tested on the same time you will need to move into the directory which hold all the tiles
  
Before starting to work on the it is recommended to run the local host to make sure that the configuration went well. 

    $   php bin/console server:run
   
As a result, if you open the browser and access the http://localhost:8000/ you can see the Welcome Page of Symfony:

![Welcome Page of Symfony. \label{choice_list}](./03_figures/09_figures/fig_09_03.png)

It any error occur than you will need to Fix File Permissions

#  Create a Symfony entity 

The advantage of using Symfony is that you can use the generate:doctrine:entity command on the command line.

       $ php bin/console generate:doctrine:entity

This command generates a new Doctrine entity stub including the mapping definition and the class properties, getters and setters.

![Create a new class. \label{choice_list}](./03_figures/09_figures/fig_09_04.png)

By default, the command is run in the interactive mode and asks questions to determine the bundle name, location, configuration format and default structure:

![Create a new class in interactive mode. \label{choice_list}](./03_figures/09_figures/fig_09_05.png)

The command can be run in a non-interactive mode by using the --no-interaction option, but you need to pass all needed options:

    $ php bin/console generate:doctrine:entity --no-interaction --entity=AcmeBlogBundle:Post --fields="product_name:string(30) product_description:text" --format=xml
    

# Generating database with Sympfony

The easiest way to understand how Doctrine works is to see how it is working. 
 
To be able to generate a table in a database you'll configure the database, use the Product object created before, persist it to the database and fetch it back out.

Configuring the Database

Before you really begin, you'll need to configure your database connection information. By convention, this information is usually configured in an app/config/parameters.yml file:

![Connect to database. \label{choice_list}](./03_figures/09_figures/fig_09_07.png)


## Creating tables in the database ##

Before you begin, you'll need to configure your database connection information. 
By convention, this information is usually configured in an ‘app/config/parameters.yml’ file.
Once the connection with the database it is setup we can tell Doctrine to create a corresponding table.


     $ php bin/console doctrine:schema:update --force

 ![Create table. \label{choice_list}](./03_figures/09_figures/fig_09_08.png)

Once the command is lunch on the terminal a couple of confirmation messages will confirm that table has been created:
If you update the structure of an entity and run the same command line you can se that the table it is updated.

    Updating database schema...
    Database schema updated successfully! "3" query was executed

If you access your database you can see that see a new table in the database it is created.
 
Figure \ref{new_table} shows our new `product_details` table created for us.

![CLI created table in PHPMyAdmin. \label{new_table}](./03_figures/06_figures/fig_06_01_1.png)

