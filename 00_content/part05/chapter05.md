# Database design #

In today's fast-moving environment with short lead times, getting the right goods, delivered on time, at the agreed price is important.
Inevitably without a formal system in place you will always need the goods in a hurry in order to complete a job.
You can also record your supplier details against your purchase orders. Any discrepancies will be visually 
so you can see if you have been overcharged.

The objective of this assessment is to the design the full data requirements required by the material control for hotels system.
 
This must include:

*	Product details including details and inventory.
*	Orders which will include the details in regards list of PO, orders, orders details. 
*   Suppliers with all details, including address, contact details and bank details. 	
*   Stock details
*   Quotation dequest details and suppliers responses details.
*	User details including name, address, phone number, e-mail, and specialisation and log in details.


## Product details  ##

The table will contain details about a product used in the hotel  including its name, price, description,
 and ordering options. It also includes a link to the offer listing page, which includes offers from sellers as well and allows users to quickly make price comparisons.

![Product details. \label{choice_list}](./03_figures/05_figures/fig_05_01.png)

![Product Inventory . \label{choice_list}](./03_figures/05_figures/fig_05_02.png)

## PO - purchase order   ##

A purchase order, or PO, is an document issued by the Hotel to pay the seller for the sale of specific products or services to be delivered in the future.
A PO specifies: quantity purchased, product or service purchased, price per unit, delivery date, 
delivery location, payment terms, such as on delivery or in 30 days

Each PO has a unique number associated with it that helps both buyer and seller track delivery and payment.

![PO details. \label{choice_list}](./03_figures/05_figures/fig_05_03.png)

Orders will contain general indormation about whom and when en PO have been place.

![Orders. \label{choice_list}](./03_figures/05_figures/fig_05_04.png)

Where the Order will hold general information about the product order. 

![Orders details. \label{choice_list}](./03_figures/05_figures/fig_05_05.png)

##   Quotation   ##

Quotation refers to stock quote. A stock quote is an estimate of price or a price at which one party is willing to buy  a certain number of shares of stock from the other.
A quotation consists of a bid price and an ask price. A Quotation specified who request the price, the product name, and description, date of request.
 
![Quotation. \label{choice_list}](./03_figures/05_figures/fig_05_06.png)

To be able to get a quote in real time the suppliers can access the WEB application and respond to the request. In this case the information stored are:
supplier ID, product group, quantity, price, description and a link to the product if exist online. 

![Supplier quotation. \label{choice_list}](./03_figures/05_figures/fig_05_12.png)

##   Stock   ##

The stock of the hotel is the amount of goods, such as parts, materials, and finished products, that a company has available at a particular time.
They are depleting their stock on hand before ordering new inventory. So the information kept on the table are: 

![Stock. \label{choice_list}](./03_figures/05_figures/fig_05_07.png)

##  Supplier    ##

A supplier is a person or entity that is the source for goods or services. 
The information store when you come to this are huge. You don't wand that all information store in regards to your supplier to be seen. In this case the information will be distributed in different table, each one 
having specific information: supplier details, supplier address, contact details for the supplier and the bank details as follow:  
Supplier details:

![Supplier details. \label{choice_list}](./03_figures/05_figures/fig_05_11.png)
    
Supplier address:

![Supplier address. \label{choice_list}](./03_figures/05_figures/fig_05_08.png)

Supplier contact person details:

![Supplier contact person details. \label{choice_list}](./03_figures/05_figures/fig_05_10.png)

Supplier contact: 

![Supplier bank details. \label{choice_list}](./03_figures/05_figures/fig_05_09.png)

## User details  ##

The User Details side of WEB application comes with two blocks: "User LOGIN" which will hold basic information about login and "User Details": which will hold general information about each person which access the information.

![User LOGIN. \label{choice_list}](./03_figures/05_figures/fig_05_14.png)

![User details. \label{choice_list}](./03_figures/05_figures/fig_05_13.png)

##   EED Diagram  ##

An entity-relationship model (ERM) is a theoretical and conceptual way of showing data relationships in 
software development. ERM is a database modeling technique that generates an abstract diagram 
or visual representation of a system's data that can be helpful in designing a relational database.
For a better understanding between the table in the database, was used a graphical representation of
entities and their relationships to each other. 

![EED Diagram. \label{choice_list}](./03_figures/05_figures/EEDDiagram.png)