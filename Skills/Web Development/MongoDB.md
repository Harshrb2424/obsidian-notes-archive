- 26 - MongoDB
    - 003 MongoDB [CRUD](https://www.mongodb.com/docs/manual/crud/) Operations in the Shell_ Create **insertOne()**
        - `mongod` to start server
        - `mongo` to interact with mongoDB (in new terminal)
            - > `help` to see amm commands
                
            - `show dbs` show data bases
            - `use nameDB` create (or) create and use the nameDB
            - `db` show the data base you are in.
            - `db.collectname.insertOne({_id: 1, name: “pen”, price: 20})`
                - `insertOne` to add JSON file
            - or `db.collection.insertMany()`
    - 004 MongoDB [CRUD](https://www.mongodb.com/docs/manual/crud/) Operations in the Shell_ Reading & Queries **find()**
        - `db.collection.find(query, projection)`
        - `db.collection.find({"name": "Pen"},{name: 1, id: 0, price: 1})` find all
            - `projection` has `name: 1` -> to show and `id: 0` → hide
    - 005 MongoDB [CRUD](https://www.mongodb.com/docs/manual/crud/) Operations in the Shell_ Update **updateOne()**
        - `[**db.collection.updateOne({id: 1}, {stock: 32})**](<https://www.mongodb.com/docs/manual/reference/method/db.collection.updateOne/#mongodb-method-db.collection.updateOne>)`
        - `db.collection.updateMany(filter, action)`
        - `db.collection.replaceOne()`
    - 006 MongoDB [CRUD](https://www.mongodb.com/docs/manual/crud/) Operations in the Shell_ Delete `deleteOne()`
        - `db.collection.deleteOne(delete filter)`
        - `db.collection.deleteMany()`
    - 007 Relationships in MongoDB [{data1}, {data2}]
        - add a document with other document with [{data1}, {data2}]
    - 008 Working with The Native MongoDB Driver
        - you can use mongoDB with Node.js with
            - native driver (hard)
            - mongoose (simple)
        - [https://www.mongodb.com/docs/drivers/node/current/quick-start/](https://www.mongodb.com/docs/drivers/node/current/quick-start/)
        - [https://www.mongodb.com/docs/drivers/node/current/](https://www.mongodb.com/docs/drivers/node/current/)
- 27 - Mongoose
    - **Mongoose Shell** commands
        
        - show dbs - shows Databases
        - use itemsDB - uses itemsDB
        - db.dropDatabase() - deletes the used (itemsDB) database
        - show collections - shows collections
        - db.items.find() - finds all the data in items collection
        - db.items.drop() - deletes the items collection
    - 001 Introduction to Mongoose **mongoose.connect**
        
        - Connect to a database with `mongoose.connect(”url”)`
        
        ```
        mongoose.connect("mongodb://localhost:27017/todolistDB");
        ```
        
        - Create a collection with `mongoose.model(”item”, itemsSchema)` _use singular form._
            
            ```
            const Item = mongoose.model("Item", itemsSchema);
            ```
            
            - Schema is a skeleton for how to store the data. Create by `mongoose.Schema({})`
            
            ```
            const itemsSchema = new mongoose.Schema({
              name: String,
            });
            ```
            
        - Creating a item
            
        
        ```
        const item1 = new Item({
          name: "Testing Item 1",
        });
        ```
        
        - to save `item1.save()` or for many
        
        ```
        Item.insertMany([item1, item2, item3], function (error) {
                if (error) {
                  console.log("error: " + error);
                } else {
                  console.log("Working Broo 3 Items added ");
                }
        ```
        
    - 002 Reading from Your Database with Mongoose **Item.find**
        
        - Find data with
        
        ```
        Item.find({}, function (error, foundItems) { 
        console.log(foundItems)
        // use the items found with foundItems
         });
        ```
        
        - as the `foundItems` are in Js Object (JSON) you can use the data with `.` , `[ i ]` , `foundItems.forEach(Function(item) { console.log(item); })`
        - To end the connection at the End
        
        ```
        mongoose.connection.close();
        ```
        
    - 003 Data Validation with Mongoose **JSON**
        
        - For proper Data Validation you can add replace `name: String,` with
        
        ```
        name: {
            type: String,
            required: [true, "No Item Bro"]
          },
        ```
        
        - For more info [https://mongoosejs.com/docs/validation.html](https://mongoosejs.com/docs/validation.html)
    - 004 Updating and Deleting Data Using Mongoose **Fruit.updateOne Fruit.deleteOne**
        
        - All commands - [https://mongoosejs.com/docs/api/model.html](https://mongoosejs.com/docs/api/model.html)
        - Update with `Item.updateOne()`
        
        ```
        // Item.updateOne({filter},{update Info}, call back function)
        Fruit.updateOne(
          { _id: "6326ed3f3e320f42aa1678db" },
          { name: "Lol" },
          function (err) {
            if (err) {
              console.log("error: " + err);
            } else {
              console.log("res: Updated Working Bro ");
            }
            mongoose.connection.close();
          }
        );
        ```
        
        - Delete with `Item.deleteOne()`
        
        ```
        // Item.deleteOne({filter *what to delete*}, call back function)
        Fruit.deleteOne({ _id: "6326eb0b0910b6eb3fe0427a" }, function (err) {
          if (err) {
            console.log("error: " + err);
          } else {
            console.log("res: Deleted Working Bro ");
          }
          mongoose.connection.close();
        });
        ```
        
    - 005 Establishing Relationships and Embedding Documents using Mongoose **mongoose.Schema**
        
        - connect other collections buy using `[itemsSchema]` as one of its data type.
        
        ```
        const listsSchema = new mongoose.Schema({
          name: String,
          items: [itemsSchema],
        });
        ```
