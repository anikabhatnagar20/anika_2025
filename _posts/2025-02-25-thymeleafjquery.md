---
layout: post
comments: True
title: Thymeleaf/Jquery hw/popcorn hacks
description: This was what i learned from the team teach and my hw 
categories: ['AP CSA']
courses: {'csa': {'week': 5}}
type: ccc
author: Anika Bhatnagar
---

## popcorn hack 1 
$("button").click(function(){ //this is a selector 

## Homework 
# question 1: 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>jQuery Dynamic Content Update</title>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>
<body>

    <input type="text" id="userInput" placeholder="Type something...">
    <button id="updateBtn">Update Text</button>
    <p id="output">This text will change.</p>

    <script>
        $(document).ready(function(){
            $("#updateBtn").click(function(){
                let inputText = $("#userInput").val(); // Get input value
                $("#output").text(inputText); // Update the <p> element with input value
            });
        });
    </script>

</body>
</html>


## Question 2 
# studentcontroller.java 
package com.example.demo.controller;

import com.example.demo.model.Student;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import java.util.Arrays;
import java.util.List;

import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class StudentController {

    @GetMapping("/students")
    public String getStudents(Model model) {
        List<Student> students = Arrays.asList(
            new Student("Alice", 85, true),
            new Student("Bob", 45, false),
            new Student("Charlie", 78, true),
            new Student("David", 50, false)
        );

        model.addAttribute("students", students);
        return "students"; // Refers to students.html in templates folder
    }
}

# student.java

package com.example.demo.model;
public class Student {
    private String name;
    private int grade;
    private boolean status;
    public Student(String name, int grade, boolean status) {
        this.name = name;
        this.grade = grade;
        this.status = status;
    }

    public String getName() {
        return name;
    }

    public int getGrade() {
        return grade;
    }

    public boolean getStatus() {
        return status;
    }
}

# student.html 
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Student List</title>
    <style>
        .passed { color: green; }
        .failed { color: red; }
    </style>
</head>
<body>
    <h2>Student List</h2>
    <table border="1">
        <tr>
            <th>Name</th>
            <th>Grade</th>
            <th>Status</th>
        </tr>
        <tr th:each="student : ${students}">
            <td th:text="${student.name}"></td>
            <td th:text="${student.grade}"></td>
            <td th:text="${student.status ? 'Passed' : 'Failed'}" 
                th:classappend="${student.status ? 'passed' : 'failed'}">
            </td>
        </tr>
    </table>

</body>
</html>


## Bonus 

Thymeleaf is better for tables because it updates automatically with data from the backend, so you don’t have to add new rows manually. It works well with Spring Boot, making it easy to pull and display information. Since it runs on the server, search engines can read the content better. The code is also much cleaner because it uses simple HTML instead of complicated JavaScript. Plus, it’s safer because it prevents hackers from adding harmful code. You can even style the table easily by changing colors or text based on conditions.







