---
title: "Pattern: In-Place Reversal Linked List"
date: 2024-02-14
---

# In-Place Reversal Linked List

```
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
```

```

static void Main(string[] args)
{
    // data
    ListNode node2 = new ListNode(val: 2, next: null);
    ListNode node1 = new ListNode(val: 1, next: node2);
    ListNode node0 = new ListNode(val: 0, next: node1);
    
    // display original order
    ListNode a = node0;
    while(a != null)
    {
        Console.WriteLine($"{a.val}");
        a = a.next;
    }
    
    // display reverse order
    ListNode b = InPlaceReverseList(node0);
    while(b != null)
    {
        Console.WriteLine($"{b.val}");
        b = b.next;
    }
}

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

static ListNode InPlaceReverseList(ListNode head)
{
    ListNode curr = head;
    ListNode prev = null;
    
    // loop
    while(curr != null)
    {
        ListNode next = curr.next;
        curr.next = prev;
        prev = curr;
        curr = next;
    } // while
    
    return prev;
}


```

### References:
[https://www.youtube.com/watch?v=XM0b_MhW7NA](https://www.youtube.com/watch?v=XM0b_MhW7NA)
