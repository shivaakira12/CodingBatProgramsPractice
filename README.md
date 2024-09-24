Here is the full explanation along with the question and code, formatted as requested:

---

### **Question:**

Write a function that takes a string as input and returns a new string where each character from the original string appears twice consecutively.

#### **Examples:**

- `doubleChar("The")` → `"TThhee"`
- `doubleChar("AAbb")` → `"AAAAbbbb"`
- `doubleChar("Hi-There")` → `"HHii--TThheerree"`

### **Approach:**

1. **Problem Breakdown:**
   - For each character in the input string, we need to append the character twice to a result string.
   - To efficiently handle string operations, we will use a `StringBuilder` which allows mutable string construction.
   
2. **Steps:**
   - Create a `StringBuilder` object to store the resulting string.
   - Iterate through each character in the input string.
   - Append each character to the `StringBuilder` twice.
   - After processing all characters, convert the `StringBuilder` back to a string and return it.

3. **Time Complexity:**
   - The time complexity of the solution is **O(n)**, where **n** is the length of the input string. This is because we process each character in the input string exactly twice.

### **Code:**

```java
public class DoubleChar {

    // Method that returns a string where every char in the original is repeated twice
    public static String doubleChar(String str) {
        // Using StringBuilder for efficient string concatenation
        StringBuilder result = new StringBuilder();
        
        // Loop through each character in the string
        for (int i = 0; i < str.length(); i++) {
            char c = str.charAt(i);    // Get the current character
            result.append(c).append(c); // Append the character twice
        }
        
        // Convert the StringBuilder to a string and return it
        return result.toString();
    }

    // Main method to test the doubleChar method
    public static void main(String[] args) {
        // Test cases
        System.out.println(doubleChar("The"));       // Output: "TThhee"
        System.out.println(doubleChar("AAbb"));      // Output: "AAAAbbbb"
        System.out.println(doubleChar("Hi-There"));  // Output: "HHii--TThheerree"
    }
}
```

### **Explanation of Code:**

- **Method `doubleChar(String str)`**:
  - We initialize a `StringBuilder` to accumulate the result.
  - We iterate over each character of the input string using a for loop.
  - For each character, we append it twice to the `StringBuilder`.
  - Finally, we return the constructed string by calling the `toString()` method of `StringBuilder`.

- **Main Method**:
  - The main method tests the `doubleChar` method using different input strings.
  - The expected outputs for each test case are displayed as comments.

### **Output:**
For the given test cases:
```
TThhee
AAAAbbbb
HHii--TThheerree
```
### **Question:**

Write a function that takes a string as input and returns the number of times the substring "hi" appears within the string. The search should be case-sensitive, meaning only lowercase "hi" will be counted.

#### **Examples:**

- `countHi("abc hi ho")` → `1`
- `countHi("ABChi hi")` → `2`
- `countHi("hihi")` → `2`

### **Approach:**

1. **Problem Breakdown:**
   - We need to scan the string and count every occurrence of the exact substring "hi".
   - The function should be case-sensitive, so only the lowercase "hi" will be considered.

2. **Steps:**
   - Initialize a counter to zero.
   - Use a loop or string method to check for occurrences of the substring "hi".
   - Increment the counter every time the substring "hi" is found.
   - Return the total count.

3. **Time Complexity:**
   - The time complexity is **O(n)**, where **n** is the length of the input string. We traverse the string once and count how many times "hi" appears.

### **Code:**

```java
public class CountHi {

    // Method that returns the number of times "hi" appears in the string
    public static int countHi(String str) {
        int count = 0; // Initialize counter for occurrences of "hi"
        
        // Loop through the string, checking for occurrences of "hi"
        for (int i = 0; i < str.length() - 1; i++) {
            // Check if the current and next character form "hi"
            if (str.substring(i, i + 2).equals("hi")) {
                count++; // Increment the counter if "hi" is found
            }
        }
        
        return count; // Return the final count
    }

    // Main method to test the countHi method
    public static void main(String[] args) {
        // Test cases
        System.out.println(countHi("abc hi ho"));  // Output: 1
        System.out.println(countHi("ABChi hi"));   // Output: 2
        System.out.println(countHi("hihi"));       // Output: 2
    }
}
```

### **Explanation of Code:**

- **Method `countHi(String str)`**:
  - We initialize a counter `count` to track the number of times the substring "hi" appears.
  - A loop iterates through the string, checking every pair of consecutive characters using `substring(i, i + 2)`.
  - Whenever we find "hi", we increment the `count`.
  - The loop runs until `i` is less than `str.length() - 1` to avoid going out of bounds.
  - The function returns the total count.

- **Main Method**:
  - The main method tests the `countHi` method with various input strings to ensure correctness.

### **Output:**
For the given test cases:
```
1
2
2
```
