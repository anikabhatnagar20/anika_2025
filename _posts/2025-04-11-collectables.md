## Lists popcorn hack 

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class PopcornHack {
    public static void main(String[] args) {
        // Create an ArrayList of at least 10 integers
        List<Integer> numbers = new ArrayList<>();
        numbers.add(23);
        numbers.add(42);
        numbers.add(15);
        numbers.add(8);
        numbers.add(19);
        numbers.add(60);
        numbers.add(33);
        numbers.add(90);
        numbers.add(12);
        numbers.add(7);

        // Sort the list in ascending order
        Collections.sort(numbers);

        // Print the sorted list
        System.out.println("Sorted list: " + numbers);

        // Filter and print only even numbers using enhanced for loop
        System.out.println("Even numbers:");
        for (int num : numbers) {
            if (num % 2 == 0) {
                System.out.println(num);
            }
        }
    }
}



## Sets popcorn hack 

import java.util.HashMap;
import java.util.Map;
import java.util.Scanner;
import java.util.TreeMap;

public class PhoneBook {
    public static void main(String[] args) {
        // Creating the phone book with given names
        Map<String, String> phoneBook = new HashMap<>();
        phoneBook.put("Tara", "858-123-4567");
        phoneBook.put("Lilian", "858-234-5678");
        phoneBook.put("Alisha", "858-345-6789");
        phoneBook.put("Sharon", "858-456-7890");
        phoneBook.put("Anika", "858-567-8901");

        Scanner scanner = new Scanner(System.in);
        String input;

        System.out.println("Welcome to the Phone Book!");
        System.out.println("Type a name to search for a phone number, 'all' to display the entire phone book, or 'quit' to exit.");

        while (true) {
            System.out.print("\nEnter a command or name: ");
            input = scanner.nextLine().trim();

            if (input.equalsIgnoreCase("quit")) {
                System.out.println("Exiting the phone book. Goodbye!");
                break;
            } else if (input.equalsIgnoreCase("all")) {
                printSortedPhoneBook(phoneBook);
            } else {
                if (phoneBook.containsKey(input)) {
                    System.out.println(input + "'s number is: " + phoneBook.get(input));
                } else {
                    System.out.println("Name not found in the phone book.");
                }
            }
        }

        scanner.close();
    }

    // Print the phone book in sorted order by name
    public static void printSortedPhoneBook(Map<String, String> phoneBook) {
        System.out.println("\nPhone Book (sorted by name):");
        Map<String, String> sorted = new TreeMap<>(phoneBook);
        for (String name : sorted.keySet()) {
            System.out.println(name + ": " + sorted.get(name));
        }
    }
}

## Q and DQ popcorn hack 
import java.util.ArrayDeque;
import java.util.ArrayList;
import java.util.Deque;
import java.util.List;

public class DequeExperiment {
    public static void main(String[] args) {
        // Create a deque
        Deque<String> deque = new ArrayDeque<>();

        // Add elements to both ends
        deque.addFirst("Tara");
        deque.addLast("Lillian");
        deque.addFirst("Alisha");
        deque.addLast("Sharon");
        deque.addFirst("Anika");

        // Current state: [Anika, Alisha, Tara, Lillian, Sharon]
        System.out.println("Deque after additions: " + deque);

        // Remove one element from each end
        String removedFirst = deque.removeFirst();  // Anika
        String removedLast = deque.removeLast();    // Sharon

        System.out.println("Removed from front: " + removedFirst);
        System.out.println("Removed from end: " + removedLast);

        // Print updated deque
        System.out.println("Deque after removals: " + deque);

        // Optional: convert to list and print
        List<String> asList = new ArrayList<>(deque);
        System.out.println("Converted to List: " + asList);

        // Optional: empty the deque while printing each removed element
        System.out.println("Emptying the deque:");
        while (!deque.isEmpty()) {
            System.out.println("Removed: " + deque.removeFirst());
        }

        // Final state
        System.out.println("Deque is now empty: " + deque);
    }
}


## Part 1 hw 
import java.util.ArrayList;
import java.util.List;

public class ListExample {
    // Filters even numbers from the input list
    public static List<Integer> filterEvenNumbers(List<Integer> input) {
        List<Integer> evens = new ArrayList<>();
        for (int i = 0; i < input.size(); i++) {
            int num = input.get(i);
            if (num % 2 == 0) {
                evens.add(num);
            }
        }
        return evens;
    }

    public static void main(String[] args) {
        List<Integer> input = new ArrayList<>();
        for (int i = 1; i <= 10; i++) {
            input.add(i);
        }

        List<Integer> result = filterEvenNumbers(input);

        System.out.println("Input List: " + input);
        System.out.println("Filtered Even Numbers: " + result);
    }
}

## part 2 hw 
import java.util.HashSet;
import java.util.Set;

public class SetExample {
    // Finds the intersection between two sets
    public static Set<String> findIntersection(Set<String> set1, Set<String> set2) {
        Set<String> result = new HashSet<>();
        for (String item : set1) {
            if (set2.contains(item)) {
                result.add(item);
            }
        }
        return result;
    }

    public static void main(String[] args) {
        Set<String> set1 = new HashSet<>();
        set1.add("apple");
        set1.add("banana");
        set1.add("cherry");
        set1.add("date");

        Set<String> set2 = new HashSet<>();
        set2.add("banana");
        set2.add("date");
        set2.add("fig");
        set2.add("grape");

        Set<String> intersection = findIntersection(set1, set2);

        System.out.println("Set1: " + set1);
        System.out.println("Set2: " + set2);
        System.out.println("Intersection: " + intersection);
    }
}

## part 3 hw 

import java.util.ArrayDeque;
import java.util.Deque;

public class DequeExample {
    public static void main(String[] args) {
        Deque<String> line = new ArrayDeque<>();

        // Enqueue 4 regular customers at the end
        line.addLast("Alice");
        line.addLast("Bob");
        line.addLast("Charlie");
        line.addLast("Diana");

        System.out.println("Initial line after adding 4 customers (end): " + line);

        // VIP customer arrives at the front
        line.addFirst("VIP1");
        System.out.println("After VIP arrival (added at front): " + line);

        // Serve customer at the front
        line.removeFirst();
        System.out.println("After serving the customer at the front (removed): " + line);

        // Inspect front and back of the line
        System.out.println("Current front of the line: " + line.peekFirst());
        System.out.println("Current back of the line: " + line.peekLast());

        // Size of the deque
        System.out.println("Total number of customers waiting: " + line.size());
    }
}

## bonus: 
// Use a HashSet for storing unique student IDs efficiently
Set<String> studentIDs = new HashSet<>();
