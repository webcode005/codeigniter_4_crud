# codeigniter_4_crud
Learn CRUD Operation Using Codeigniter 4

Codeigniter4

Just Follow below Steps:

0) You need to install Composer first, if you already installed you can skip this step.
1) Open your working folder, if you are using xammpp you need to open htdocs directory.
2) Now open CMD and go to htdocs folder, and run the composer command given below.
   composer create-project codeigniter4/appstarter ci4_crud

   Note: make sure  *intl* and *mbstring* extension installed.

3) To access the project in browser, we need top open ci4_crud in CMD and run the command given below.
   php spark serve
    If, you see a welcome screen it means, you have successfully installed Codeigniter 4 project.

4) Create a database called ci4_latest with a table called "books", that we will use in our CRUD application
   id, title, isbn_no, author, created_at
5) Create a controller called "Book" inside the following directory.
   app\controllers\Book.php

6) Now inside "Book" controller, we'll create a method called "index". This method will load our 
   first landing page, which will hold the listing of books in a tabular form.

7) Open routes.php and create a "Get" route for books listing.

8) We will use bootstrap 4 for our project, you can download bootstrap files from my github account.
   ci4_assets-master folder

9) Create a folder name "assets" inside public directory and paste the "css" and "js" folder there.
   
10) Now, we will create a view called "list.php" inside sub folder  called "books" in views 
    directory, directory given below.    
    app\views\books\list.php

11) Let's load our "list.php" view in "index" method of Book Controller class and create some basic 
    structure for our CRUD APP in our "list.php" view.

############# Create 
12) Now we'll create function in "Book Controller" that will load our create form
    Location: app\Controllers\Book.php

13) Now in routes.php file we need to define a get route.

14) Let's create a view called "create.php" in the location given below. And load this view in in 
    create method of "Book Controller"
    Location: Views/books/create.php

15) Lets create our create form inside "create.php" view.    

16) In "create" method of "Book" Controller, we'll validate our form, and then save values in DB.

17) Before save we need to create a model which will interact with database and save values in DB, 
    we will create a model called "BookModel.php" in following location. 
    App\Models\BookModel.php
    Note: Make sure define allowed fields in model
    protected $allowedFields = ['title','isbn_no','author'];

19) Now after save we will redirect user with a flash session message
    
    Winner Winner Chicken Dinner, you have successfully completed create part.


 ############# Read 

20) Now, we have to create a method called "getRecords()" in "BookModel.php" which will fetch all 
    records from database.
21) In "BookController" we'll call "getRecords()" method and then we'll pass array to "list.php" view
    to list records using foreach loop.


############# Edit / Update

21) First we'll modify "list.php" and add link on "Edit" button.
22) When you click the edit button it'll show you 404 not found page because we did't not created a 
    method which will load "edit" book page. 
23) Let's create a "edit" method inside "Book Controller", which will show edit page.
24) Create a route for "edit" book page inside "route.php"

25) Create a "edit.php" view inside views folder. And copy the code of "create.php" view and 
    paste in "edit.php" view.
    Location: Views/books/edit.php

26) Copy the code of "create" method and paste inside "edit" method in "Book Controller", load edit view 
    instead of "create" in edit method of "Book Controller", let's modify the "edit" view.

27) As we need to prefill the "edit.php" form, we need to fetch from database, so we'll create a "getRow()"
    method in "BookModel" which will fetch a single row from DB.

28) Now we'll update the record using update method.

    Winner Winner Chicken Dinner, you have successfully finished Update part.

    ---------------------------------------------------------------------------------------

############# Delete Part

29) In this step we'll create a "deleteConfirm()" javascript method, which will confirm if user wants to delete 
    the record?

30) Let's create a method called "delete()" in Book controller which will handle delete logic.

31) After delete from database will redirect to listing page with a delete confirmation message.

    Winner Winner Chicken Dinner, you have successfully finished delete part.
