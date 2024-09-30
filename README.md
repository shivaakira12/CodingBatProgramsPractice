

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
## 1. RepeatSeparator Problem
### Question
Given two strings, `word` and a separator `sep`, return a big string made of `count` occurrences of the `word`, separated by the `separator` string.
| Input                            | Output                 |
|-----------------------------------|------------------------|
| `repeatSeparator("Word", "X", 3)` | `"WordXWordXWord"`     |
| `repeatSeparator("This", "And", 2)` | `"ThisAndThis"`        |
| `repeatSeparator("This", "And", 1)` | `"This"`               |
### Solution
```java
package StringPrograms;
public class RepeatSeparator {
    public static void main(String[] args) {
        System.out.println(repeatSeparator("Word", "X", 3));
        System.out.println(repeatSeparator("This", "And", 2));
        System.out.println(repeatSeparator("This", "And", 1));
    }
    private static String repeatSeparator(String word, String sep, int count) {
        StringBuilder result = new StringBuilder(word);
        for (int i = 1; i < count; i++) {
            result.append(sep).append(word);
        }
        return result.toString();
    }
}
```
---
## 2. PrefixAgain Problem
### Question
Given a string, consider the prefix string made of the first N chars of the string. Does that prefix string appear somewhere else in the string? Assume that the string is not empty and that N is in the range 1..str.length().
| Input                            | Output                |
|-----------------------------------|-----------------------|
| `prefixAgain("abXYabc", 1)`       | `true`                |
| `prefixAgain("abXYabc", 2)`       | `true`                |
| `prefixAgain("abXYabc", 3)`       | `false`               |
### Solution
```java
package StringPrograms;
public class PrefixAgain {
    public static void main(String[] args) {
        System.out.println(prefixAgain("abXYabc", 1));
        System.out.println(prefixAgain("abXYabc", 2));
        System.out.println(prefixAgain("abXYabc", 3));
    }
    public static boolean prefixAgain(String str, int N) {
        String prefix = str.substring(0, N);
        return str.indexOf(prefix, N) != -1;  // Search from position N onwards
    }
}
```
---
## 3. XyzMiddle Problem
### Question
Given a string, does "xyz" appear in the middle of the string? To define middle, we'll say that the number of chars to the left and right of the "xyz" must differ by at most one.
| Input                     | Output     |
|---------------------------|------------|
| `xyzMiddle("AAxyzBB")`    | `true`     |
| `xyzMiddle("AxyzBB")`     | `true`     |
| `xyzMiddle("AxyzBBB")`    | `false`    |
### Solution
```java
package StringPrograms;
public class XyzMiddle {
    public static void main(String[] args) {
        System.out.println(xyzMiddle("AAxyzBB"));
        System.out.println(xyzMiddle("AxyzBB"));
        System.out.println(xyzMiddle("AxyzBBB"));
    }
    public static boolean xyzMiddle(String str) {
        int len = str.length();
        if (len < 3) {
            return false;
        }
        int midIndex = len / 2;
        if (len % 2 == 1) {
            return str.substring(midIndex - 1, midIndex + 2).equals("xyz");
        } else {
            return str.substring(midIndex - 1, midIndex + 2).equals("xyz") ||
                   str.substring(midIndex - 2, midIndex + 1).equals("xyz");
        }
    }
}
```
---
## 4. RepeatEnd Problem
### Question
Given a string and an int n, return a string made of n repetitions of the last n characters of the string. You may assume that n is between 0 and the length of the string, inclusive.
| Input                         | Output       |
|-------------------------------|--------------|
| `repeatEnd("Hello", 3)`       | `"llollollo"` |
| `repeatEnd("Hello", 2)`       | `"lolo"`      |
| `repeatEnd("Hello", 1)`       | `"o"`         |
### Solution
```java
package StringPrograms;
public class RepeatEnd {
    public static void main(String[] args) {
        System.out.println(repeatEnd("Hello", 3)); // → "llollollo"
        System.out.println(repeatEnd("Hello", 2)); // → "lolo"
        System.out.println(repeatEnd("Hello", 1)); // → "o"
    }
    private static String repeatEnd(String str, int num) {
        String endSubstring = str.substring(str.length() - num);
        return endSubstring.repeat(num);
    }
}
```

---
