import java.util.Arrays; // Import utility class for array manipulation

// Class definition
public class SortDemo {

    // Main method - entry point of the program
    public static void main(String[] args) {
        // Initialize the array to be sorted
        int[] stock = {29, 10, 14, 37, 13, 18, 25, 30, 4, 9, 12, 40, 50, 23, 28};

        // Call selection sort method with the array
        runSelectionSort(stock);
    }

    // Method to perform selection sort on an integer array
    public static void runSelectionSort(int[] data) {
        // Loop through the array (excluding the last element)
        for (int i = 0; i < data.length - 1; i++) {
            // Assume the current index has the smallest value
            int smallest = i;

            // Find the index of the smallest value in the remaining array
            for (int j = i + 1; j < data.length; j++) {
                if (data[j] < data[smallest]) {
                    smallest = j;
                }
            }

            // Swap the smallest element found with the current element
            int swap = data[smallest];
            data[smallest] = data[i];
            data[i] = swap;
        }

        // Print the sorted array
        System.out.println("Sorted by Selection: " + Arrays.toString(data));
    }
}
