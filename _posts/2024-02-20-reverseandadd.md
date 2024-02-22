---
title: "Challenge: Reverese and Add"
date: 2024-02-20
---

# Reverese and Add

```

Palindrome palindrome = new Palindrome();
palindrome.ReverseAndAdd(195);

```

```

public void ReverseAndAdd(long num)
{
    int loop = 1;
    while (loop <= 100)
    {
        var reversedNum = reverseDigits(num);
        num = num + reversedNum;
        if (IsPalindrome(num))
        {
            Console.WriteLine($"{num} is a palindrome. Iterated {loop} time(s).");
            break;
        }
        
        loop += 1;
    }
}

public bool IsPalindrome(long num)
{
    long reverse_num = reverseDigits(num);
    if (num != reverse_num)
    {
        return false;
    }
    return true;
}

public long reverseDigits(long num)
{
    long rev_num = 0;
    while (num > 0)
    {
        long step1 = rev_num * 10; // build/increment the number by 10
        long step2 = num % 10; // get the remainder

        rev_num = rev_num * 10 + num % 10;

        // remove the 10th place of the original number
        num = num / 10;
    }
    return rev_num;
}

```
