#### Definitions
- **Database**: An organised collection of data
- **Relational database**: Database made up of a collection of related tables (relations)
- **Entity**: A category of object
- **Attributes**: Properties of an entity
- **Entity descriptions**: Written as `entity_name(attribute1, attribute2...)`. The entity identifier or primary key is underlined.
- **Entity identifier / primary key**: Each entity must have attribute to uniquely identify each record - the primary key (underlined in the entity description) Sometimes a combination of non-unique attributes can be combined to make a composite unique identifier.
- **Foreign keys** are used to form relationships between two entities. It is an attribute common to both entities. Foreign keys are italicised.

#### Normalisation
**Normalisation** is a process to ensure that data in a relational database is stored in most efficient way. In a normalised database, there is no redundant data, each item of data is stored in correct table and is at an atomic level. Atomic means split to a level where it cannot be further decomposed.

**First normal form**
- Tables do not contain repeating attributes or groups
- Data is atomic 
- Will sometimes result in composite primary key

**Second normal form**
- 1NF must be achieved first 
- A database in 1NF may already meet 2NF  
- Every non-primary key attribute must depend on the whole of the primary key  
- Relations may be split into 2 or more relations

**Third normal form**
- 2NF must be achieved first  
- A database in 2NF may already meet 3NF  
- Every non-primary key attribute must be solely dependent on the primary key to separate relations - it can't be dependent on any other attribute.
- Relations may be split into 2 or more relations

#### String data types
**CHAR**  
- Fixed length 
- Any remaining space in the field is padded with blanks 
- 1 byte per character 
- CHAR(100) means it can hold maximum 100 characters 
- E.g. 'Hat' would take up 100 bytes 

**VARCHAR** 
- Variable length 
- Holds only the characters assigned to it 
- 1 byte per character plus 1-2 bytes to hold length information 
- VARCHAR(100) means it can hold maximum 100 characters 
- E.g. ‘Hat’ would take up 5 bytes

#### SQL
SQL commands use the following syntax:
- `SELECT <attribute> FROM <table> WHERE <condition> ORDER BY <ASC/DESC>`
- `UPDATE <table> SET <attribute> = <value> WHERE <attribute> = <value>`
- `DELETE FROM <table> WHERE <condition>`
- `INSERT INTO <table> (<column1>, <column2>, ...) VALUES (<value1>, <value2>, ...)`
- `CREATE TABLE <table>(<column1> <column1type>, <column2> <column2type>, ...)`

#### Transactions
All transactions must satisfy:  
- **Atomicity** - either the whole transaction is executed or none of it.
- **Consistency** - integrity of the DB must be maintained so that the database is consistent before and after the transaction. Refers to correctness of a database.
- **Isolation** - transaction can take place concurrently without leading to inconsistencies in the database. Changes occurring in a particular transaction will not be visible to any other transaction until that particular change in that transaction is written to memory or has been committed. This property ensures that the execution of transactions concurrently will result in a state that is equivalent to a state achieved these were executed serially in some order.
- **Durability** - Changes that are committed must be persistent (permanent) and not lost even if there is a system failure.

###### Record locks
A **lock** is put on an item data as soon as a user with write-access starts using it. There are two types of lock:
- A shared lock for reading, which any number of transactions can hold at once.
- An exclusive lock for writing, which only one transaction can hold at once.

While a record is exclusive locked, other users cannot access the record. This means two users cannot concurrently update a record; users must wait until other transactions have released the record with the COMMIT command. A downside of using locks is that deadlocks can occur, where two transactions wait for each other to release records.

###### Serialisation
- DBMS will ensure that only one transaction at a time is executed on a record. It will work out which transactions need serialising and provide schedule for this. 
- A user cannot see uncommitted changes that were made by another user or changes committed after it began. 
- A transaction cannot modify data that has been modified by concurrent transaction. If this is attempted, the transaction is rolled back and restarted.

###### Timestamp ordering
- Each transaction has a timestamp when it starts.
- Each piece of data has read and write timestamp.
- Until transactions are committed, they are registered as temporary and can be rolled-back if they will cause concurrency violation. 
- Temporary changes are used to check for concurrency violations. 
- Two transactions can be started but any transaction can only be allowed to commit if the read and write timestamps for data are <= transaction timestamp.

###### Commitment ordering
- Transactions are all-or-nothing (atomic).
- If two transactions are in conflict DBMS will decide which transaction should take precedence, the other is aborted and re-started. 
- Commitment ordering is used where transactions are created on a client device then transferred to a server, such as when using mobile devices where the connection to the server may be intermittent. The client device may only be connected to the server at the start and end of the transaction.
