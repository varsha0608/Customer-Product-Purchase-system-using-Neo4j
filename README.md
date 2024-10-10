
# Customer-Product Purchase System

This project demonstrates how to build a knowledge graph using **Neo4j** and **Python** (via the `py2neo` library) to model customer purchases and recommend new products based on their purchase history and interactions with product categories. The knowledge graph allows for personalized product recommendations to improve customer engagement and sales.

## Features
- **Graph Schema**: Models relationships between customers, products, and categories.
- **Data Ingestion**: Adds customers, products, categories, and relationships in a batch.
- **Personalized Recommendations**: Suggests products to customers based on their previous purchases and category interactions.
- **Query Capabilities**: Finds products purchased by a customer and recommends new products based on shared categories.

## Project Structure
- **`customer_product_graph.py`**: Contains the main implementation for creating and managing the customer-product purchase knowledge graph using Neo4j.
- **`requirements.txt`**: Lists the required Python packages for the project.
- **`README.md`**: Instructions for setting up and using the project.

## Prerequisites

1. **Neo4j**:
   - Install Neo4j on your local machine. You can download it from [Neo4j Download Center](https://neo4j.com/download/).
   - Start Neo4j and ensure it's running on `localhost:7687`.
   - Set the default Neo4j username and password (usually `neo4j` and `password`).

2. **Python**:
   - Ensure you have Python 3.x installed on your machine.


## Usage

1. **Configure Neo4j Credentials**:
   Open the `customer_product_graph.py` file and modify the following line if your Neo4j server uses different credentials:
   ```python
   graph = CustomerProductGraph(uri="bolt://localhost:7687", user="neo4j", password="your_password")
   ```

2. **Running the Script**:
   To run the knowledge graph example, use:
   ```bash
   python customer_product_graph.py
   ```

   The script will:
   - Clear the existing graph (optional).
   - Add customers, products, and categories.
   - Define relationships (e.g., which customer purchased which product, which product belongs to which category, etc.).
   - Query the graph to find products purchased by a specific customer and recommend products based on category preferences.

3. **Queries**:
   The script provides sample outputs for the following operations:
   - **Products purchased by a customer**: Find which products a specific customer has purchased.
   - **Recommendations for a customer**: Suggest products based on categories of products the customer has previously purchased.

4. **Customizing Data**:
   You can modify the customers, products, and categories in the code to create your own data set and relationships.


## Modifying the Graph

To add new customers, products, or categories, or to create new relationships, simply modify the code in `customer_product_graph.py`. For example, to add more products:

```python
products = ["Laptop", "Phone", "Tablet", "Smartwatch", "Headphones"]
graph.add_products(products)
```

## Neo4j Browser

You can also explore the data visually in the Neo4j browser by opening [http://localhost:7474](http://localhost:7474) and running the following query:

```cypher
MATCH (n) RETURN n
```

This will show you all the nodes and relationships in your knowledge graph.

