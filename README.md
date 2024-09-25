

---
# **String** Medium String problems -- 1 loop
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

### **Question:**

Write a function that takes two strings as input and returns `true` if either of the strings appears at the very end of the other string, ignoring case differences.

#### **Examples:**

- `endOther("Hiabc", "abc")` → `true`
- `endOther("AbC", "HiaBc")` → `true`
- `endOther("abc", "abXabc")` → `true`

### **Approach:**

1. **Problem Breakdown:**
   - We need to check if one string appears at the end of the other string.
   - The comparison should be case-insensitive.

2. **Steps:**
   - Convert both strings to lowercase to ignore case differences.
   - Use the `endsWith` method (or a similar approach) to check if one string ends with the other.
   - Return `true` if either string ends with the other; otherwise, return `false`.

3. **Time Complexity:**
   - The time complexity is **O(n)**, where **n** is the length of the longer string. This is because we may need to compare characters from the end of each string.

### **Code:**

```java
public class EndOther {

    // Method that returns true if either string appears at the end of the other
    public static boolean endOther(String str1, String str2) {
        // Convert both strings to lowercase
        String lowerStr1 = str1.toLowerCase();
        String lowerStr2 = str2.toLowerCase();
        
        // Check if str1 ends with str2 or str2 ends with str1
        return lowerStr1.endsWith(lowerStr2) || lowerStr2.endsWith(lowerStr1);
    }

    // Main method to test the endOther method
    public static void main(String[] args) {
        // Test cases
        System.out.println(endOther("Hiabc", "abc"));     // Output: true
        System.out.println(endOther("AbC", "HiaBc"));     // Output: true
        System.out.println(endOther("abc", "abXabc"));    // Output: true
        System.out.println(endOther("Hello", "World"));   // Output: false
    }
}
```

### **Explanation of Code:**

- **Method `endOther(String str1, String str2)`**:
  - The method first converts both input strings to lowercase using `toLowerCase()` to ensure the comparison is case-insensitive.
  - It then checks if `lowerStr1` ends with `lowerStr2` using `endsWith()`, or if `lowerStr2` ends with `lowerStr1`.
  - The method returns `true` if either condition is satisfied; otherwise, it returns `false`.

- **Main Method**:
  - The main method tests the `endOther` method with various input strings and prints the results.

### **Output:**
For the given test cases:
```
true
true
true
false
``` 

This implementation correctly checks if one string appears at the end of the other, ignoring case differences.

### **Question:**

Write a function that returns `true` if the given string contains an appearance of "xyz" where "xyz" is not directly preceded by a period (.). 

#### **Examples:**

- `xyzThere("abcxyz")` → `true`
- `xyzThere("abc.xyz")` → `false`
- `xyzThere("xyz.abc")` → `true`

### **Approach:**

1. **Problem Breakdown:**
   - We need to check for occurrences of "xyz" in the string.
   - The condition is that "xyz" should not be preceded directly by a period.

2. **Steps:**
   - Loop through the string to find occurrences of "xyz".
   - For each occurrence of "xyz", check if the character before it is a period (and handle the case when "xyz" is at the start of the string).
   - Return `true` if a valid occurrence is found; otherwise, return `false`.

3. **Time Complexity:**
   - The time complexity is **O(n)**, where **n** is the length of the input string, as we might need to scan through the entire string.

### **Code:**

```java
public class XyzThere {

    // Method that returns true if "xyz" appears not preceded by a period
    public static boolean xyzThere(String str) {
        // Loop through the string, checking for "xyz"
        for (int i = 0; i < str.length() - 2; i++) {
            // Check if current substring is "xyz"
            if (str.substring(i, i + 3).equals("xyz")) {
                // Check if it's either at the start or not preceded by a period
                if (i == 0 || str.charAt(i - 1) != '.') {
                    return true; // Valid occurrence found
                }
            }
        }
        return false; // No valid occurrence found
    }

    // Main method to test the xyzThere method
    public static void main(String[] args) {
        // Test cases
        System.out.println(xyzThere("abcxyz"));      // Output: true
        System.out.println(xyzThere("abc.xyz"));     // Output: false
        System.out.println(xyzThere("xyz.abc"));     // Output: true
        System.out.println(xyzThere("xyz"));         // Output: true
        System.out.println(xyzThere(".xyz"));        // Output: false
    }
}
```

### **Explanation of Code:**

- **Method `xyzThere(String str)`**:
  - The method iterates through the string, checking every substring of length 3 to see if it matches "xyz".
  - If a match is found, it checks if the character before the match is a period or if the match is at the start of the string (index 0).
  - If the conditions are satisfied, the method returns `true`.
  - If no valid occurrences are found after the loop, the method returns `false`.

- **Main Method**:
  - The main method tests the `xyzThere` method with various input strings and prints the results.

### **Output:**
For the given test cases:
```
true
false
true
true
false
``` 

This implementation correctly checks for the presence of "xyz" in the string under the specified conditions.


### **Question:**

Write a function that returns `true` if the given string contains a "bob" pattern, where the middle 'o' can be any character.

#### **Examples:**

- `bobThere("abcbob")` → `true`
- `bobThere("b9b")` → `true`
- `bobThere("bac")` → `false`

### **Approach:**

1. **Problem Breakdown:**
   - The pattern we are looking for is "b_b", where `_` can be any character.
   - We need to find occurrences of this pattern in the string and return `true` if it exists.

2. **Steps:**
   - Loop through the string, checking every substring of length 3.
   - If the substring starts with 'b', ends with 'b', and has any character in between, return `true`.
   - If no such pattern is found, return `false`.

3. **Time Complexity:**
   - The time complexity is **O(n)**, where **n** is the length of the input string, since we scan through the string once.

### **Code:**

```java
public class BobThere {

    // Method that returns true if the pattern "b_b" appears in the string
    public static boolean bobThere(String str) {
        // Loop through the string, checking for "b_b" pattern
        for (int i = 0; i < str.length() - 2; i++) {
            // Check if the substring matches the pattern "b_b"
            if (str.charAt(i) == 'b' && str.charAt(i + 2) == 'b') {
                return true; // Valid "bob" pattern found
            }
        }
        return false; // No valid "bob" pattern found
    }

    // Main method to test the bobThere method
    public static void main(String[] args) {
        // Test cases
        System.out.println(bobThere("abcbob"));   // Output: true
        System.out.println(bobThere("b9b"));      // Output: true
        System.out.println(bobThere("bac"));      // Output: false
        System.out.println(bobThere("bbbbb"));    // Output: true
        System.out.println(bobThere("bxb"));      // Output: true
    }
}
```

### **Explanation of Code:**

- **Method `bobThere(String str)`**:
  - The method loops through the string, checking every substring of length 3.
  - It looks for the pattern where the first and third characters are both 'b' (`b_b`).
  - If such a pattern is found, the method immediately returns `true`.
  - If no such pattern is found, the method returns `false`.

- **Main Method**:
  - The main method tests the `bobThere` method with different input strings and prints the results.

### **Output:**
For the given test cases:
```
true
true
false
true
true
``` 

This implementation correctly identifies the "bob" pattern, where the middle character can be any character.

