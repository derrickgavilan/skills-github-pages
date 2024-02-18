---
title: "Merge Intervals"
date: 2024-02-14
---

# Pattern: Merge Intervals

```
static void MergeIntervals()
{
	// Set up the data
        int[][] intervals = new int[][]
        {
            new int[] {1,3},
            new int[] {2,6},
            new int[] {8,10},
            new int[] {15,18},
        };
        
        // get first interval values
        int left = intervals[0][0];
        int right = intervals[0][1];
        
        // Loop through array
        // start at next element
        for(int i = 1; i <= intervals.Length - 1; i++)
        {
            int[] interval = intervals[i];
            
            if(right >= interval[0])
            {
		// overlap
            	// adjust right value
            	right = Math.Max(right, interval[1]);
            }
            else
            {
            	Console.WriteLine($"{left} - {right}");
            
            	// no overlap
            	// reset values
            	left = interval[0];
                right = interval[1];
            }
        } // for

		// Add last interval
        Console.WriteLine($"{left} - {right}");
}
```
