# Chapter 3 Practice

<a name="jlv5X"></a>
## 218. Student Level

<br />[Question](https://www.lintcode.com/problem/student-level/description)

---

<a name="i4XEu"></a>
#### Solution
```java
public class Student {
    /**
     * Declare two public attributes name(string) and score(int).
     */
    
    public String name;
    public int score;
    
    /**
     * Declare a constructor expect a name as a parameter.
     */
    
    public Student(String name) {
        this.name = name;
    }
    
    /**
     * Declare a public method `getLevel` to get the level(char) of this student.
     */
    
    public char getLevel() {
        if (score >= 90) {
            return 'A';
        } else if (score >= 80) {
            return 'B';
        } else if (score >= 60) {
            return 'C';
        } else {
            return 'D';
        }
    }
}
```

---

<a name="PONTK"></a>
## 455. Student ID

<br />[Question](https://www.lintcode.com/problem/student-id/description)

---

<a name="qQSLx"></a>
#### Solution
```java
class Student {
    public int id;
    
    public Student(int id) {
        this.id = id;
    }
}

public class Class {
    /**
     * Declare a public attribute `students` which is an array of `Student`
     * instances
     */
    public Student[] students;
     
    /**
     * Declare a constructor with a parameter n which is the total number of
     * students in the *class*. The constructor should create n Student
     * instances and initialized with student id from 0 ~ n-1
     */
    public Class(int n) {
        this.students = new Student[n];
        for (int i = 0; i < n; i++) {
            this.students[i] = new Student(i);
        }
    }
}
```

---

<a name="YOeaA"></a>
## 241. String to Integer

<br />[Question](https://www.lintcode.com/problem/string-to-integer/description)

---

<a name="efrWI"></a>
#### Solution
```java
public class Solution {
    /**
     * @param str: A string
     * @return: An integer
     */
    public int stringToInteger(String str) {
        if (str == null || str.isEmpty()) return 0;
        boolean isNegative = str.charAt(0) == '-';
        int start = isNegative ? 1 : 0;
        int result = 0;
        for (int i = start; i < str.length(); i++) {
            char ch = str.charAt(i);
            int digit = ch - '0';
            result = isNegative ? result * 10 - digit : result * 10 + digit;
        }
        return result;
    }
}
```


