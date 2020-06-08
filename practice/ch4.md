# Chapter 4 Practice

<a name="u4NmS"></a>
## 385. ArrayList
<a name="1B3k8"></a>
#### Link
[Question](https://www.lintcode.com/problem/arraylist/description)
<a name="fLGIi"></a>
#### Solution
```java
public class ArrayListManager {
    /**
     * @param n: You should generate an array list of n elements.
     * @return: The array list your just created.
     */
    public static ArrayList<Integer> create(int n) {
        ArrayList<Integer> list = new ArrayList<Integer>();
        for (int i = 0; i < n; i++) {
            list.add(i);
        }
        return list;
    }
    
    /**
     * @param list: The list you need to clone
     * @return: A deep copyed array list from the given list
     */
    public static ArrayList<Integer> clone(ArrayList<Integer> list) {
        ArrayList<Integer> newList = new ArrayList<Integer>();
        for (Integer a : list) {
            newList.add(a);
        }
        return newList;
    }
    
    /**
     * @param list: The array list to find the kth element
     * @param k: Find the kth element
     * @return: The kth element
     */
    public static int get(ArrayList<Integer> list, int k) {
        return list.get(k);
    }
    
    /**
     * @param list: The array list
     * @param k: Find the kth element, set it to val
     * @param val: Find the kth element, set it to val
     */
    public static void set(ArrayList<Integer> list, int k, int val) {
        list.set(k, val);
    }
    
    /**
     * @param list: The array list to remove the kth element
     * @param k: Remove the kth element
     */
    public static void remove(ArrayList<Integer> list, int k) {
        list.remove(k);
    }
    
    /**
     * @param list: The array list.
     * @param val: Get the index of the first element that equals to val
     * @return: Return the index of that element
     */
    public static int indexOf(ArrayList<Integer> list, int val) {
        if (list == null) return -1;
        return list.indexOf(val);
    }
}
```
<a name="E8k8u"></a>
## 456. Reference
<a name="wXBeR"></a>
#### Link
[Question](https://www.lintcode.com/problem/reference/description)
<a name="IEXoC"></a>
#### Solution
```java
/**
 * Definition of Node:
 * class Node {
 *     public int val;
 *     public Node(int val) {
 *         this.val = val;
 *     }
 * }
 */
public class ReferenceManager {
    public Node node;

    public void copyValue(Node obj) {
        if (obj == null) return;
        if (node == null) node = new Node(obj.val);
        node.val = obj.val;
    }

    public void copyReference(Node obj) {
        node = obj;
    }
}
```
<a name="6QhNB"></a>
## 656. Multiply Strings
<a name="HjHf1"></a>
#### Link
[Question](https://www.lintcode.com/problem/multiply-strings/description)
<a name="RG1LM"></a>
#### Solution
```java
public class Solution {
    /**
     * @param num1: a non-negative integers
     * @param num2: a non-negative integers
     * @return: return product of num1 and num2
     */
    public String multiply(String num1, String num2) {
        if (num1 == null || num2 == null) {
            return null;
        }
        
        int len1 = num1.length(), len2 = num2.length();
        int len3 = len1 + len2;
        int i, j, product, carry;

        int[] num3 = new int[len3];
        for (i = len1 - 1; i >= 0; i--) {
            carry = 0;
            for (j = len2 - 1; j >= 0; j--) {
                product = carry + num3[i + j + 1] +
                    Character.getNumericValue(num1.charAt(i)) *
                    Character.getNumericValue(num2.charAt(j));
                num3[i + j + 1] = product % 10;
                carry = product / 10;
            }
            num3[i + j + 1] = carry;
        }

        StringBuilder sb = new StringBuilder();
        i = 0;

        while (i < len3 - 1 && num3[i] == 0) {
            i++;
        }

        while (i < len3) {
            sb.append(num3[i++]);
        }

        return sb.toString();
    }
}
```
