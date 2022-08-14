# API Requirements
The company stakeholders want to create an online storefront to showcase their great product ideas. Users need to be able to browse an index of all products, see the specifics of a single product, and add products to an order that they can view in a cart page. You have been tasked with building the API that will support this application, and your coworker is building the frontend.

These are the notes from a meeting with the frontend developer that describe what endpoints the API needs to supply, as well as data shapes the frontend and backend have agreed meet the requirements of the application. 

=============================================================================

> ## API Endpoints

### *Users Routes*

`Index`  : get all the users.
GET localhost:3000/api/users

`Show`  : get user with id.
GET : localhost:3000/api/users/{{user_uuid}}

`Create` : add a user 
POST : localhost:3000/api/users

`Update` : update a user using put http method, 
PUT : localhost:3000/api/users/{{user_uuid}}

`Update` : update a user using patch http method
PATCH : localhost:3000/api/users/{{user_uuid}}

`Authenticate` : authenticate a user  if the password is correct  return all the user's info ;else  return null.
GET : localhost:3000/api/users/auth/{{user_uuid}}
Content-Type: application/json

`Delete` : delete a user, 
DELETE : localhost:3000/api/users/{{user_uuid}}

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

### *Products Routes*
`Index`  : get all the products.
GET: localhost:3000/api/products

`Show` : get a specific product with uuid.

GET : localhost:3000/api/products/{{product_uuid}}

`IndexCategory/{{category}}`  : get all the products by category.
GET : localhost:3000/api/products/indexByCategory/vegetables

`Create` : create a new product.

POST : localhost:3000/api/products

`Update` : update a product using put http method.
PUT : localhost:3000/api/products/{{product_uuid}}

`Update` : update a product using patch http method.

PATCH : localhost:3000/api/products/{{product_uuid}}

`Delete` : to delete a specific order.
DELETE : localhost:3000/api/products/{{product_uuid}}

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

### *Orders Routes*

`Index` : to get all of the orders.
GET : localhost:3000/api/orders

`Show` : get a specific order.
GET : localhost:3000/api/orders/{{order_uuid}}

`Create` [token required] : create a new order.
POST : localhost:3000/api/orders

`Update` : update an order using put http method 
PUT : localhost:3000/api/orders/{{order_uuid}}

`Update` : update an order using patch http method
PATCH  : localhost:3000/api/orders/{{order_uuid}}

$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$

> ## Tables' structures - Database Schema

### *users Schema*
-  id
-  firstname
-  lastname
-  username
-  email
-  password

CREATE TABLE users (
- id serial PRIMARY KEY,
- firstname VARCHAR (100),
- lastname VARCHAR (100),
- username  VARCHAR (100),
- email     VARCHAR (100),
  password VARCHAR (100)


### *products Schema*
-  id
-  name
-  price

CREATE TABLE products(
   - id serial PRIMARY KEY,
   - name VARCHAR(50) ,
   - price INTEGER 
 
);

### *Orders Schema*
-  id
-  status
-  quantity
-  user_FK_id
-  product_fk_id

CREATE TABLE orders(
id            SERIAL PRIMARY KEY,
quantity      INTEGER,
status        BOOLEAN ,
user_fk_id       INTEGER NOT NULL REFERENCES users (id),
product_fk_id    INTEGER NOT NULL REFERENCES products (id)
);
