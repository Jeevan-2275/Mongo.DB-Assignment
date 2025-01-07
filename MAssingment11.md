# Practice Assignment:
## 1. Additional Questions on CRUD Operations:
- Insert new students into the `"students"` collection with random data.
```bash
db.students.insertOne(
  { 
    "name": "Jeevan",
    "rollNumber": 101,
    "department": "Computer Science",
    "year": 2,
    "coursesEnrolled": ["CS101", "CS102"]
  });
```

- Update the department of a student based on their roll number.
```bash
db.students.updateOne({ name: "Jeevan" }, { $set: { department: "CS" } });
```



- Remove all students who have enrolled in less than 3 courses.
