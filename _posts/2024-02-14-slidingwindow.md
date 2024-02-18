---
title: "Sliding Window"
date: 2024-02-14
---


# Pattern: Sliding Window

```
static void SlidingWindow()
    {
    	// set up the data
        int[] data = { 5, 7, 1, 4, 3, 6, 2, 9, 2 };
        
        // set up window size
        int windowSize = 3;
        
        // hold window value;
        int windowValue = 0;
        
        // hold largest window value
        int largestWindowValue = 0;
        
        // get first window value
        for(int i = 0; i <= data.Length - 1; i++)
        {
        	windowValue += data[i];
        }
        
        Console.WriteLine($"first window is {windowValue}");
        
        largestWindowValue = windowValue;
        
        // loop through array
        // get all window values
        // print largest window value
        
        int j = 1;
        while(j <= data.Length - windowSize)
        {
        	Console.WriteLine($"{data[j - 1]} | {windowValue} | {data[j + windowSize - 1]}");
        
        	// get next window value
            // subtract value from left most element
            // add value in next element
            
            windowValue -= data[j - 1];
            windowValue += data[j + windowSize - 1]; 
            
            // update largest window value
            if(windowValue > largestWindowValue)
            {
            	largestWindowValue = windowValue;
            }
            
            // move to the next element
            j++;
        }
        
        // print largest window value
        Console.WriteLine($"largest window is {largestWindowValue}");
       
    }
```
