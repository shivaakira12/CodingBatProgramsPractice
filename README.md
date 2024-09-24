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

### **Question:**

Write a function that returns `true` if the string "cat" and "dog" appear the same number of times in the given string. The function should be case-sensitive, meaning only lowercase "cat" and "dog" are considered.

#### **Examples:**

- `catDog("catdog")` → `true`
- `catDog("catcat")` → `false`
- `catDog("1cat1cadodog")` → `true`

### **Approach:**

1. **Problem Breakdown:**
   - We need to count how many times the substrings "cat" and "dog" appear in the input string.
   - If the counts for both substrings are equal, we return `true`. Otherwise, return `false`.

2. **Steps:**
   - Initialize two counters: one for "cat" and one for "dog".
   - Use a loop to go through the string, checking for occurrences of "cat" and "dog".
   - Increment the respective counter when either substring is found.
   - After looping through the string, compare the two counters.
   - Return `true` if the counts are equal, otherwise return `false`.

3. **Time Complexity:**
   - The time complexity is **O(n)**, where **n** is the length of the input string. We traverse the string once, checking for both substrings.

### **Code:**

```java
public class CatDog {

    // Method that returns true if "cat" and "dog" appear the same number of times
    public static boolean catDog(String str) {
        int catCount = 0; // Counter for "cat"
        int dogCount = 0; // Counter for "dog"
        
        // Loop through the string, checking for occurrences of "cat" and "dog"
        for (int i = 0; i < str.length() - 2; i++) {
            // Check for "cat"
            if (str.substring(i, i + 3).equals("cat")) {
                catCount++;
            }
            // Check for "dog"
            if (str.substring(i, i + 3).equals("dog")) {
                dogCount++;
            }
        }
        
        // Return true if the counts of "cat" and "dog" are equal, else false
        return catCount == dogCount;
    }

    // Main method to test the catDog method
    public static void main(String[] args) {
        // Test cases
        System.out.println(catDog("catdog"));         // Output: true
        System.out.println(catDog("catcat"));         // Output: false
        System.out.println(catDog("1cat1cadodog"));   // Output: true
    }
}
```

### **Explanation of Code:**

- **Method `catDog(String str)`**:
  - We initialize two counters: `catCount` to count occurrences of "cat" and `dogCount` to count occurrences of "dog".
  - A loop iterates through the string, using `substring(i, i + 3)` to check for "cat" and "dog".
  - Each time we find "cat", we increment `catCount`, and for "dog", we increment `dogCount`.
  - The loop runs until `i` is less than `str.length() - 2` to avoid going out of bounds for the 3-character check.
  - Finally, the function returns `true` if `catCount` equals `dogCount`, otherwise it returns `false`.

- **Main Method**:
  - The main method tests the `catDog` method with different input strings and prints the results.

### **Output:**
For the given test cases:
```
true
false
true
```
### **Question:**

Write a function that returns the number of times the substring "code" appears in the given string, where any letter can be accepted in place of the letter 'd'.

#### **Examples:**

- `countCode("aaacodebbb")` → `1`
- `countCode("codexxcode")` → `2`
- `countCode("cozexxcope")` → `2`

### **Approach:**

1. **Problem Breakdown:**
   - We need to find occurrences of "co_e", where `_` can be any character.
   - For each substring that matches "co_e", we should increment our count.

2. **Steps:**
   - Initialize a counter to zero.
   - Loop through the string and check each substring of length 4.
   - If the substring starts with "co", ends with "e", and has any character in between, increment the counter.
   - Return the total count after checking all possible substrings.

3. **Time Complexity:**
   - The time complexity is **O(n)**, where **n** is the length of the input string. We iterate through the string once.

### **Code:**

```java
public class CountCode {

    // Method that returns the number of times "code" appears with any letter for 'd'
    public static int countCode(String str) {
        int count = 0; // Initialize counter
        
        // Loop through the string up to the length - 3 to avoid out-of-bounds
        for (int i = 0; i < str.length() - 3; i++) {
            // Check if substring matches "co_e"
            if (str.charAt(i) == 'c' && str.charAt(i + 1) == 'o' && str.charAt(i + 3) == 'e') {
                count++; // Increment count if match found
            }
        }
        
        return count; // Return the final count
    }

    // Main method to test the countCode method
    public static void main(String[] args) {
        // Test cases
        System.out.println(countCode("aaacodebbb"));  // Output: 1
        System.out.println(countCode("codexxcode"));   // Output: 2
        System.out.println(countCode("cozexxcope"));   // Output: 2
    }
}
```

### **Explanation of Code:**

- **Method `countCode(String str)`**:
  - We initialize a counter `count` to keep track of occurrences.
  - A loop iterates through the string up to `str.length() - 3` to avoid going out of bounds when checking substrings of length 4.
  - Inside the loop, we check if the substring starts with 'c', has 'o' as the second character, and ends with 'e', while allowing any character in the third position. 
  - If the condition is met, we increment the `count`.
  - Finally, the function returns the total count of occurrences.

- **Main Method**:
  - The main method tests the `countCode` method with various input strings and prints the results.

### **Output:**
For the given test cases:
```
1
2
2
``` 

This implementation accurately counts occurrences of the substring "code" with any character in place of 'd'.
