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
```bash
db.students.deleteMany({ coursesEnrolled: { $size: 2 } });
```



## 2. Aggregation Exercise:
### Use aggregation to find the department with the most number of students.
```bash
db.students.aggregate([
  { $group: { _id: "$department", studentCount: { $sum: 1 } } },
  { $sort: { studentCount: -1 } },
  { $limit: 1 }
]);
```

## 3. Advanced Querying Exercise:

### Query students who have enrolled in a specific set of courses (e.g., CS101 and MATH101).
```bash
db.students.aggregate([
  { 
    $match: {
      coursesEnrolled: { $all: ["CS101", "MATH202"] }
    }
  },
  {
    $project: {
      _id: 1,
      name: 1,
      coursesEnrolled: 3
    }
  }
]);
```


## 4. Indexing and Performance:

### Experiment with creating indexes on various fields like department, year, etc., and measure the query performance using explain().
 - Create an index on `"department"`:
   ```bash
    db.students.find({ department: "CSE" }).explain("executionStats");
   ```

-  Drop a specific index:

    ```bash
   db.students.dropIndex("department_1");
   ```


