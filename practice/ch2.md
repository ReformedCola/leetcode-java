# Chapter 2 Practice

<a name="cZt57"></a>
## 478. Simple Calculator
<a name="e7oI8"></a>
### Link
[Question](https://www.lintcode.com/problem/simple-calculator/description)
<a name="wEoQ6"></a>
### Answer
```java
public class Calculator {
    /**
     * @param a: An integer
     * @param operator: A character, +, -, *, /.
     * @param b: An integer
     * @return: The result
     */
    public int calculate(int a, char operator, int b) {
        switch (operator) {
            case '+': return a + b;
            case '-': return a - b;
            case '*': return a * b;
            case '/': return a / b;
        }
        return 0;
    }
}
```
<a name="UvxJt"></a>
## 214. Max of Array
<a name="i0kDc"></a>
### Link
[Question](https://www.lintcode.com/problem/max-of-array/description)
<a name="8mu4I"></a>
### Answer
```java
public class Solution {
    /**
     * @param A: An integer
     * @return: a float number
     */
    public float maxOfArray(float[] A) {
        // write your code here
        float max = A[0];
        for (int i = 1; i < A.length; i++) {
            if (A[i] > max) {
                max = A[i];
            }
        }
        return max;
    }
}
```
<a name="35iaL"></a>
## 491. Palindrome Number
<a name="BHP7o"></a>
### Link
[Question](https://www.lintcode.com/problem/palindrome-number/description)
<a name="dXTye"></a>
### Answer
```java
public class Solution {
    /**
     * @param num: a positive number
     * @return: true if it's a palindrome or false
     */
    public boolean isPalindrome(int num) {
        if (num < 0) {
            return false;
        }
        return num == reverse(num);
    }
    
    public int reverse(int num) {
        int result = 0;
        while (num != 0) {
            result = result * 10 + num % 10;
            num /= 10;
        }
        return result;
    }
}
```
<a name="XWqkH"></a>
## 521. Remove Duplicate Numbers in Array
<a name="QkcFd"></a>
### Link
[Question](https://www.lintcode.com/problem/remove-duplicate-numbers-in-array/description)
<a name="tSJGV"></a>
### Answer
```java
public class Solution {
    /**
     * @param nums: an array of integers
     * @return: the number of unique integers
     */
    public int deduplication(int[] nums) {
        if (nums.length == 0) return 0;
        Arrays.sort(nums);
        int slowP = 0;
        for (int fastP = 0; fastP < nums.length; fastP++) {
            if (nums[fastP] != nums[slowP]) {
                slowP++;
                nums[slowP] = nums[fastP];
            }
        }
        return slowP + 1;
    }
}
```


