# Pizza Sales SQL Project

## Project Overview

This project involves analyzing pizza sales data using SQL. The data is divided into four CSV files:

1. `pizzas.csv`
2. `pizza_type.csv`
3. `orders.csv`
4. `order_details.csv`

The objective is to perform various SQL queries to gain insights into sales performance, popular pizza types, and customer order patterns.

## Data Files

### `pizzas.csv`

Contains information about the pizzas sold.

- `pizza_id`: Unique identifier for each pizza
- `pizza_type_id`: Identifier for the type of pizza
- `size`: Size of the pizza (e.g., small, medium, large)
- `price`: Price of the pizza

### `pizza_type.csv`

Contains detailed information about each type of pizza.

- `pizza_type_id`: Unique identifier for each type of pizza
- `name`: Name of the pizza type
- `category`: Category of the pizza (e.g., classic, gourmet)
- `ingredients`: List of ingredients used in the pizza

### `orders.csv`

Contains information about each order placed.

- `order_id`: Unique identifier for each order
- `date`: Date when the order was placed
- `time`: Time when the order was placed

### `order_details.csv`

Contains details about the pizzas included in each order.

- `order_detail_id`: Unique identifier for each order detail entry
- `order_id`: Identifier linking to the orders table
- `pizza_id`: Identifier linking to the pizzas table
- `quantity`: Number of pizzas of the specified type included in the order

## Setting Up the Project

1. **Clone the Repository**: Clone this repository to your local machine using the command:
    ```sh
    git clone https://github.com/yourusername/pizza-sales-sql.git
    ```

2. **Import the Data**: Import the CSV files into your SQL database. You can use a tool like MySQL Workbench, pgAdmin, or any other SQL management tool.

3. **Database Schema**: Create tables in your database corresponding to the structure of the CSV files. You can use the following SQL commands as a reference:

    ```sql
    CREATE TABLE pizzas (
        pizza_id VARCHAR(50) PRIMARY KEY,
        pizza_type_id VARCHAR(50),
        size VARCHAR(50),
        price DECIMAL(10, 2)
    );

    CREATE TABLE pizza_type (
        pizza_type_id VARCHAR(50) PRIMARY KEY,
        name VARCHAR(100),
        category VARCHAR(50),
        ingredients TEXT
    );

    CREATE TABLE orders (
        order_id VARCHAR(50) PRIMARY KEY,
        date DATE,
        time TIME
    );

    CREATE TABLE order_details (
        order_detail_id VARCHAR(50) PRIMARY KEY,
        order_id VARCHAR(50),
        pizza_id VARCHAR(50),
        quantity INT,
        FOREIGN KEY (order_id) REFERENCES orders(order_id),
        FOREIGN KEY (pizza_id) REFERENCES pizzas(pizza_id)
    );
    ```

4. **Load the Data**: Load the data from the CSV files into the corresponding tables using SQL commands or your SQL management tool's import feature.

## Contribution

If you would like to contribute to this project, please fork the repository and create a pull request with your changes.

## License

This project is licensed under the MIT License.
