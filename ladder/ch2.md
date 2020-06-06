# Chapter 2 Ladder

<a name="9vEjf"></a>
## 37. Reverse 3-digit Integer
<a name="bEDTH"></a>
### Link
[Question](https://www.lintcode.com/problem/reverse-3-digit-integer/description?_from=ladder&&fromId=71)
<a name="woO2f"></a>
### Solution
```java
public class Solution {
    /**
     * @param number: A 3-digit number.
     * @return: Reversed number.
     */
    public int reverseInteger(int number) {
        int single = number % 10;
        int ten = (number / 10) % 10;
        int hundred = ((number / 10) / 10) % 10;
        return hundred + ten * 10 + single * 100;
    }
}
```
<a name="4CT4a"></a>
## 9. Fizz Buzz
<a name="Lmbvb"></a>
### Link    
[Question](https://www.lintcode.com/problem/fizz-buzz/description?_from=ladder&&fromId=71)
<a name="21YWO"></a>
### Solution
```java
// Method 1
public class Solution {
    /**
     * @param n: An integer
     * @return: A list of strings.
     */
    public List<String> fizzBuzz(int n) {
        ArrayList<String> result = new ArrayList<String>();
        for (int i = 1; i <= n; i++) {
            if (i % 15 == 0) {
                result.add("fizz buzz");
            } else if (i % 5 == 0) {
                result.add("buzz");
            } else if (i % 3 == 0) {
                result.add("fizz");
            } else {
                result.add(String.valueOf(i));
            }
        }
        return result;
    }
}

// Method 2
public class Solution {
    /**
     * @param n: An integer
     * @return: A list of strings.
     */
    public List<String> fizzBuzz(int n) {
        ArrayList<String> result = new ArrayList<String>();
        int i = 1;
        int p3 = 1, p5 = 1;
        while (i <= n) {
            while (i < p3 * 3 && i < p5 * 5) {
                result.add(i + "");
                i++;
            }
            if (i <= n && p3 * 3 == p5 * 5) {
                result.add("fizz buzz");
                p3++;
                p5++;
                i++;
                continue;
            }
            while (i <= n && p3 * 3 <= i) {
                result.add("fizz");
                p3++;
                i++;
            }
            while (i <= n && p5 * 5 <= i) {
                result.add("buzz");
                p5++;
                i++;
            }
        }
        return result;
    }
}
```
<a name="OkPxx"></a>
## 1. A + B Problem
<a name="aEGt8"></a>
### Link
[Question](https://www.lintcode.com/problem/a-b-problem/description?_from=ladder&&fromId=71)
<a name="uEO1r"></a>
### Solution
```java
public class Solution {
    /**
     * @param a: An integer
     * @param b: An integer
     * @return: The sum of a and b 
     */
    public int aplusb(int a, int b) {
        // 主要利用异或运算来完成 
        // 异或运算有一个别名叫做：不进位加法
        // 那么a ^ b就是a和b相加之后，该进位的地方不进位的结果
        // 然后下面考虑哪些地方要进位，自然是a和b里都是1的地方
        // a & b就是a和b里都是1的那些位置，a & b << 1 就是进位
        // 之后的结果。所以：a + b = (a ^ b) + (a & b << 1)
        // 令a' = a ^ b, b' = (a & b) << 1
        // 可以知道，这个过程是在模拟加法的运算过程，进位不可能
        // 一直持续，所以b最终会变为0。因此重复做上述操作就可以
        // 求得a + b的值。
        while (b != 0) {
            int _a = a ^ b;
            int _b = (a & b) << 1;
            a = _a;
            b = _b;
        }
        return a;
    }
}
```


