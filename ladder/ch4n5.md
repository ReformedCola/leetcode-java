# Chapter 4 and 5 Ladder

<a name="qqujD"></a>
## 483. Convert Linked List to Array List
<a name="FOYz0"></a>
#### Link
[Question](https://www.lintcode.com/problem/convert-linked-list-to-array-list/description?_from=ladder&&fromId=71)
<a name="wGCQa"></a>
#### Solution
```java
/**
 * Definition for ListNode
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */

public class Solution {
    /**
     * @param head: the head of linked list.
     * @return: An integer list
     */
    public List<Integer> toArrayList(ListNode head) {
        List<Integer> result = new ArrayList<Integer>();
        while (head != null) {
            result.add(head.val);
            head = head.next;
        }
        return result;
    }
}
```
<a name="J2xXl"></a>
## 225. Find Node in Linked List
<a name="gRxvk"></a>
#### Link
[Question](https://www.lintcode.com/problem/find-node-in-linked-list/description?_from=ladder&&fromId=71)
<a name="bAnvp"></a>
#### Solution
```java
/**
 * Definition for ListNode
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */


public class Solution {
    /*
     * @param head: the head of linked list.
     * @param val: An integer.
     * @return: a linked node or null.
     */
    public ListNode findNode(ListNode head, int val) {
        for (ListNode node = head; node != null; node = node.next) {
            if (node.val == val) {
                return node;
            }
        }
        return null;
    }
}
```
<a name="tbvlE"></a>
## 174. Remove Nth Node From End of List
<a name="AvSXE"></a>
#### Link
[Question](https://www.lintcode.com/problem/remove-nth-node-from-end-of-list/description?_from=ladder&&fromId=71)
<a name="cFlvv"></a>
#### Solution
```java
/**
 * Definition for ListNode
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) {
 *         val = x;
 *         next = null;
 *     }
 * }
 */

public class Solution {
    /**
     * @param head: The first node of linked list.
     * @param n: An integer
     * @return: The head of linked list.
     */
    public ListNode removeNthFromEnd(ListNode head, int n) {
        if (n <= 0) return null;
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        ListNode slowPointer = dummy;
        for (int fastPointer = 0; fastPointer < n; fastPointer++) {
            if (head == null) return null;
            head = head.next;
        }
        while (head != null) {
            head = head.next;
            slowPointer = slowPointer.next;
        }
        slowPointer.next = slowPointer.next.next;
        return dummy.next;
    }
}
```
