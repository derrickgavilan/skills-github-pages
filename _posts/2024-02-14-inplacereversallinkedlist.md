---
title: "Pattern: In-Place Reversal Linked List"
date: 2024-02-14
---

# In-Place Reversal Linked List

```
public class ListNode
{
    public int val;
    public ListNode next;
    public ListNode(int val = 0, ListNode next = null)
    {
        this.val = val;
        this.next = next;
    }
}

static void InPlaceReverseList()
{
    // Set up the data
    ListNode node2 = new ListNode(val: 2, next: null);
    ListNode node1 = new ListNode(val: 1, next: node2);
    ListNode node0 = new ListNode(val: 0, next: node1);

    ListNode cur = node0;
    while (cur != null)
    {
        Console.WriteLine(cur.val);
        cur = cur.next;
    }

    // Reverse the linked list
    ListNode cur2 = ReverseList(node0);
    while (cur2 != null)
    {
        Console.WriteLine(cur2.val);
        cur2 = cur2.next;
    }
}

static ListNode ReverseList(ListNode head)
{
    if (head == null || head.next == null)
    {
        return head;
    }

    ListNode prev = null;
    ListNode curr = head;

    while (curr != null)
    {
        ListNode next = curr.next;
        
        curr.next = prev;
        prev = curr;

        // Move to the next node
        curr = next;
    }

    /*

    ORIG:
    0 -> 1 
    1 -> 2 
    2 -> null

    REVERSE:
    0 -> null
    1 -> 0
    2 -> 1

    */

    return prev;
}
```

### References:
[https://www.youtube.com/watch?v=XM0b_MhW7NA](https://www.youtube.com/watch?v=XM0b_MhW7NA)
