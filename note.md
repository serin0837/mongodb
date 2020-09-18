# net Ninja

- 1. introduction
  - No SQL (no relation)
  - SQL-Postgress?(relation)
  - MERN stack (MongoDB, Express, React, Node)
  - client - mongoose(server node) - mongodb
- 2. install

  - I download mongoDb locally and "C:\Program Files\MongoDB\Server\4.4\bin\mongo.exe"- run mongodb
  - clone ninja repo
  - install mongoose

- 4. model and schema

  - model represents a collection in the database
  - schema represents the structure of the individual records in that collection

- 5. mocha is testing framework
- ```js
  describe("some demo tests", function () {
    //create test
    it("adds two numbers together", function () {
      assert(2 + 3 === 5);
    }); // assert evaluate true or false->pass the test//false fail test
  });
  ```

  - we want to test our connection with the database
    - creating records
    - reading records
    - updating records
    - deleting records
    - npm install mocha
  - npm run test -> change package.json test script to mocha

- 6. saving data in mongoose

- 7. ES6 promises / mongoose does not want us to use mongoose default
  - mocha hook// we want the connection is fully made before the test starts!!
  - connect to the db before tests run
  - in connection.js add before function and put original connect function inside of before function
  - this connect also asyn so mongoose don't know when completed so we want to add done parameter in here too
- 8. Robomongo: visual representation

  - allow to see all the data in mongo db
  - download robomongo -> i can create new connection-> connect -> I can see what i save with code!!!!
  - mariochar plural now in robomongo mariochars and got 4 objects// we run a lot of npm run test so they keep make object with unique id

- 9. drop collection(delete collection )

  - mocha hook : we want you to do all the time
  - add mocha hook in connection.js and i can check in robomongo that there is only one mariochar

- 10. finding records
- demonstrate findOne()method

- find( criteria) - multiple result
- findOne (criteria) -first one
- difference save() and find()

  - save() method was on a single instance
    ex) myChar = new MarioChar({name:"Mario"})
    myChar.save()

  - find() methods are on the models
    ex)marioChar.find({name:"Mario"})

- 11. Object ID
- 12. Deleting Records

  - demonstrate findOneAndRemove()
    - create and save a new record to the db
    - use findOneAndRemove() to remove the record
    - Try to findOne in the db
    - assert that the result is null
  - Focus on 3 Mongooses methods:
    char.remove()
    MarioChar.remove()
    MarioChar.findOneAndRemove()

- 13. Updating Records
  - Various Mongoose methods
    - char.update()
    - MarioChar.update()
    - MarioChar.findOneAndUpdate()
  - Demonstrate
    - create and save a new record to the db
    - use findOneAndUpdate() the name of the record
    - Try to findOne in the db
    - assert that the result has the updated property value
- 14. Update Operators

  - what is this? something that can help us update our fields in certain ways
  - ex)increment update operators....
  - \$inc
  - https://docs.mongodb.com/manual/reference/operator/update/

- 15. Relational Data
      <new model>

  - authors : name, age,books
  - books :title, number of pages, genre
  - ex)
    author id
    - name
    - age
    - books(array)
      - title..
  - object format
    {
    Name:"patrick",
    age:38,
    books:[
    {title:"name of the wind",pages:400},
    {title:"wise man's fear,pages:500}
    ]
    }
  - create author.js

- 16. Nesting Sub-documents

## check mongodb-playlist repo
