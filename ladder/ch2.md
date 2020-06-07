# Chapter 2 Ladder

<a name="uDLGy"></a>
## 449. String to Integer (ASCII)
<a name="o0mZs"></a>
#### Link
[Question](https://www.lintcode.com/problem/char-to-integer/description?_from=ladder&&fromId=71)
<a name="bWmQC"></a>
#### Solution
```java
public class Solution {
    /**
     * @param character: a character
     * @return: An integer
     */
    public int charToInteger(char character) {
        return (int) character;
    }
}
```
<a name="EGBTg"></a>
## 283. Max of 3 Integers
<a name="6TLde"></a>
#### Link
[Question](https://www.lintcode.com/problem/max-of-3-numbers/description?_from=ladder&&fromId=71)
<a name="cMdNp"></a>
#### Solution
```java
public class Solution {
    /**
     * @param num1: An integer
     * @param num2: An integer
     * @param num3: An integer
     * @return: an interger
     */
    public int maxOfThreeNumbers(int num1, int num2, int num3) {
        if (num1 >= num2 && num1 >= num3) {
            return num1;
        } else if (num2 >= num1 && num2 >= num3) {
            return num2;
        } else {
            return num3;
        }
    }
}
```
<a name="yd9cX"></a>
## 145. Lowercase to Uppercase
<a name="7Wvnl"></a>
#### Link
[Question](https://www.lintcode.com/problem/lowercase-to-uppercase/description?_from=ladder&&fromId=71)
<a name="f2P7E"></a>
#### Solution
```java
public class Solution {
    /**
     * @param character: a character
     * @return: a character
     */
    public char lowercaseToUppercase(char character) {
        return (char)(character - 'a' + 'A');
    }
}
```
<a name="a4fvO"></a>
## Second Max of Array
<a name="xlwb8"></a>
#### Link
[Question](https://www.lintcode.com/problem/second-max-of-array/description?_from=ladder&&fromId=71)
<a name="tSwyf"></a>
#### Solution
```java
public class Solution {
    /**
     * @param nums: An integer array
     * @return: The second max number in the array.
     */
    public int secondMax(int[] nums) {
        int max = Math.max(nums[0], nums[1]);
        int second = Math.min(nums[0], nums[1]);
        for (int i = 2; i < nums.length; i++) {
            if (nums[i] > max) {
                second = max;
                max = nums[i];
            } else if (nums[i] > second) {
                second = nums[i];
            }
        }
        return second;
    }
}
```
