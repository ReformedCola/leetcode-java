# Chapter 3 Ladder

<a name="JgqKT"></a>
## 454. Rectangle Area
<a name="HuzMt"></a>
#### Link
[Question](https://www.lintcode.com/problem/rectangle-area/description?_from=ladder&&fromId=71)
<a name="1Q7tZ"></a>
#### Solution
```java
public class Rectangle {
    /*
     * Define two public attributes width and height of type int.
     */
    public int width, height;

    /*
     * Define a constructor which expects two parameters width and height here.
     */
    public Rectangle(int width, int height) {
        this.width = width;
        this.height = height;
    }
    
    /*
     * Define a public method `getArea` which can calculate the area of the
     * rectangle and return.
     */
    public int getArea() {
        return this.width * this.height;
    }
}
```



---

<a name="Xn8FS"></a>
## 484. Swap Two Integers in Array
<a name="bMlJX"></a>
#### Link
[Question](https://www.lintcode.com/problem/swap-two-integers-in-array/description?_from=ladder&&fromId=71)
<a name="USY7E"></a>
#### Solution
```java
public class Solution {
    /**
     * @param A: An integer array
     * @param index1: the first index
     * @param index2: the second index
     * @return: nothing
     */
    public void swapIntegers(int[] A, int index1, int index2) {
        int temp = A[index1];
        A[index1] = A[index2];
        A[index2] = temp;
    }
}
```



---

<a name="G3YLp"></a>
## 222. Setter and Getter
<a name="FygdN"></a>
#### Link
[Question](https://www.lintcode.com/problem/setter-and-getter/description?_from=ladder&&fromId=71)
<a name="A7SiH"></a>
#### Solution
```java
public class School {
    /*
     * Declare a private attribute *name* of type string.
     */
    private String name;

    /**
     * Declare a setter method `setName` which expect a parameter *name*.
     */
    public void setName(String name) {
        this.name = name;
    }

    /**
     * Declare a getter method `getName` which expect no parameter and return
     * the name of this school
     */
    public String getName() {
        return this.name;
    }
}
```



---

<a name="yjPaf"></a>
## 146. Lowercase to Uppercase II
<a name="NxToB"></a>
#### Link
[Question](https://www.lintcode.com/problem/lowercase-to-uppercase-ii/description?_from=ladder&&fromId=71)
<a name="T5uA7"></a>
#### Solution
```java
public class Solution {
    /**
     * @param str: A string
     * @return: A string
     */
    public String lowercaseToUppercase2(String str) {
        StringBuilder sb = new StringBuilder(str);
        for (int index = 0; index < sb.length(); index++) {
            char c = sb.charAt(index);
            if (Character.isLowerCase(c)) {
                sb.setCharAt(index, Character.toUpperCase(c));
            }
        }
        return sb.toString();
    }
}
```


