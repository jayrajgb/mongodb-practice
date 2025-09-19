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


// projection - only true columns are returned

school> db.students.find({}, {_id: 0, name: 1, date: 1})

// can use true / false instead
// cannot use 0, 1 together, _id is exception

// find that not equals to
school> db.students.find({ name: {$ne: "Jay"} })

// find that is lt, lte, gt, gte
school> db.students.find({ rollno: {$lt: 10} })
school> db.students.find({ rollno: {$gte: 5, $lte: 10} })

// find using in or nin operator, within a array of range
school> db.students.find({ name: {$in: ["Jay", "Raj"] } })
school> db.students.find({ name: {$nin: ["Ansh", "Dev"] } })

```

---

##### **DATATYPES**

```
school> db.students.insertOne({

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

##### **UPDATE COMMAND**

```
school> db.students.updateOne(
        { name: "Ansh" },
        { $set: { rollno: 14 } } )

school> db.students.updateOne(
        { name: "Ansh" },
        { $unset: { passout: true } } )
```

---

##### **UPSERT COMMAND**

```
school> db.students.updateOne(
        { name: "Shiv" },
        { $set: { name: "Shiv", rollno: 13 } },
        { upsert: true } )
```

---

##### **UPDATE MANY COMMAND**

```
school> db.students.updateMany({}, { $inc: { rollno: 1 } })

school> db.students.updateMany({}, { $inc: { rollno: -1 } })

school> db.students.updateMany({}, { $set: { passout: false } })

school> db.students.updateMany(
        { passout: { $exists: false } },
        { $set: { passout: true } } )
```

---

##### **DELETE COMMAND**

```
// delete one document

school> db.students.deleteOne({ rollno: 0 })


// delete many documents

school> db.students.deleteMany({ age: 18 })

school> db.students.deleteMany({ passout: { $exists: false } })
```

---

##### **SORT COMMAND**

```
school> db.students.find().sort({ rollno: 1 })          // 1 for asc, -1 for desc
```

---

##### **LIMIT COMMAND**

```
school> school> db.students.find().limit(2)
```

---
