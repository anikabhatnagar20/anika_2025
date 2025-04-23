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
