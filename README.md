##### **SHOW DBS**

```
test> show dbs
```

---

##### **USE DB**

```
test> use school
```

---

##### **CREATE COMMAND**

```
school> db.createCollection("students")
```

---

##### **DROP COMMAND**

```
school> db.dropDatabase()
```

---

##### **INSERT COMMAND**

```
// insert one document

school> db.students.insertOne({ name: "Jay" , rollno: 11 })

// insert many documents

school> db.students.insertMany([{ name: "Dev" , rollno: 10 } , { name: "Raj" , rollno: 12 } , { name: "Ansh" , rollno: 13 }])
```

---

##### **FIND COMMAND**

```
// all documents are returned

school> db.students.find()

// first documents is returned

school> db.students.findOne()

// queried document is returned

school> db.students.find( { rollno: 11 } )

school> db.students.findOne( { rollno: 11 } )
```

---

##### **DATATYPES**

```
school> db.data.insertOne({
  name: "Sam",                      // String
  age: 17,                          // Int
  gpa: 8.5,                         // Double
  active: true,                     // Boolean
  hobbies: ["cricket","music"],     // Array
  address: { city:"Delhi" },        // Object
  phone: null,                      // Null
  joined: new Date(),               // Date
  marks: NumberDecimal("88.75"),    // Decimal128
  ts: Timestamp(),                  // Timestamp
  file: BinData(0,"ABC"),           // Binary
  custom_id: ObjectId()             // ObjectId
})

```

---
