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
