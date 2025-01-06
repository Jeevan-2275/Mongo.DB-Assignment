# Assignment NO. 9
## Task 1: Create a "CodingGita Students" database


// Create a new MongoDB database called CodingGita. Add two collections:

// students: Name, roll number, department, year, courses enrolled.
// courses: Course code, name, credits, instructor.

db.students.insertOne({
  name: "Jack",
  rollNumber: "12345",
  department: "CSE",
  year: 3,
  coursesEnrolled: ["Data Structures", "Algorithms", "DBMS"],
  age: 22,
  registrationDate: new Date()
}); 




// courses: Course code, name, credits, instructor.
db.courses.insertOne(
    { 
      "courseCode": "CS101", 
      "courseName": "Introduction to Programming", 
      "credits": 3, 
      "instructor": "Prof. Sharma" ,
    registrationDate: new Date()
    });




//     Task 2: Perform CRUD operations

// Add a few more students and courses to the database.
// Query data based on:
// Department (e.g., "Computer Science").
// Year (e.g., "2").
// Courses enrolled (e.g., "CS101").


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
    }
  ]);
  

// Update the courses for a specific student (e.g., adding a new course).
db.students.updateOne({ "name": "Kiran"},{$push: {"coursesEnrolled": "CS102"}});

// Delete a student or course from the database.
db.students.deleteOne({ "name": "Jeevan" });
