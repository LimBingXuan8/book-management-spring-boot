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

```

2. Import the provided POSTMAN collection into POSTMAN by clicking on the "Import" button and selecting the file "book-management-api.postman_collection.json".

3. In POSTMAN, select the appropriate endpoint from the imported collection and click the "Send" button to test the API.
