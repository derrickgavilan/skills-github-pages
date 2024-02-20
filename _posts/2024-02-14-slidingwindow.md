---
title: "Sliding Window"
date: 2024-02-14
---


# Pattern: Sliding Window

Notes:
- 1 loop
- loop through the size of the array less the window's size

```

static void SlidingWindow()
{
    // data
    int[] data = { 5, 7, 1, 4, 3, 6, 2, 9, 2 };
    
    // window size
    int windowSize = 5;
    
    // window and largestWindow values
    int window = 0;
    int largestWindow = 0;
    
    // first window
    for(int i=0; i<=data.Length-1; i++)
    {
        window += data[i];
    }
    
    // use window as the largest value for now
    largestWindow = window;
    
    // loop
    // start on 2nd element
    // subtract window size from loop's upper bound check
    for(int j=1; j<=data.Length-windowSize; j++)
    {
        // move to next window
        window -= data[j-1]; // remove left most element in window
        window += data[j+(windowSize-1)]; // add next element to the right of the window
        
        // get largest of the 2 values
        largestWindow = Math.Max(window, largestWindow);
    } // for
    
    Console.WriteLine($"largest window is: {largestWindow}");
}

```
