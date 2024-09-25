

---

# String Manipulation Challenges

This repository contains solutions to several string manipulation problems. Below is a description of each problem, examples in a table format, and the corresponding Java code to solve it.

## Problem 1: **Double Char**

### Question:
Given a string, return a string where for every character in the original, there are two characters.

| Input         | Output     |
|---------------|------------|
| "The"         | "TThhee"   |
| "AAbb"        | "AAAAbbbb" |
| "Hi-There"    | "HHii--TThheerree" |

### Solution:
```java
public class DoubleChar {
    public static String doubleChar(String str) {
        StringBuilder result = new StringBuilder();
        for (int i = 0; i < str.length(); i++) {
            char c = str.charAt(i);
            result.append(c).append(c);
        }
        return result.toString();
    }

    public static void main(String[] args) {
        System.out.println(doubleChar("The"));
        System.out.println(doubleChar("AAbb"));
        System.out.println(doubleChar("Hi-There"));
    }
}
```

---

## Problem 2: **Count Hi**

### Question:
Return the number of times that the string "hi" appears anywhere in the given string.

| Input           | Output |
|-----------------|--------|
| "abc hi ho"     | 1      |
| "ABChi hi"      | 2      |
| "hihi"          | 2      |

### Solution:
```java
public class CountHi {
    public static int countHi(String str) {
        int count = 0;
        for (int i = 0; i < str.length() - 1; i++) {
            if (str.substring(i, i + 2).equals("hi")) {
                count++;
            }
        }
        return count;
    }

    public static void main(String[] args) {
        System.out.println(countHi("abc hi ho"));
        System.out.println(countHi("ABChi hi"));
        System.out.println(countHi("hihi"));
    }
}
```

---

## Problem 3: **Cat and Dog**

### Question:
Return `true` if the string "cat" and "dog" appear the same number of times in the given string.

| Input               | Output |
|---------------------|--------|
| "catdog"            | true   |
| "catcat"            | false  |
| "1cat1cadodog"      | true   |

### Solution:
```java
public class CatDog {
    public static boolean catDog(String str) {
        int catCount = 0;
        int dogCount = 0;
        for (int i = 0; i < str.length() - 2; i++) {
            if (str.substring(i, i + 3).equals("cat")) {
                catCount++;
            }
            if (str.substring(i, i + 3).equals("dog")) {
                dogCount++;
            }
        }
        return catCount == dogCount;
    }

    public static void main(String[] args) {
        System.out.println(catDog("catdog"));
        System.out.println(catDog("catcat"));
        System.out.println(catDog("1cat1cadodog"));
    }
}
```

---

## Problem 4: **Count Code**

### Question:
Return the number of times that the string "code" appears anywhere in the given string, except we'll accept any letter for the 'd', so "cope" and "cooe" count.

| Input           | Output |
|-----------------|--------|
| "aaacodebbb"    | 1      |
| "codexxcode"    | 2      |
| "cozexxcope"    | 2      |

### Solution:
```java
public class CountCode {
    public static int countCode(String str) {
        int count = 0;
        for (int i = 0; i < str.length() - 3; i++) {
            if (str.substring(i, i + 2).equals("co") && str.charAt(i + 3) == 'e') {
                count++;
            }
        }
        return count;
    }

    public static void main(String[] args) {
        System.out.println(countCode("aaacodebbb"));
        System.out.println(countCode("codexxcode"));
        System.out.println(countCode("cozexxcope"));
    }
}
```

---

## Problem 5: **End Other**

### Question:
Given two strings, return `true` if either of the strings appears at the very end of the other string, ignoring upper/lower case differences.

| Input                | Output |
|----------------------|--------|
| "Hiabc", "abc"       | true   |
| "AbC", "HiaBc"       | true   |
| "abc", "abXabc"      | true   |

### Solution:
```java
public class EndOther {
    public static boolean endOther(String a, String b) {
        a = a.toLowerCase();
        b = b.toLowerCase();
        return a.endsWith(b) || b.endsWith(a);
    }

    public static void main(String[] args) {
        System.out.println(endOther("Hiabc", "abc"));
        System.out.println(endOther("AbC", "HiaBc"));
        System.out.println(endOther("abc", "abXabc"));
    }
}
```

---

## Problem 6: **Mix String**

### Question:
Given two strings, a and b, create a bigger string made of the first char of a, the first char of b, the second char of a, the second char of b, and so on. Any leftover chars go at the end of the result.

| Input           | Output    |
|-----------------|-----------|
| "abc", "xyz"    | "axbycz"  |
| "Hi", "There"   | "HTihere" |
| "xxxx", "There" | "xTxhxexre" |

### Solution:
```java
public class MixString {
    public static String mixString(String a, String b) {
        StringBuilder result = new StringBuilder();
        int minLength = Math.min(a.length(), b.length());
        for (int i = 0; i < minLength; i++) {
            result.append(a.charAt(i)).append(b.charAt(i));
        }
        result.append(a.substring(minLength)).append(b.substring(minLength));
        return result.toString();
    }

    public static void main(String[] args) {
        System.out.println(mixString("abc", "xyz"));
        System.out.println(mixString("Hi", "There"));
        System.out.println(mixString("xxxx", "There"));
    }
}
```

---
