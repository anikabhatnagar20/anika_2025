---
layout: post
comments: True
title: Final blog
description: Final
categories: ['AP CSA']
courses: {'csa': {'week': 5}}
type: ccc
menu: nav/CSA_Units/csa_unit3_p1.html
author: Anika Bhatnagar
---

Preperation Checklist 
- [x] Reviewed all 10 units
- [x] Created a full-topic flowchart
- [x] Practiced FRQs (all 4 types)
- [ ] Timed FRQ practice
- [x] College Board MCQs
- [ ] Used AP Classroom progress checks
- [x] Read scoring guidelines + samples
- [ ] Review over formula sheet given 
Collegeboard MCQs: <img width="1236" alt="Image" src="https://github.com/user-attachments/assets/086c76b9-5ebb-4bca-a31c-d4bdababca54" />
Full topic flowchart: 
<img width="357" alt="Image" src="https://github.com/user-attachments/assets/754f8060-c4ae-4be1-94f3-9a5bd65c3fe5" />
Topics to review:
- [ ]  Creating and Storing Objects (Instantiation)
- [ ] Static Variables and Methods
- [ ]  Scope and Access
- [ ] Polymorphism
- [ ] Compound Boolean Expressions
- [ ] Equivalent Boolean Expressions

| Date       | Focus Area                                      | Task                                                                 |
|------------|--------------------------------------------------|----------------------------------------------------------------------|
| Apr 15 (Mon) | Variables, Types & Arithmetic                  | Practice type declarations, integer division, casting                |
| Apr 16 (Tue) | String & Math Class Methods                    | Use `substring`, `indexOf`, `Math.random`, etc. in short programs    |
| Apr 17 (Wed) | Conditionals & Logic Tracing                   | Trace `if`, `else if`, `else`, and compound conditions               |
| Apr 18 (Thu) | Loop Construction & Fixing Loop Errors         | Create `for` and `while` loops, fix off-by-one and infinite loops    |
| Apr 19 (Fri) | Writing Constructors & Using `this`            | Create constructors, initialize objects, use `this.variable`         |
| Apr 20 (Sat) | Method Writing & Returns                       | Write methods with parameters, return types, and proper headers      |
| Apr 21 (Sun) | FRQ Practice: Methods & Control                | Complete a full FRQ and review scoring guidelines                    |
| Apr 22 (Mon) | 1D Array Traversal & Logic                     | Max/min/sum/count with loops, index safety                          |
| Apr 23 (Tue) | ArrayList Access & Modifications               | Practice `.add()`, `.remove()`, `.get()`, `.set()` with loops        |
| Apr 24 (Wed) | Nested Loops & 2D Array Patterns               | Trace row/column logic in nested loops                               |
| Apr 25 (Thu) | 2D Array FRQ Practice                          | Complete a 2D array FRQ with row/column conditions                   |
| Apr 26 (Fri) | Class Design: Fields, Accessors, `toString()`  | Write a full class with private fields, methods, and formatting      |
| Apr 27 (Sat) | Inheritance & Overriding Methods               | Create subclass, override method, explain `super()` usage            |
| Apr 28 (Sun) | Recursion Tracing & Base Case Logic            | Practice tracing and writing recursive methods                       |
| Apr 29 (Mon) | FRQ Practice: Any Type (random pick)           | Timed FRQ (randomly chosen), self-grade with rubric                  |
| Apr 30 (Tue) | Mixed MC Practice & Bug Fixing                 | Do 20+ MCQs + debug 3 broken code snippets                           |
| May 1 (Wed)  | Review Java Quick Reference + Vocabulary       | Highlight key methods, reserved words, and syntax                    |
| May 2 (Thu) | Mock Exam Practice                              | Full 90-minute simulation (MC + FRQ blend)                           |
| May 3 (Fri) | Analyze Missed Questions + Review Notes         | Go over mistakes from mock + review weak areas                       |
| May 4 (Sat) | Light Review: Class, Arrays, Logic              | Skim notes + reinforce method, class, and array flow                 |
| May 5 (Sun) | Rapid Recall: Flashcards + Scoring Rubrics      | Use flashcards + skim sample student FRQs + scoring                  |
| **May 6 (Mon)** |  **AP CSA Exam Day**                         |               |


FRQ practice: 
[FRQ 2024](https://apcentral.collegeboard.org/media/pdf/ap24-frq-comp-sci-a.pdf)

## Question 1 Feeder Simulation
     public class Feeder {
    private int currentFood;

    public Feeder(int food) {
        currentFood = food;
    }

    // Part (a)
    public void simulateOneDay(int numBirds) {
        double chance = Math.random();
        if (chance < 0.05) {
            currentFood = 0;
        } else {
            int foodPerBird = (int) (Math.random() * 41) + 10;
            int totalFood = foodPerBird * numBirds;
            if (totalFood >= currentFood) {
                currentFood = 0;
            } else {
                currentFood -= totalFood;
            }
        }
    }

    // Part (b)
    public int simulateManyDays(int numBirds, int numDays) {
        int count = 0;
        for (int i = 0; i < numDays; i++) {
            if (currentFood == 0) break;
            simulateOneDay(numBirds);
            count++;
        }
        return count;
    }
} 

## Question 2 Scoreboard 
    public class Scoreboard {
    private String team1Name;
    private String team2Name;
    private int team1Score;
    private int team2Score;
    private boolean isTeam1Active;

    public Scoreboard(String name1, String name2) {
        team1Name = name1;
        team2Name = name2;
        team1Score = 0;
        team2Score = 0;
        isTeam1Active = true;
    }

    public void recordPlay(int points) {
        if (points > 0) {
            if (isTeam1Active) {
                team1Score += points;
            } else {
                team2Score += points;
            }
        } else {
            isTeam1Active = !isTeam1Active;
        }
    }

    public String getScore() {
        return team1Score + "-" + team2Score + "-" + (isTeam1Active ? team1Name : team2Name);
    }
} 

## Question 3 Wordchecker 
``` import java.util.ArrayList;

public class WordChecker {
    private ArrayList<String> wordList;

    public WordChecker(ArrayList<String> words) {
        wordList = words;
    }

    // Part (a)
    public boolean isWordChain() {
        for (int i = 1; i < wordList.size(); i++) {
            if (!wordList.get(i).contains(wordList.get(i - 1))) {
                return false;
            }
        }
        return true;
    }

    // Part (b)
    public ArrayList<String> createList(String target) {
        ArrayList<String> result = new ArrayList<>();
        for (String word : wordList) {
            if (word.startsWith(target)) {
                result.add(word.substring(target.length()));
            }
        }
        return result;
    }
}

## Question 4 GridPath and Location
    public class Location {
    private int theRow;
    private int theCol;

    public Location(int r, int c) {
        theRow = r;
        theCol = c;
    }

    public int getRow() { return theRow; }
    public int getCol() { return theCol; }
}
public class GridPath {
    private int[][] grid;

    public GridPath(int[][] g) {
        grid = g;
    }

    // Part (a)
    public Location getNextLoc(int row, int col) {
        boolean hasRight = col + 1 < grid[0].length;
        boolean hasDown = row + 1 < grid.length;

        if (hasRight && hasDown) {
            if (grid[row + 1][col] < grid[row][col + 1]) {
                return new Location(row + 1, col);
            } else {
                return new Location(row, col + 1);
            }
        } else if (hasRight) {
            return new Location(row, col + 1);
        } else {
            return new Location(row + 1, col);
        }
    }

    // Part (b)
    public int sumPath(int row, int col) {
        int sum = grid[row][col];
        while (row != grid.length - 1 || col != grid[0].length - 1) {
            Location next = getNextLoc(row, col);
            row = next.getRow();
            col = next.getCol();
            sum += grid[row][col];
        }
        return sum;
    }
}
