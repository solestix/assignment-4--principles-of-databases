# Fall 2024 Principles of Databases — Assignment 4

* **Do not start this project until you’ve read and understood these instructions. If something is not clear, ask.**

---

## ❖ Introduction ❖

For this assignment, you will write responses to nine questions based on different topics from our textbook, *Database Systems — The Complete Book* and to one question based on your notes. Reply to each question in the provided region using Markdown syntax.

---

## ❖ Questions ❖

### 1. [2.4] What is the difference between a Cartesian Product, a Natural Join, and Theta-Joins?

A cartesian product is a cross-join of two tables that includes all pairs of tuples from the two tables as tuples. For example, a cartesian-product of table A with 3 tuples and table B with 4 tuples would have 12 total tuples, where each includes a tuple from A joined with a tuple from B. A natural join is like a cartesian product except it only includes rows of joined tuples that share an attribute, then duplicate attributes are deleted. A natural-join joins two tables only where a specified condition is met. For example, you could theta-join two tables where an attribute from one table is greater than the other. The resulting table would include all joined tuples where that condition is met.

### 2. [2.5] What is a Referential Integrity Constraint?

A Referential Integrity Constraint is a rule in a relational database that ensures the consistency of relationships between tables. It enforces the validity of references by ensuring that any foreign key value in one table either matches a primary key value in another table or is null. This constraint is essential for maintaining data accuracy and logical consistency across the database. For example, say there are two tables in a database, orders and customers, and both of these tables have a customer_id attribute. In order for a tuple in orders with customer_id 3 to exist, there must be a tuple in customers with customer_id 3. This is a referential integrity constraint that could be implemented with a foreign key. This referential integrity constraint enforces that the database reflects reality, because in order for a customer to make an order, that customer must exist.

###  3. [2.5] What is a Key Constraint?

A key constraint is a rule in a relational database that ensures uniqueness of entries and relationships between tables. For example, one type of key constraint is a primary key. Primary keys are attributes whose values must be unique in their table. This ensures uniqueness for attributes that would only appear once in a table, like an attribute called social_security_num in a table called citizens. There can be two tables with one of the same primary key attributes. This shared attribute relates the two tables together, like a citizens and a tax_form table that both share an attribute called social_security_num. Shared primary keys like this can be used to join two tables together.

### 4. [4.1] What is an Entity/Relationship Model? What purpose does it serve in the process of creating/designing databases?

An ER model is a high-level representation of a relational database. An ER model includes entity sets, the attributes of those sets, and relationships between those sets. ER models are created with the real world in mind, so that when you implement the database, there are constraints that ensure entries match the real world. The purpose of an ER model is to visualize a relational database before it is implemented. In the process of making or overlooking an ER model, it will inform you on how to logically set up the database.

### 5. [4.4] What is a Weak Entity Set?

A weak entity set is an entity set that depends on a strong entity set to exist. There is always a one-to-many relationship between a weak and strong entity set. Instead of having it's own unique primary key, a weak entity set has the primary key of its associated strong entity set and at least one other attribute to distinguish itself from other weak entity sets that are linked to the same strong entity set.

### 6. [5.2.7; 6.3.8] Explain the concepts of Outerjoin, Natural Right Outer Joins, Natural Left Outer Joins, and Full Outer Joins.

There are three types of outer joins, a left, right, and full outer join. Say there are two tables, A and B, that are being outer-joined. If that is a left outer join, the resulting table will include all tuples from table A paired with tuples from table B that match on some attribute. If no tuples from table B match with a tuple from table A, then the rest of the row corresponding with that tuple in table A in the resulting join will be NULL. A right outer join is the same concept as a left outer join, except it contains all tuples from the right table (table B) paired with any matching tuples from the left table. A full outer join contains the results from both the left and right outer joins. It contains all tuples from both tables matched wherever there is a match, and NULL for any attributes that are unmatched in a tuple.

### 7. [6.6.3] What is the difference between the SQL command `TRANSACTION` and the execution of any statement in SQL?

Any individual SQL statement (SELECT, INSERT, UPDATE, DELETE) is executed as a single, atomic operation by default. A transaction groups multiple SQL statements into a single unit of work, ensuring that they are executed together or not at all (atomicity). During the execution of a transaction if something fails, it can be rolled back, this ensures atomicity. One SQL statement is atomic by itself, being that nothing changes if it fails. However, if an action you want to take on a database consists of multiple statements, if a statement fails in the middle of that action, data could be ruined and the statements have to be manually rolled back one by one. The TRANSACTION command lets you have atomicity on a multi-step process.

### 8. [8] What is a Virtual View and what are its advantages?

A virtual view is a temporary table that contains the results of some query on a database. It does not store data physically but dynamically retrieves the data from the underlying base tables when queried. The resulting view can be referenced or changed after it is created, allowing an SQL user to keep track of the information in the view. Changing a view can result in a change in the actual database, but only if the view was created from one table. For example, if you wanted to delete a number of entries from a large table, you could create a view that contains a subset of that table. Then, you can delete from the view as you please and the changes will be reflected in the database. Another advantage of virtual views is security. If you wanted to display information from a database on a website with some private attributes excluded, the you could have your site create and display a view selecting only the attributes the user is allowed to see.

### 9. [8.3] What is an *index* and what are its advantages?

An index in SQL is a database object that enhances the speed of data retrieval operations on a table. It is similar to an index in a book, allowing the database to quickly locate rows without scanning an entire table. An index is created on one or more columns of a table and is stored separately from the table data. Internally an index is a binary search tree of key value pairs of attributes and their location. Binary search trees are much faster to navigate than a whole table for one attribute, so creating a table can save a lot of time if one attribute is frequently mentioned in queries.

### 10. Explain the concept of an MVC, or model, view, controller, framework for designing full stack applications

The MVC framework is a software design framework that is commonly used for building full-stack applications. It consists of three interconnected layers, the model, the view, and the controller. The model is the hidden data layer of an application that handles querying the database. The view is the layer that presents actions and data to an application user. The controller is the intermediary layer that connects the model and the view. The controller processes input from a user, performs CRUD operations on the model accordingly, then tells the view what to display.

---

## ❖ Due ❖

Sunday, 15 December 2024, at 10:00 AM.

---

## ❖ Grading ❖

| Item        | Points |
|-------------|:------:|
| Question 1  | `10`   |
| Question 2  | `10`   |
| Question 3  | `10`   |
| Question 4  | `10`   |
| Question 5  | `10`   |
| Question 6  | `10`   |
| Question 7  | `10`   |
| Question 8  | `10`   |
| Question 9  | `10`   |
| Question 10 | `10`   |

---

## ❖ Submission ❖

**NO late submissions will be accepted.**

You will need to issue a pull request back into the original repo, the one from which your fork was created for this project. See the **Issuing Pull Requests** section of [this site](http://code-warrior.github.io/tutorials/git/github/index.html) for help on how to submit your assignment.

**Note**: This assignment may **only** be submitted via GitHub. **No other form of submission will be accepted**.
