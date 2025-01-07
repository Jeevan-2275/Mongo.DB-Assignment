# Task 1: Add multiple students
## Insert at least 5 students into the students collection with unique roll numbers, names, departments, years, and subjects enrolled.

```bash
db.students.insertMany([
  { 
    "name": "Jeevan",
    "rollNumber": 101,
    "department": "Computer Science",
    "year": 2,
    "coursesEnrolled": ["CS101", "CS102"]
  },
  { 
    "name": "Rohit",
    "rollNumber": 102,
    "department": "Computer Science",
    "year": 2,
    "coursesEnrolled": ["CS101", "CS103"]
  },
  { 
    "name": "Kiran",
    "rollNumber": 103,
    "department": "Electrical Engineering",
    "year": 3,
    "coursesEnrolled": ["EE101", "EE102"]
  },
  { 
    "name": "Jack",
    "rollNumber": 104,
    "department": "Electrical Engineering",
    "year": 3,
    "coursesEnrolled": ["EE101", "EE102"]
  },
  { 
    "name": "Paul",
    "rollNumber": 105,
    "department": "Electrical Engineering",
    "year": 3,
    "coursesEnrolled": ["EE101", "EE102"]
  }
]);
```

 ## Task 2: Add multiple subjects
 ### Insert 4 subjects into the subjects collection, each with 3 to 5 topics.
 ```bash
  db.subjects.insertMany([
  {"subjectName": "React",
"topics" : ["Components" , "React Hooks", "Routing with React Router","State Management","React Lifecycle Methods" ]
  },
 {"subjectName": "Node.js",
"topics" : [ "Modules", 
      "Express", 
      "File System", 
      "Asynchronous Programming" ]
  },

{  "subjectName": "MongoDB", 
    "topics": [
      "Database Design", 
      "CRUD Operations", 
      "Aggregation", 
      "Indexes"
    ]
  },{ 
    "subjectName": "React",
    "topics": [
      "JSX", 
      "Components", 
      "State", 
      "Props", 
      "Hooks"
    ]
  }
]);
  ```

## Task 3: Query students based on subject enrollment.
### Query the students collection to find all students who are enrolled in NodeJS.

```bash
db.students.find({ "subjectsEnrolled": "React" });
```
## Task 4: Add a new topic to a subject.
### Add a new topic to the NodeJS subject.
```bash
db.subjects.updateOne(
  { "subjectName": "Node.js" },
  { $push: { "topics": "Rest API" } }
);
```
## Task 5: Query subjects with multiple topics
 ### Query the subjects collection to find subjects that contain at least 4 topics.
 ```bash
 db.subjects.find({ "topics": {$size:4} });
 ```
 ## Task 6: Update student enrollment
### Add the subject "React Native" to Jenil's subjects.


```bash
db.students.updateOne(
  { name: "Nagesh" }, 
  { $set: { subjectsEnrolled: ["IoT", "JavaScript"," C", "React", "APIs", "React Native"] } }
);
```
## Task 7: Query all students
### Query all studets in the database and print out their names and enrolled subjects.
```bash


```