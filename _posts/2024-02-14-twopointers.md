---
title: "Pattern: Two Pointer"
date: 2024-02-14
---

# Two Pointer

```
static void TwoPointer()
    {
    	// set up the data
        int[] data = { 1, 2, 3, 7, 8, 9, 11, 22, 33 };
        
        // set up target value to compare left and right sums
        int target = 15;
        
        // set indexes
        int leftIndex = 0;
        int rightIndex = data.Length - 1;
        
        int leftRightSum = 0;
        
        // loop through array
        for(int i = 0; i <= data.Length - 1; i++)
        {
        	// get left and right values
            leftRightSum = data[leftIndex] + data[rightIndex];
            
            Console.WriteLine($"{data[leftIndex]} + {data[rightIndex]}");
            Console.WriteLine($"{target} == {leftRightSum}\n");
            
            // compare with target
            if(target == leftRightSum)
            {
            	// done!
                Console.WriteLine($"target '{target}' found in index {leftIndex} and {rightIndex}");
                return;
            }
            else
            {
            	// move indexes
            	if(leftRightSum < target)
                {
                	leftIndex += 1;
                }
                else
                {
                	rightIndex -= 1;
                }
            }
            
        } // for
    }
```
