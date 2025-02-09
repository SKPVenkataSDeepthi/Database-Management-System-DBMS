# 1. Inserting Documents
* To insert data into MongoDB, you need to connect to the database using the MongoClient from the mongodb package.
* The insertOne() method is used to insert a single document, while insertMany() is used to add multiple documents at once.
* The insertOne() function returns an object containing the insertedId, which is the unique identifier of the inserted document.
* The insertMany() function returns an array of inserted document IDs.
* The finally block ensures the database connection is closed after the operation.


const { MongoClient } = require('mongodb');
const uri = 'mongodb://localhost:27017/my_database';
const client = new MongoClient(uri, { useNewUrlParser: true, useUnifiedTopology: true });
async function insertDocuments() {
    try {
        await client.connect(); // Establish connection
        const database = client.db('my_database');
        const collection = database.collection('my_collection');
        // Insert a single document
        const result = await collection.insertOne({ name: 'John Doe', age: 30 });
        console.log('Inserted document:', result.insertedId);
        // Insert multiple documents
        const documents = [{ name: 'Alice', age: 25 }, { name: 'Bob', age: 35 }];
        const resultMany = await collection.insertMany(documents);
        console.log('Inserted documents:', resultMany.insertedIds);
    } catch (error) {
        console.error('Error inserting documents:', error);
    } finally {
        await client.close();
    }
}
insertDocuments();

### Example: 
Imagine you are writing down names and ages in your notebook. You can add one person's details at a time or add multiple people at once.
* Adding one person:
> "John Doe, 30 years old" is written on a page.
* Adding multiple people:
> You write "Alice, 25 years old" and "Bob, 35 years old" on separate pages.

# 2. Finding Documents
* The find() method is used to search for documents that match a given query.
* The query { age: { $gt: 30 } } retrieves documents where the age field is greater than 30.
* The result is stored in a cursor object, which allows iteration through multiple documents.
* forEach() is used to print each document found in the database.
* The finally block ensures the database connection is closed after retrieving data.

async function findDocuments() {
    try {
        await client.connect(); // Establish connection
        const database = client.db('my_database');
        const collection = database.collection('my_collection');
        // Query for documents where age is greater than 30
        const query = { age: { $gt: 30 } };
        const cursor = collection.find(query);
        await cursor.forEach(document => {
            console.log('Found document:', document);
        });
    } catch (error) {
        console.error('Error finding documents:', error);
    } finally {
        await client.close();
    }
}
findDocuments();

### Example:
Imagine you want to find people older than 30 in your notebook. Instead of flipping through every page, MongoDB helps you find the right pages instantly.
>  "Find everyone older than 30."

MongoDB's Answer: It flips through the notebook and says, "I found Bob, he is 35!"
