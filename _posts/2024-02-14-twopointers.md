---
title: "Pattern: Two Pointer"
date: 2024-02-14
---

# Two Pointer

Notes:

- 1 loop
- traverse left and right side of array at the same time
- left and right index are manipulated separately

```

static void TwoPointer()
{
    // data
    int[] data = { 1, 2, 3, 7, 8, 9, 11, 22, 33 };
    
    // target
    int target = 17;
    
    // left and right index
    int left = 0;
    int right = data.Length - 1;
    
    // loop
    for(int i=0; i <= data.Length-1; i++)
    {
        // sum of left and right
        int leftRightSum = data[left] + data[right];

        // compare target
        if(target == leftRightSum)
        {
            // done
            Console.WriteLine($"target {target} found in {left},{right}");
            break;
        }
        else
        {
            // move left or right index
            if(leftRightSum < target)
            {
                left += 1;
            }
            else
            {
                right -= 1;
            }
        }
    } // loop
}

```
