# Magento 2 Training Workbook

This repository contains a list of practice tasks to build skill
important to be a good php engineer. Magento 2 just happens to be a 
tool that we are using here to understand large codebases. Principles 
learned while deep diving into Magento are very similar to principles used
in other frameworks. 

Before you jump into Magento 2 codebase, it's important to understand configurations
available in Magento. Install opensource version on your local machine.Explore at
least few configurations in Store->Configurations section. Do add products, and place an order.
Create a discount coupon and take a look at different options available. Once
you have looked at Magento 2 from users perspective, you are ready for the training.

We do this skill building in 3 phases.
1. Get familiar with database and build SQL skills. Knowing database will help in understanding data structures used in codebase.
2. Use core php and implement a few tools that Magento internally uses.
3. Implement a few interesting Magento 2 extensions.

### How to approach this training. 
Fork this repository. Each task should a folder. Each folder should contain 
solution of the task and readme.md file which contains your notes. For sql files 
solution will be .sql files and for magento extensions it will be installation Magento extensions.

### SQL tasks
1. Write a query to that outputs configurable SKU and simple SKU .
2. Write a query to output all the configurable products which are disabled
3. Write a query to fetch all the products which belong to a particular category
4. Write a query to print Order increment ID and which skus were ordered in the order. There should be only one row per order.
5. Write a query to print all the order which have at least one product that is now disabled
6. Write down your understanding of why ui_bookmark table is used?
7. Write a query that outputs, SKU and pretty URL of the product that is seen on the fronend.
8. Delete a few product URLS from URL table. Now write a Query to fetch all the products which do not have entry in url_rewrite using a join
9. Write a query that queries information_schema table to find out all the tables which contain a column named sku
10. Write down a query to find all the orders  which have more that 2 items. Output should contain number of items and order increment id
11. Write a Query to find all the outof stock SKU's
12. Before doing operations on catalog_product_entity table you need to backup the table. How will you copy the table into another table named catalog_product_entity_backup
13. Write a query to find out of all the SKU's which have numbers in them. Use Regex
14. Find bestselling products
15. Find products that were created more than 6 months ago but have not been ordered yet
16. Find top 5 customers based on number of orders they have placed

### Core php

1. Write a program to consume more than 300MB's memory. Now reduce memory limit and see what error do you get.
2. Create an empty class named Foo . Do no define any method or properties. Now create an instance of Foo an call method ->bar() see what error you get. Now make this error go away by using __call ? What else can you do with __call.
3. Just like call, implement 1 example of each Magic method in php
4. Write  program in php (OOP style) which analyses schema of all the tables in database. a) It should be able to print tables and unique indexes on the table b) table and composite indexes on the table c.) Foreign keys in the tables.
5. Modify the program given above to solve following real life problem.
   "Queries perform better when they can use indexes on the table. Which columns to index depends on which columns are used the most in most of the queries. Write a program which takes a query log as input and compares it with schema of the table. The program should suggest which indexes are unneccesary and which columns should have indexes. Make your notes on when this program won't work or when would this program give wrong results. Generate query log by using mysql query log configuration"
6. Write a php script to parse nginx log lines and convert each log line into a JSON
7. Create examples of code that trigger various fatal errors and other errors. 1. Execution time exceeded, memory limit exceeded , undefined index, mysql connection failed, invalid query syntax. Research on various php errors you can get and write snippets. This task is important to get comfortable looking at error strings.


### Magento 2 tasks
1. Create a Magento extension that allows super admin user to login with a pre-defined password which is stored in app/etc/env.php Only super admin should be able to use this predefined key. This task should give you understanding of how magento admin authentication works
2. Write Magento extension that allows Magento admin to bypass authentication if IP is 127.0.0.1 (which is your local environment)
3. Write a Magento command that takes comma separated skus as arguement, adds them to cart and prints grand_total. Hardcode a shipping and billing address. This task should familirize you with some internals of add to cart.
4. Create a index.php on your localmachine accessible at localhost/index.php This index.php should store what ever is posted to this URL in a file. Now write a magento extension that posts order data to localhost/index.php whenever an order is placed. Use an observer to do this.
5. In last extension that we created, we hardcoded the URL, now create admin grid which allows admin user to add new URL's, username and password required to access that URL. How will you ensure that your feature works?
6. Write a extension to make shipping price zero if customer_email contains a number.
7. Write a cron system to send a coupon code to customer on there birthday and wish them happy birthday in email
8. Create Two extensions. First extension should render a hello world page. You would have to create route,controller, layouts and templates. After your layout is rendered, create second extension that will add your name to Hello world page of the first extension.
9. Create Magento extension to apply 10 percent discount if customer_id is divisible by 3
10. Create extension to fullfill following requirement. If the product price is greater than 100rs then non-logged in user should not be able to add that product to cart. Meaning, Only logged in customers should be able to add to cart if product price is greater than 100rs. Show user error message that "You need to log-in for adding any product worth 100Rs or more" In your assignment notes note down cases that you have'nt covered.
11. 


