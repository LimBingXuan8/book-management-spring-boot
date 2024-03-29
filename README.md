# Spring Boot Book Management API
This is a Java Spring Boot application that provides an API to manage books. The API allows you to create, read, update and delete books, and also retrieve books by author, title or ISBN. In addition, the API integrates with the Google Books API to retrieve additional information about books.

The endpoints of the API are as follows:
| Endpoint | HTTP Method | Description |
| -------- | ----------- | ----------- |
| /books  |  GET | Retrieves a list of all books  |
| /books/{id}  |  GET | Retrieves a book by ID  |
| /books  |  POST | Creates a new book  |
| /books/{id} |  	PUT | Updates an existing book by ID  |
| /books/{id} | DELETE | Deletes a book by ID  |
| /books/author/{author} |  GET | Retrieves a list of books by author  |
| /books/title/{title}  |  GET | Retrieves a list of books by title  |
| /books/isbn/{isbn}  |  GET | 	Retrieves a book by ISBN  |


## Setting up the project on your local computer
To set up the project on your local computer, please follow these steps:
1. Clone the repository:
```
git clone https://github.com/LimBingXuan8/book-management-spring-boot.git
```

2.Navigate to the project directory:
```
cd book-management-spring-boot
```

3. Build the project using Maven:
```
mvn clean package
```

4. Run the project using Maven:
```
mvn spring-boot:run
```


## Setting up the MSSQL server on your local computer
1. Open SQL Server Management Studio and connect to the server. Make sure it runs on port 1433

2. Create a new database called "TESTDB" by executing the following SQL command:
```
CREATE DATABASE TESTDB
```

3. Create a new user with full privileges on the "TESTDB" database by executing the following SQL command:
```
CREATE USER 'your_username_here'@'localhost' IDENTIFIED BY 'your_password_here';
GRANT ALL PRIVILEGES ON TESTDB.* TO 'your_username_here'@'localhost';
FLUSH PRIVILEGES;
```
Replace the 'your_username_here' and 'your_password_here' with your desired username and password, respectively. And don't forget to update your application properties file accordingly.



## Testing the API using POSTMAN
1. Download the POSTMAN collection from the link below:
```
https://drive.google.com/file/d/1sAbYYWpX6JG3qdwTraxo_u8y7Ln-wOwi/view?usp=sharing
```

2. Import the provided POSTMAN collection into POSTMAN by clicking on the "Import" button and selecting the file "book-management-api.postman_collection.json".

3. In POSTMAN, select the appropriate endpoint from the imported collection and click the "Send" button to test the API.


## A checklist of the requirements and explanation as to how they have been met:
- [x]  1. Create a Java Spring Boot Application

    The project is created using Spring Boot

- [x] 2. Project Structure

    The project follows a clear structure with separate packages for models, controllers, services, repositories, exceptions, and clients.

- [x] 3. Explore API for Client

    The API has several endpoints that can be tested via Postman. 

- [x] 4. Log REQUEST & RESPONSE info

    Using Spring Boot's default logging capabilities, request and response information are logged into the book-management-system.log file. 

- [x] 5. Connect to the MSSQL database

    The application connects to an MSSQL database (TESTDB) running on the local machine. The @Transactional annotation is implemented for the required HTTP methods         (INSERT, UPDATE, GET).

- [x]  6. GET method with Pagination

    The API includes a GET endpoint for retrieving books with pagination support. It returns 10 records per page.

- [x] 7. Nested API calls

    The application demonstrates a nested API call by integrating with the Google Books API when updating a book with an ISBN. The Google Books API returns a preview       link, which is saved in the database.
