# Pattern: In-Place Reversal Linked List

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
    ListNode cur = head;

    while (cur != null)
    {
        ListNode post = cur.next;
        cur.next = prev;
        prev = cur;
        cur = post;
    }

    /*
    
    prev    cur     next
    ----    ----    ----
    null    0       1
    0       1       2
    1       2       null
    null    null    null

    prev    cur     next
    ----    ----    ----
    null    0       1
    0       1       2
    1       2       null
    2       null    null
    */

    return prev;
}
```
