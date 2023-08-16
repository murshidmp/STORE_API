
# **Store API**

Store API is a backend application built using Node.js, Express.js, and MongoDB for managing and retrieving product information. The API allows you to fetch products, apply filters, and retrieve information based on different query parameters.


## **Table of Contents**



* [Project Structure](https://chat.openai.com/#project-structure)
* [Getting Started](https://chat.openai.com/#getting-started)
    * [Installation](https://chat.openai.com/#installation)
    * [Running the Application](https://chat.openai.com/#running-the-application)
* [API Routes](https://chat.openai.com/#api-routes)
* [Database Connectivity](https://chat.openai.com/#database-connectivity)
* [Populating the Database](https://chat.openai.com/#populating-the-database)
* [Error Handling](https://chat.openai.com/#error-handling)
* [Configuration](https://chat.openai.com/#configuration)
* [Contributing](https://chat.openai.com/#contributing)
* [License](https://chat.openai.com/#license)


## **Project Structure**

The project follows a well-organized structure with modular components for better maintainability and scalability.

go

Copy code


```
Store_API/
┣ controllers/
┃ ┗ products.js
┣ db/
┃ ┗ connect.js
┣ middleware/
┃ ┣ error-handler.js
┃ ┗ not-found.js
┣ models/
┃ ┗ product.js
┣ routes/
┃ ┗ products.js
┣ app.js
┣ .env
┣ .gitignore
┣ README.md
┣ package-lock.json
┣ package.json
┣ populate.js
┗ products.json
```



## **Getting Started**


### **Installation**



1. Clone this repository to your local machine.
2. Navigate to the project directory and install the dependencies:

bash

Copy code


```
npm install
```



### **Running the Application**

To run the Store API application, follow these steps:



1. Create a `.env` file in the root directory with the following content:

env

Copy code


```
MONGO_URI=your-mongodb-connection-string
PORT=3000
```


Replace `your-mongodb-connection-string` with your actual MongoDB connection string.



1. Start the application:

bash

Copy code


```
npm start
```


The API server will start on the specified port (default is 3000).


## **API Routes**

The API provides the following routes for managing products:



* `GET /api/v1/products`: Retrieve a list of products based on query parameters like `featured`, `company`, `name`, `sort`, `fields`, and `numericFilters`.
* `GET /api/v1/products/static`: Retrieve a list of products with a static filter where the price is greater than 30.


## **Database Connectivity**

The database connection is established using the `connect.js` file located in the `db` directory. The application connects to the MongoDB database using the connection URI provided in the `.env` file.


## **Populating the Database**

To populate the database with sample product data, you can use the `populate.js` script. This script connects to the database, deletes existing products, and creates new products using the data from `products.json`.

To populate the database, run:

bash

Copy code


```
node populate.js
```



## **Error Handling**

The application handles errors using middleware located in the `middleware` directory. The `error-handler.js` middleware is responsible for sending appropriate error responses.


## **Configuration**



* The `.env` file is used to store configuration variables like the MongoDB connection URI and port number.


## **Contributing**

Contributions are welcome! If you find any issues or have suggestions for improvements, feel free to open an issue or create a pull request.


## **License**

This project is licensed under the[ MIT License]
