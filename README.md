###### **SHOW DBS**

```
test> show dbs    // to show databases
```

---

###### **USE DB**

```
test> use school    // creates schooldb
```

---

###### **CREATE COMMAND**

```
school> db.createCollection("students")    // creates collection named students
```

---

###### **DROP COMMAND**

```
school> db.dropDatabase()    // removes schooldb
```

---

###### **INSERT COMMAND**

```
// insert one document
school> db.students.insertOne({ name: "Jay" , rollno: 11 })

// insert many documents
school> db.students.insertMany([{ name: "Dev" , rollno: 10 } , { name: "Raj" , rollno: 12 } , { name: "Ansh" , rollno: 13 }])
```

---

###### **VIEW ALL DOCS COMMAND**

```
school> db.students.find()
```

---

###### **DATATYPES**

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
