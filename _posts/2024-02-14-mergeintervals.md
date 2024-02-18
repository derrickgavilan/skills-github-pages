---
title: "Merge Intervals"
date: 2024-02-14
---

# Pattern: Merge Intervals

```
static void MergeIntervals()
{
    /*
    1. Loop through intervals
    2. Check if there is an overlap
    3. Merge intervals
    */

    // Set up the data
    int[][] intervals = new int[][]
    {
    new int[] {1,3},
    new int[] {5,10},
    new int[] {7,15},
    new int[] {18,30},
    new int[] {22,31},
    new int[] {23,32},
    new int[] {30,35},
    new int[] {37,40},
    };

    // NOTE: intervals must be sorted

    string[] newIntervals = new string[5];
    int newIntervalIndex = 0;

    // 1. Loop through intervals

    int ii = 0;
    while (ii <= intervals.Length - 1)
    {
        // get interval to start with
        int[] currRecord = intervals[ii];

        int newIntervalLeft = currRecord[0];
        int newIntervalRight = currRecord[1];

        // get the next inteval to compare
        int nextRecordIndex = ii + 1;
        for (int j = nextRecordIndex; j <= intervals.Length - 1; j++)
        {
            int[] nextRecord = intervals[j];

            Console.WriteLine($"Interval: {newIntervalLeft}, {newIntervalRight}");
            Console.WriteLine($"Merge with: {nextRecord[0]}, {nextRecord[1]}");

            bool hasOverlap = nextRecord[0] >= newIntervalLeft && nextRecord[0] <= newIntervalRight;

            Console.WriteLine($"{newIntervalLeft} > {nextRecord[0]} < {newIntervalRight} {hasOverlap}");

            if (hasOverlap)
            {
                newIntervalRight = (newIntervalRight >= nextRecord[1] ? newIntervalRight : nextRecord[1]);

                Console.WriteLine($"Overlap found. Update right side of interval.");
                Console.WriteLine($"Interval (NEW): {newIntervalLeft}, {newIntervalRight}");
                ii++;
            }
            else
            {
                // record interval
                newIntervals[newIntervalIndex] = $"{newIntervalLeft}, {newIntervalRight}";
                newIntervalIndex += 1;

                // move to next interval
                Console.WriteLine($"No Overlap. Start new interval.");
                break;
            }
        }

        Console.WriteLine("\n---\n");

        // move to next interval
        ii++;

        if (ii >= intervals.Length)
        {
            newIntervals[newIntervalIndex] = $"{newIntervalLeft}, {newIntervalRight}";
        }
    } //while

    for (int k = 0; k <= newIntervals.Length - 1; k++)
    {
        Console.WriteLine($"{newIntervals[k]}");
    }
}
```
