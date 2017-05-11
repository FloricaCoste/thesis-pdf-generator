#   System analysis #

The systems analysis is a stage of process developing information. This serves to set the stage and bound the project. Working on concepts such as data implementation, interfaces, and roles, you will describe in details whom and what would the WEB application will do.

Object-oriented analysis is the process of analyzing a task, to develop a conceptual model that can then be used to complete the task. The models describe computer software that could be used to satisfy a set of customer-defined requirements

Use case are use in this project to describe each operation. Each use case provides one or more sequence that describe how the system should interact with the users called actors to achieve a specific function. Actors are end users: user, managers, account and super user (General Manager). 

**Functional Requirements**

This chapter presents what the system is expecting to do and also how it in different scenarios, in the Use Cases
   
System requirement:
   
In case user login the WEB application will provide the following function:
*	the user can see supplier’s details;
*	the user can see list of products from a supplier;
*	the user can see if any other supplier provides the same product at different price;
*	the user can send a request for a quotation; 
*	the user can add a comment to a product; 
*	the user can add a review to a supplier;
   
In case manager user login the WEB application will provide the same function as a regular user and in addition will have the following function:
 
*   do what a regular user does;
*   add new supplier;
*   update details of a supplier;
*   to be able to add/update/remove a product from a supplier;
*   to update the stock on hand;
*   to create order proposals based on the stock requirements;
*   transfer an order to a related user (General Manager and Account Manager);
*   follow up with a supplier on orders;
*   to update the price for the items; 
*   to add, remove items from the list; 
*   to modified the contact details; 
*   once an order it is place to update the delivery date and the due date for the payment;
*	see the stock level;  

In case manager user login the WEB application will provide the same function as a regular user and in addition will have another function that will give permission
 to approve/deny/place on hold a PO;
     
Account Manager can do what the general manager. In addition the general manager and the account manager – 
they both must agree before an order is placed. When an order is approved then automatically get an PO number, send to the supplier a copy of the POs, and confirm to the manager that the order has been place 
   


##User login: - Use case   ##
    

  ![Before user login. \label{choice_list}](./03_figures/04_figures/fig_04_12.png) 
  
  **Title**: This use case describes how a user logs into the WEB application.
  
  **Actor** : any user;
  
  **Scenario** :
  
  This use case starts when an actor wishes to log into the WEB application.
  
  *	The system requests that the actor enter username and password.
  *	The actor enters username and password.
  *	The system validates the entered username and password and logs the actor into the system.
  
   **Alternative Scenario**
  
  * Invalid username or password; 
  
  If the actor enters an invalid username or password, the system displays an error message. 
  The actor can choose to either return to the beginning of the scenario or cancel the login.
  
  Pre-Conditions
   *    None
  
  Post-Conditions
   *   If the use case was successful, the actor is now logged into the system. If not the system state is unchanged.

  
1.  **User login can see supplier’s details**
  
  ![User login can see supplier’s details. \label{choice_list}](./03_figures/04_figures/fig_04_01.png)
   

**Title**: User login is looking for information to see supplier’s details;

**Actor**: User login;

**Scenario**

*   user select from the menu the option supplier;
*   the system displays a list of supplier;
*   user can select a specific supplier;
*   user will see the supplier description, some supplier details are not accessible;
*   user logout;

**Alternative Scenario**
   
At any time before selecting a supplier, the user can cancel the request and the use case ends.

2.   **User login can see list of products from a supplier;**

![User login can see the products details. \label{choice_list}](./03_figures/04_figures/fig_04_02.png)

**Title**: User login is looking for information to see product details;

**Actor**: User login;

**Scenario**

*   user select from the menu the option product;
*   the system displays a list of products;
*   user can select a specific product;
*   user will see the product description, some products details are not accessible;
*   user logout;

**Alternative Scenario**
   
At any time before selecting a product, the user can cancel the request and the use case ends.

3 **User login can see the stock level**
       
  ![User login can see stock level. \label{choice_list}](./03_figures/04_figures/fig_04_03.png)
  
 **Title**: User login is looking to see stock level;
 
 **Actor**: User login;
 
 **Scenario**
 
 *   user select from the menu the option stock level;
 *   the system displays a list of products stock level;
 *   user can select a specific product to see the stock level;
 *   user will see the product stock level;
 *   user logout;
 
 **Alternative Scenario**
    
 At any time before selecting a product, the user can cancel the request and the use case ends.
   
4.  **User login can request a quotation**

![User login can send request for a quotation. \label{choice_list}](./03_figures/04_figures/fig_04_04.png)
  
**Title**: User login is looking to get a quotation;
 
 **Actor**: User login;
 
 **Scenario**
 
 *   user select from the menu the option quotation;
 *   the system displays a list of suppliers;
 *   user can select a specific supplier to be able to send a quote request;
 *   user will send a request via e-mail to the supplier to get a quote for a specific product;
 *   user logout;
 
 **Alternative Scenario**
    
 *  At any time before selecting a supplier, the user can cancel the request and the use case ends.
 *  At any time before sending the request, the user can cancel the request and the use case ends.
 
5.  **User is login to create an user**

![User login request for a login. \label{choice_list}](./03_figures/04_figures/fig_04_05.png)
  
**Title**: User is looking to get user account;
 
 **Actor**: Any user;
 
 **Scenario**
 
 *   user select from the menu the option "Create user";
 *   the system displays a list of user form;
 *   user can complete the form in order to create am user;
 *   user submit the request;
 *   user has crated an user account;
 *   user logout;
 
 **Alternative Scenario**
    
 *  At any time before sending the request, the user can cancel the request and the use case ends. 
 
 
 
6. **User login can add a comment to a product**

![User login can add a comment to a product. \label{choice_list}](./03_figures/04_figures/fig_04_06.png)

**Title**: User is looking to add a comment to a product;
 
 **Actor**: User login;
 
 **Scenario**
 
 *   user select from the menu the option product;
 *   the system displays a list of products;
 *   user select update comment for a specific product;
 *   user write the comment;  
 *   user submit the comment;
 *   user logout;
 
 **Alternative Scenario**
    
 *  At any time before completing the comment, the user can cancel the request and the use case ends. 
 
7.  **User login can add a comment to a product**

![User login can add a comment to a supplier. \label{choice_list}](./03_figures/04_figures/fig_04_06_1.png)

**Title**: User is looking to add a comment to a supplier;
 
 **Actor**: User login;
 
 **Scenario**
 
 *   user select from the menu the option supplier;
 *   the system displays a list of supplier;
 *   user select update comment for a specific supplier;
 *   user write the comment;  
 *   user submit the comment;
 *   user logout;
 
 **Alternative Scenario**
    
 *  At any time before completing the comment, the user can cancel the request and the use case ends. 
    
   
## Manager login: - Use case    ## 

1. **Supplier interface**

![Manager login can add/update/delete/display a supplier. \label{choice_list}](./03_figures/04_figures/fig_04_07.png)
  
**Title**: Manager user is looking to add/update/delete/display a comment to a supplier;
 
**Actor**: Manager login;
 
**Scenario**

 add:
 
 *    Manager login;
 *    Manager login select from the menu button a supplier;
 *    Manager login select from the list of supplier the option New; 
 *    Manager login complete the supplier details form;
 *    Manager login "Save" the details of the supplier; 
 *    Manager login can see in the list of suppliers that a new supplier has been added;
 *    Manager logout;
   

update:

   *    Manager login
   *    Manager login select from the menu button a supplier;
   *    Manager login select from the list of supplier a supplier 
   *    Manager select the option Update for the supplier selected; 
   *    Manager login updates the supplier details form;
   *    Manager login "Save" the details of the supplier; 
   *    Manager login can see in the list of suppliers the changes of supplier details;
   *    Manager logout;

 delete:
 *    Manager login
 *    Manager login select from the menu button a supplier;
 *    Manager login select from the list of supplier a supplier 
 *    Manager login select the option Delete; 
 *    Manager login "Delete" the details of the supplier; 
 *    Manager login can see in the list of suppliers that the supplier has been change;
 *    Manager logout;
   
   

display:

*    Manager login;
*    Manager login select from the menu button a supplier;
*    Manager login select from the list of suppliers select the option display; 
*    Manager login can see the details of the supplier;
*    Manager login can return to the list of the supplier;
*    Manager logout;

2. **Product interface**
   
![Manager login can add/update/delete/display details of a product. \label{choice_list}](./03_figures/04_figures/fig_04_08.png)
  
 **Title**: Manager user is looking to add/update/delete/display details of a product;
  
  **Actor**: Manager login;
  
  **Scenario**

 add:
 
 *    Manager login;
 *    Manager login select from the menu button a product;
 *    Manager login select from the list of product select the option "New"; 
 *    Manager login complete the product details form;
 *    Manager login "Save" the details of the product; 
 *    Manager login can see in the list of products that a new product has been added;
 *    Manager logout;
   

update:

*    Manager login
*    Manager login select from the menu button a product;
*    Manager login select from the list of products a product; 
*    Manager select the option Update for the product selected; 
*    Manager login updates the product details form;
*    Manager login "Save" the details of the product; 
*    Manager login can see in the list of product the changes of product details;
*    Manager logout;


 delete:
 
*    Manager login;
*    Manager login select from the menu button a product;
*    Manager login select from the list of products a product; 
*    Manager login select the option Delete; 
*    Manager login "Delete" the details of the product; 
*    Manager login can see in the list of products that the product has been remove;
*    Manager logout;
   
   

display:

*    Manager login;
*    Manager login select from the menu button a product;
*    Manager login select from the list of products select the option display; 
*    Manager login can see the details of the product;
*    Manager login can return to the list of the product;
*    Manager logout;
 
3. **Stock  interface**
   
![Manager login can create/update/report/display stock. \label{choice_list}](./03_figures/04_figures/fig_04_09.png)
  
 **Title**: Manager user is looking to create/update/report/display stock;
  
  **Actor**: Manager login;
  
  **Scenario**
   

 crete:
 
 *    Manager login;
 *    Manager login select from the menu button stock;
 *    Manager login select the option create stock; 
 *    Manager login complete the stock using a form;
 *    Manager login "Save" the details of the stock; 
 *    Manager login can see in the stock list that the stock level has been created;
 *    Manager logout;
   

update:

 *    Manager login;
 *    Manager login select from the menu button stock;
 *    Manager login select from the list of product the products that have been updated; 
 *    Manager select the option Update for the stock; 
 *    Manager login "Save" the details of the stock; 
 *    Manager login can see in the stock list that stock has been updated;
 *    Manager logout;


 report:
 
 *    Manager login;
 *    Manager login select from the menu button a stock;
 *    Manager login select from the form a period of time; 
 *    Manager login select create the report; 
 *    Manager login can see the report; 
 *    Manager login can return to the stock level list;
 *    Manager logout;
   

display:

 *    Manager login;
 *    Manager login select from the menu button a stock;
 *    Manager login select from the form a period of time; 
 *    Manager login select display; 
 *    Manager login can see the stock display on the screen; 
 *    Manager login can return to the stock level list;
 *    Manager logout;
 
 4. **Quotation interface**
    
![Manager login can request/update/report/display Quotation. \label{choice_list}](./03_figures/04_figures/fig_04_10.png)
  
  **Title**: Manager user is looking to request/update/report/display Quotation;
   
  **Actor**: Manager login;
   
  **Scenario**
    

  request:
  
 *    Manager login;
 *    Manager login select from the menu button quotation;
 *    Manager login select the option request quotation; 
 *    Manager login complete the request using a form;
 *    Manager login a supplier from a list of suppliers;
 *    Manager login "Send" the details of the supplier; 
         *    Suppliers can:
         *    Select from the menu button quotation replay;
         *    Select the option request quotation replay; 
         *    Supplier complete the request using a form;
         *    Supplier "Send" the details of the quote to the user (Manager...);    
 *    Manager login can see in the request list that the quotation has been add to the list of quotation;
 *    Manager logout;
    

 update:
 
  *    Manager login;
  *    Manager login select from the list of quotation the quotation that you want to be updated; 
  *    Manager login select from the menu button quotation;
  *    Manager select the option Update for the quotation; 
  *    Manager login "Save" the details of the quotation; 
  *    Manager login can see in the quotation list that quotations has been updated;
  *    Manager logout;

  report:
  
  *    Manager login;
  *    Manager login select from the menu button a quotation;
  *    Manager login select from the list a quotation; 
  *    Manager login select create the report; 
  *    Manager login can see the report; 
  *    Manager login can return to the quotation level list;
  *    Manager logout;
  

 display:
 
  *    Manager login;
  *    Manager login select from the menu button a quotation;
  *    Manager login select from the list a quotations; 
  *    Manager login select quotation; 
  *    Manager login can see the quotation display on the screen; 
  *    Manager login can return to the quotations list;
  *    Manager logout;
            
5. **Orders interface**

   
![Manager login can add/update/delete/display details of a Orders. \label{choice_list}](./03_figures/04_figures/fig_04_08.png)
  
 **Title**: Manager user is looking to add/update/delete/display details of a Orders;
  
  **Actor**: Manager login;
  
  **Scenario**
   
 
 add:
 
 *    Manager login;
 *    Manager login select from the menu button a orders;
 *    Manager login select from the list of product select the option New; 
 *    Manager login complete the order details form;
 *    Manager login "Save" the details of the order; 
 *    Manager login can see in the list of orders that a new order has been added;
 *    Manager logout;
   

update:

 *    Manager login;
 *    Manager login select from the menu button an orders;
 *    Manager login select from the list of orders an order; 
 *    Manager select the option Update for the order selected; 
 *    Manager login updates the Orders details form;
 *    Manager login "Save" the details of the Orders; 
 *    Manager login can see in the list of Orders the changes of Orders details;
 *    Manager logout;

 delete:
 
*    Manager login;
*    Manager login select from the menu button an orders;
*    Manager login select from the list of orders an order; 
*    Manager login select the option "Delete"; 
*    Manager login delete the details of the order; 
*    Manager login can see in the list of Orders that the Order has been remove;
*    Manager logout;
   

display:

*    Manager login
*    Manager login select from the menu button an orders;
*    Manager login select from the list of orders select the option display; 
*    Manager login can see the details of the orders;
*    Manager login can return to the list of the orders;
*    Manager logout;

              
           

