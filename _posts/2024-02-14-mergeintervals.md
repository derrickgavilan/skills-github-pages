---
title: "Merge Intervals"
date: 2024-02-14
---

# Pattern: Merge Intervals

```

static void MergeIntervals()
{
	// data
	int[][] intervals = new int[][]
	{
	    new int[] {1,3},
	    new int[] {2,6},
	    new int[] {8,10},
	    new int[] {15,18},
	};
	
	// 1st interval
	int left = intervals[0][0];
	int right = intervals[0][1];
	
	// loop
	// start at next interval (i.e. i=1)
	for(int i=1; i<=intervals.Length-1; i++)
	{
		// next interval
		int[] interval = intervals[i];
	    
	    // check for overlap
	    if(right >= interval[0])
	    {
		// overlap
		// merge by getting new right value
		right = Math.Max(right, interval[1]);
	    }
	    else
	    {
		// no overlap
		
		// record left and right values
		Console.WriteLine($"{left},{right}");
		
		// this is a new interval
		// set left and right values
		left = interval[0];
		right = interval[1];
	    }
	} // for
	
	// record last left and right values
	Console.WriteLine($"{left},{right}");
}

```
