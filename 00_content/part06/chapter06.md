#  Implementation of System #

The implementation phase involves putting the project plan into action. This is the time to meet the objectives of the project proposal. 
In this phase of the project life cycle: you follow the plan you’ve put together and handle any problems that come up.

The implementation phase is where your project work is done to produce the deliverable. 
On the same time you have to put the documentation together.

## Entity classes ##

As described before, each entity classes are combined key/value classes that are managed by entity.
In this project Supplier with the supplier details, Product with product details, Orders with orders details, user with user details
classes are entity classes. These classes contain fields that are a union of the fields of the key and value classes that
were defined earlier for each store.

For a better understanding it is use the entity "product_details". All other entities are following the same rules. The 
difference between the entity classes defined are just the key and value classes defined earlier is that the entity classes
are not serializable

All the entity classes are saved in directory named `Entity` under `AppBundle`.

The Doctrine has to know what table name this entity should map to. On the same time the data types of each field it is store using annotation comments.
The `use` statement and the definition of the namespace alias are define in each class. 

    namespace AppBundle\Entity;
    
    use Doctrine\ORM\Mapping as ORM;

The first comment is for the class, stating that it is an ORM entity and mapping it to database table `product_details`:
        
        /**
         * product_details
         *
         * @ORM\Table(name="product_details")
         * @ORM\Entity(repositoryClass="AppBundle\Repository\product_detailsRepository")
         */
        class product_details
        
The data/variables inside a class (ex:  `var $ product_Name` ;) are called ‘properties’. Add functions/methods to your class. 
In the same way that variables get a different name when created inside a class (they are called: properties) functions also referred to (by nerds) by a different name when created inside a class – they are called ‘methods’.
A class’s methods are used to manipulate its own data / properties.

Annotations are used to declare the types and the lengths of each field.

    /**
     * @var string
     *
     * @ORM\Column(name="product_Name", type="string", length=255)
     */
    private $productName;

Each class created will contain an 'id'  which is `AUTO_INCREMENT`.

    /**
     * @ORM\Column(type="string", length=100)
     */
    private $name;
    

 Getter and setter functions
 
 To be able to operate with a class we have to define - functions/methods: get_ product_name () and set_ product_name ().It is a convention that getter and setter names should match the property names.
 The getter and setter product_names, match the associated property name.
 This way, when other programmers want to use your objects, they will know that if you have a method/function called ‘set_ product_name ()’, there will be a property/variable called ‘product_name’.

 ## Repository Classes  ##
 
Once we create class and table which match the  entity is easy to create, read, update and delete entries in the projects.
Setting up the skeleton of our class is fairly simple once we figure out exactly what we need. In order to do this, we need the following functions: 

*   newAction - this is the function which will insert a new record to the table; 
*   delete - in the function which will delete the items on the table;
*   editAction - in the function which will update the items on the table;
*   showAction  - this is the function which will show the information from the table; 

Those seem pretty basic, but going through, we’ll notice that a lot of them utilize some similar aspects, so we may have to create more classes. Here is what your class definition should look like. Notice that I made sure that the methods were created with the public keyword.

* public function newAction()

This function allows us to insert a new information into the database. As such we will require an additional argument to the name of the table. We will require a variable that corresponds to the values we wish to input. We can simply separate each value with a comma. Then, all we need to do is quickly check to see if our table exists, and then build the insert statement by manipulating our arguments to form an insert statement. Then we just run our query.

            /**
             * Creates a new suppliers_detail entity.
             *
             * @Route("/new", name="suppliers_details_new")
             * @Method({"GET", "POST"})
             */
            public function newAction(Request $request)
            {
                $suppliers_detail = new Suppliers_details();
                $form = $this->createForm('AppBundle\Form\suppliers_detailsType', $suppliers_detail);
                $form->handleRequest($request);
        
                if ($form->isSubmitted() && $form->isValid()) {
                    $em = $this->getDoctrine()->getManager();
                    $em->persist($suppliers_detail);
                    $em->flush($suppliers_detail);
        
                    return $this->redirectToRoute('suppliers_details_show', array('id' => $suppliers_detail->getId()));
                }
        
                return $this->render('suppliers_details/new.html.twig', array(
                    'suppliers_detail' => $suppliers_detail,
                    'form' => $form->createView(),
                ));
            }


As you can see, this function is a lot simpler than our rather complex select statement. Our delete function will actually be even simpler.

* public function delete()

This function simply deletes a row from our database. As such we must pass the table name and an optional where clause. The where clause will let us know if we need to delete a row or the whole table. If the where clause is passed, that means that entries that match will need to be deleted. After we figure all that out, it’s just a matter of compiling our delete statement and running the query.

      /**
         * Deletes a suppliers_detail entity.
         *
         * @Route("/{id}", name="suppliers_details_delete")
         * @Method("DELETE")
         */
        public function deleteAction(Request $request, suppliers_details $suppliers_detail)
        {
            $form = $this->createDeleteForm($suppliers_detail);
            $form->handleRequest($request);
    
            if ($form->isSubmitted() && $form->isValid()) {
                $em = $this->getDoctrine()->getManager();
                $em->remove($suppliers_detail);
                $em->flush();
            }
    
            return $this->redirectToRoute('suppliers_details_index');
        }

On the same time it is created a for to delete the entity; 
 
       /**
          * Creates a form to delete a suppliers_detail entity.
          *
          * @param suppliers_details $suppliers_detail The suppliers_detail entity
          *
          * @return \Symfony\Component\Form\Form The form
          */
         private function createDeleteForm(suppliers_details $suppliers_detail)
         {
             return $this->createFormBuilder()
                 ->setAction($this->generateUrl('suppliers_details_delete', array('id' => $suppliers_detail->getId())))
                 ->setMethod('DELETE')
                 ->getForm()
             ;
         }
     
* public function  editAction()

This function simply serves to update a row in the database with some new information.
Because of the slightly more complex nature of it, it will come off as a bit larger and infinitely more confusing. Never fear, it follows much of the same pattern of our previous function. First it will use our arguments to create an update statement. It will then proceed to check the database to make sure that the tableExists. If it exists, it will simply update the appropriate row. The hard part, of course, comes when we try and create the update statement. Since the update statement has rules for multiple entry updating (IE – different columns in the same row via the cunning use of comma’s), we will need to take that into account and create a way to deal with it. I have opted to pass the where clause as a single array. The first element in the array will be the name of the column being updated, and the next will be the value of the column. In this way, every even number (including 0) will be the column name, and every odd number will be the new value. The code for performing this is very simple, and is presented below outside the function:
 
     /**
      * Displays a form to edit an existing suppliers_detail entity.
      *
      * @Route("/{id}/edit", name="suppliers_details_edit")
      * @Method({"GET", "POST"})
      */
     public function editAction(Request $request, suppliers_details $suppliers_detail)
     {
         $deleteForm = $this->createDeleteForm($suppliers_detail);
         $editForm = $this->createForm('AppBundle\Form\suppliers_detailsType', $suppliers_detail);
         $editForm->handleRequest($request);
 
         if ($editForm->isSubmitted() && $editForm->isValid()) {
             $this->getDoctrine()->getManager()->flush();
 
             return $this->redirectToRoute('suppliers_details_edit', array('id' => $suppliers_detail->getId()));
         }
 
         return $this->render('suppliers_details/edit.html.twig', array(
             'suppliers_detail' => $suppliers_detail,
             'edit_form' => $editForm->createView(),
             'delete_form' => $deleteForm->createView(),
         ));
     }

Now that we have that we’ve finished our last function, our simple CRUD interface for MySQL is complete. You can now create new entries, read specific entries from the database, update entries and delete things. Also, be creating and reusing this class you’ll find that you are saving yourself a lot of time and coding. Ah, the beauty of object oriented programming.

Doctrine repositories offer us lots of useful methods, including:
        
   * query for a single record by its primary key (usually "id"), used in this application to identified the product from the same suppliers.
         
    $suppliers_detail = $repository->find($id);

   * dynamic method names to find a single record based on a column value, used in this application to identified the supplier which provide a product
   
    $suppliers_detail = $repository->findOneById($id);
    $suppliers_detail = $repository->findOneByName('Alex');

 * find *all* suppliers_detail, used in this application to identified the supplier which provides the same product;
       
       $suppliers_detail = $repository->findAll();

  * dynamic method names to find a group of products based on a value, as an example if you are looking to get all the products that cost 1 euro, you can use the following command:
    
        $products = $repository->findByPrice(19.99);



*   showAction  - this is the function which will display the information from the table; 

        /**
         * Finds and displays a suppliers_detail entity.
         *
         * @Route("/{id}", name="suppliers_details_show")
         * @Method("GET")
         */
        public function showAction(suppliers_details $suppliers_detail)
        {
            $deleteForm = $this->createDeleteForm($suppliers_detail);
    
            return $this->render('suppliers_details/show.html.twig', array(
                'suppliers_detail' => $suppliers_detail,
                'delete_form' => $deleteForm->createView(),
            ));
        }



# System design #

## User Interface ##

This chapter details how the WEB application laid out. The layout it is logical and easy to use, as it determine an interaction with the users, an it determine how an inetraction it is perform by the user. If the instruction are not clear, the 
 the user won't be able to to perform the tasks given. So that may reflect to the pur quality of result from the user perspective of view.
 
1. **Home page** 

The home page will describe the purpose of this site to the user.

![Home page. \label{choice_list}](./03_figures/06_figures/fig_06_01.png)


2.  **User login:**

The user Login support the Use case **"User Login"**
This use case starts when an actor wishes to log into the WEB application. The system requests that the actor enter username and password, after the actor enters username and password.
The system validates the entered username and password and logs the actor into the system.
  
 ![User login. \label{choice_list}](./03_figures/06_figures/fig_06_02.png)


3. **Access  product details**
 
Before the user is able to access the product details it is ask to login. If the login succeed the manager can select from the menu the option product
   
![Manager login can add/update/delete/display details of a product. \label{choice_list}](./03_figures/06_figures/fig_06_03.png)

If the Manager select the option product, He can see the list of product from the database.From the list of product select the option "New" and complete the product details form.

![Add a new product. \label{choice_list}](./03_figures/06_figures/fig_06_04.png)
If you "Save" the details of the product then you can see in the list of products that a new product has been added.

![See a product. \label{choice_list}](./03_figures/06_figures/fig_06_05.png)

It the user would like to edit a Product can select from the list product a product and select the option Update:
 
![See a product. \label{choice_list}](./03_figures/06_figures/fig_06_06.png)
 
Once the user updates the product details can "Save" the details of the product. 
Managers can see in the list of product the changes of product details;

![See the list of products after delete. \label{choice_list}](./03_figures/06_figures/fig_06_07.png)

If a manager wants to delete a product has to select from the list of products a product,Edit the product before he can select the option Delete.  
If the user "Delete" the details of the product, then the changes can be seen on the list of products, so the product has been remove;

4. **Access suppliers details**

Before the user is able to access the suppliers details it is ask to login. If the login succeed the manager 
can select from the menu the option supplier.
 
![Manager login can add/update/delete/display details of a Orders. \label{choice_list}](./03_figures/06_figures/fig_06_08.png)

From the dropped menu the User Manager can select one of the flowing option:

  *    Supplier details;
  *    Supplier address;
  *    Supplier contact;
  *    Bank details; 
  
 If the user will select from option list the "Supplier details" option then the user can see a 
 list of product from the database.
 
 ![List of Suppliers. \label{choice_list}](./03_figures/06_figures/fig_06_09.png)
 
 If the user would lice to access the supplier web page direct from hire can just select from the list of supplier "Suppliers web"
 In this case the user will be aromatically deserted to the supplier WEB page:
  
 ![Access Supplier WEB page. \label{choice_list}](./03_figures/06_figures/fig_06_10.png)  
   
 From the list of Supplier select the option "Create" and complete the Supplier details form.

![Add a new product. \label{choice_list}](./03_figures/06_figures/fig_06_11.png)

If you "Save" the details of the Supplier then you can see in the list of Supplier that a new Supplier has been added.

![See a product. \label{choice_list}](./03_figures/06_figures/fig_06_12.png)

It the user would like to edit a Supplier can select from the list product a product and select the option Update:
Once the user updates the Supplier details can "Save" the details of the Supplier. 
Managers can see in the list of suppliers the changes of supplier details.

If a manager wants to delete a supplier has to select from the list of suppliers a supplier, edit the supplier before he can select the option Delete.  
If the user "Delete" the details of the supplier, then the changes can be seen on the list of supplier, so the supplier has been remove;

For all other Supplier details it can be follow the same cycle.
  
4. **Access orders details**

Before the user is able to access the stock details it is ask to login. If the login succeed the manager can select from the menu the option stock
 
![Manager login can add/update/delete/display details of a Orders. \label{choice_list}](./03_figures/06_figures/fig_06_08.png)

From the dropped menu the User Manager can select one of the flowing option:

  *    Create a PO;
  *    Orders;
  *    Orders details;  
 
  
  
4. **Access orders stock**
 
Before the user is able to access the stock details it is ask to login. If the login succeed the manager can select from the menu the option stock
 
When the user Manager will log in and access the stock option for the first time the stock lavel has to be created. In this case you have 2 option: 

You can add manually each item to the inventory or you can import the items from the list of products. 
 
 