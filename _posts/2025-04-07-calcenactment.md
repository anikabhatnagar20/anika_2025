---
layout: post
comments: True
title: 2d array hw 
description: I put the hw into a post file because for some reason when it was an nb it was not showing up on gh pages. 
categories: ['AP CSA']
courses: {'csa': {'week': 5}}
type: ccc
author: Anika

// Complete Java implementation of both CalculatorQueue and CalculatorStack with all features

import java.util.*;

public class Calculator {

    // --- Queue-Based Calculator ---
    public static double processQueue(Queue<String> queue) {
        if (queue.size() < 3) return 0.0;

        double result = 0.0;
        try {
            result = Double.parseDouble(queue.poll());
            while (!queue.isEmpty()) {
                String operator = queue.poll();
                String next = queue.poll();

                if (operator == null || next == null || !operator.matches("[+\-*/]")) {
                    System.out.println("Invalid operation: " + operator);
                    break;
                }

                double operand = Double.parseDouble(next);

                switch (operator) {
                    case "+": result += operand; break;
                    case "-": result -= operand; break;
                    case "*": result *= operand; break;
                    case "/": result /= operand; break;
                }
                System.out.println("Intermediate result: " + result);
            }
        } catch (Exception e) {
            System.out.println("Error processing queue: " + e.getMessage());
        }
        return result;
    }

    public static void displayQueueOperations(Queue<String> queue) {
        System.out.println("Queue Operations:");
        for (String op : queue) System.out.print(op + " ");
        System.out.println("\n");
    }


    // --- Stack-Based Calculator ---
    public static double processStack(Stack<String> stack) {
        Stack<Double> values = new Stack<>();
        while (!stack.isEmpty()) {
            String token = stack.pop();
            try {
                if (token.matches("-?\\d+(\\.\\d+)?")) {
                    values.push(Double.parseDouble(token));
                } else if (token.matches("[+\-*/]")) {
                    if (values.size() < 2) continue;
                    double a = values.pop();
                    double b = values.pop();
                    double res = 0.0;
                    switch (token) {
                        case "+": res = a + b; break;
                        case "-": res = a - b; break;
                        case "*": res = a * b; break;
                        case "/": res = a / b; break;
                    }
                    values.push(res);
                    System.out.println("Intermediate result: " + res);
                } else {
                    System.out.println("Invalid token: " + token);
                }
            } catch (Exception e) {
                System.out.println("Stack error: " + e.getMessage());
            }
        }
        return values.isEmpty() ? 0.0 : values.pop();
    }

    public static void displayStackOperations(Stack<String> stack) {
        System.out.println("Stack Operations (top to bottom):");
        for (int i = stack.size() - 1; i >= 0; i--) System.out.print(stack.get(i) + " ");
        System.out.println("\n");
    }


    // --- Postfix Calculator ---
    public static double calculatePostfixExpressionArray(String[] postfix) {
        Stack<Double> doubleStack = new Stack<>();
        for (String j : postfix) {
            if (j.matches("-?\\d+(\\.\\d+)?")) {
                doubleStack.push(Double.valueOf(j));
            } else {
                if (doubleStack.size() < 2) continue;
                double a = doubleStack.pop();
                double b = doubleStack.pop();
                switch (j) {
                    case "^": doubleStack.push(Math.pow(b, a)); break;
                    case "*": doubleStack.push(b * a); break;
                    case "/": doubleStack.push(b / a); break;
                    case "+": doubleStack.push(b + a); break;
                    case "-": doubleStack.push(b - a); break;
                    default:
                        System.out.println("Invalid operator: " + j);
                        doubleStack.push(b);
                        doubleStack.push(a);
                }
            }
        }
        return doubleStack.peek();
    }


    // --- Main for testing ---
    public static void main(String[] args) {

        // Queue Test
        Queue<String> queue = new LinkedList<>(List.of("10", "/", "2", "*", "5", "+", "3"));
        displayQueueOperations(queue);
        double queueResult = processQueue(new LinkedList<>(queue));
        System.out.println("Final Queue Result: " + queueResult + "\n");

        // Stack Test
        Stack<String> stack = new Stack<>();
        stack.addAll(List.of("3", "5", "+", "2", "*", "10", "/"));
        displayStackOperations(stack);
        double stackResult = processStack((Stack<String>) stack.clone());
        System.out.println("Final Stack Result: " + stackResult + "\n");

        // Postfix Test
        String[] postfix = {"10", "2", "/"};
        double postfixResult = calculatePostfixExpressionArray(postfix);
        System.out.println("Postfix Result: " + postfixResult);
    }
}
