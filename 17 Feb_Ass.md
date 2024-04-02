# Qus 1
MongoDB is an open source NoSQL database management program . NoSQL(not only SQL) is used as an alternative to traditional relational database.NoSQL databases are quite useful for working with large sets of distributed data. MongoDB is a tool that can manage document-orientd information,store or retrieve information.

A non-relational database is a database that does not use the tabular schema of rows and columns found in most traditional database systems.

MySQL is a mature relational database system, offering a familiar database environment for experienced IT professionals.
MongoDB is a well-established, non-relational database system offering improved flexibility and horizontal scalability, but at the cost of some safety features of relational databases, such as refrential integrity.
# Qus 2
* Schema-less Database: It is the great feature provided by the MongoDB.A schema-less database means onr=e collection can hold different types of documents in it.

* Document Oriented: In MongoDB, Aall the data stored in the documents instead of table like in RDBMS.

* Indexing:In MongoDB database, every field in the documents is indexed with primary and secondary indices this makes easier and takes less time to get or search data from the poll of the data.

* Scalability:MongoDB provides horizontal scalability with the help of sharding.

* Replication:MongoDB provides high availability and redundancy with the help of replication , it creates multiple copies of the data and sends these copies to a different server so that if one server fails, then the data is retrived from another server.

# Qus 3


```python
import pymongo
client=pymongo.MongoClient("mongodb+srv://syedzaid0911:syedzaid0911@cluster0.28po1ro.mongodb.net/?retryWrites=true&w=majority&appName=Cluster0")
db=client.test
db
```




    Database(MongoClient(host=['ac-5d3ubrg-shard-00-01.28po1ro.mongodb.net:27017', 'ac-5d3ubrg-shard-00-02.28po1ro.mongodb.net:27017', 'ac-5d3ubrg-shard-00-00.28po1ro.mongodb.net:27017'], document_class=dict, tz_aware=False, connect=True, retrywrites=True, w='majority', appname='Cluster0', authsource='admin', replicaset='atlas-3au6f1-shard-0', tls=True), 'test')




```python
pip install pymongo

```

    Collecting pymongo
      Downloading pymongo-4.6.3-cp310-cp310-manylinux_2_17_x86_64.manylinux2014_x86_64.whl (676 kB)
    [2K     [90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━[0m [32m676.9/676.9 kB[0m [31m44.3 MB/s[0m eta [36m0:00:00[0m
    [?25hCollecting dnspython<3.0.0,>=1.16.0
      Downloading dnspython-2.6.1-py3-none-any.whl (307 kB)
    [2K     [90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━[0m [32m307.7/307.7 kB[0m [31m34.0 MB/s[0m eta [36m0:00:00[0m
    [?25hInstalling collected packages: dnspython, pymongo
    Successfully installed dnspython-2.6.1 pymongo-4.6.3
    Note: you may need to restart the kernel to use updated packages.


# Qus 4


```python
db=client["pwskills"]
```


```python
dt={"name":"syed",
      "class":"data science",
      "time":"flexi"}
```


```python
coll_pwskills=db["zaid"]
```
coll_pwskills.insert_one(dt)

```python
record_one = {"name": "John", "age": 30, "city": "New York"}
result_one = coll_pwskills.insert_one(record_one)
print("One record inserted with ID:", result_one.inserted_id)

```


```python
records_many = [
    {"name": "Alice", "age": 25, "city": "Los Angeles"},
    {"name": "Bob", "age": 35, "city": "Chicago"},
    {"name": "Eve", "age": 28, "city": "San Francisco"}
]
result_many = mycollection.insert_many(records_many)
print("Many records inserted with IDs:", result_many.inserted_ids)

```


```python
print("\nInserted records:")
for record in mycollection.find():
    print(record)

    
print("\nOne inserted record:")
print(mycollection.find_one({"name": "John"}))
```

# Qus 5
The find() method in MongoDB is used to query documents from a collection based on certain criteria. It returns a cursor which can be iterated to retrieve documents matching the query.


Basic Query: You can use the find() method without any parameters to retrieve all documents in a collection.
for document in mycollection.find():
    print(document)
    



```python
# code
for document in mycollection.find({"age": {"$gt": 30}}):
    print(document)
```

# Qus 6
The sort() method specifies the order in which the query returns the matching documents from the given collection. You must apply this method to the cursor before retrieving any documents from the database. It takes a document as a parameter that contains a field: value pair that defines the sort order of the result set. The value is 1 or -1 specifying an ascending or descending sort respectively.

syntax:
db.Collection_Name.sort({field_name:1 or -1})

Example:
* cursor.sort({field1: order, field2: order, ...})
* cursor.sort({ field: 1 })

* cursor.sort({field: -1})

* cursor.sort({field1: 1, field2: -1});


# Qus 7
* delete_one():
    This method is used to delete a single document that matches the specified filter criteria.
It deletes the first document that matches the filter criteria and then stops.

If multiple documents match the filter criteria, only the first one encountered will be deleted.

Syntax:
collection.delete_one(filter)


* delete_many():
This method is used to delete multiple documents that match the specified filter criteria.
It deletes all documents that match the filter criteria.
It is useful when you want to remove multiple documents from a collection.
collection.delete_many(filter)

* drop():
This method is used to drop an entire collection from the database.

It removes all documents from the collection and also deletes the collection itself.
It is useful when you want to completely remove a collection, including all its documents.
collection.drop()


```python

```
