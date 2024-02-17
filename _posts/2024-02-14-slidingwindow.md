---
title: "Sliding Window"
date: 2024-02-14
---


# Pattern: Sliding Window

```
static void SlidingWindow_BruteForce(int windowSize)
{
    int[] data = { 5, 7, 1, 4, 3, 6, 2, 9, 2 };
    int largestSum = 0;

    // travers the array 1 by 1
    // make sure to subtract the windowSize from the length of the array.
    for (int i = 0; i <= data.Length - windowSize; i++)
    {
        int windowSum = 0;
        // loop through the array
        // start from i and loop N number of times (windowSize)
        for (int ii = i; ii < i + windowSize; ii++)
        {
            // sum up values
            Console.Write(data[ii] + " ");
            windowSum += data[ii];
        }

        Console.Write($" = {windowSum}");
        Console.WriteLine("");

        largestSum = (windowSum > largestSum) ? windowSum : largestSum;
    }

    Console.WriteLine($"Largest Sum: {largestSum}");
}

static void SlidingWindow_OneLoop(int windowSize)
{
    int[] data = { 5, 7, 1, 4, 3, 6, 2, 9, 2 };
    int largestSum = 0;


    // get sum of first window
    int windowSum = 0;
    for (int i = 0; i <= windowSize - 1; i++)
    {
        windowSum += data[i];
    }

    Console.WriteLine(windowSum);

    // loop through array
    // start on 2nd element
    for (int j = 1; j <= data.Length - windowSize; j++)
    {
        // remove value in 1st element
        windowSum -= data[j - 1];

        // add value from next element
        windowSum += data[j + windowSize - 1];

        Console.WriteLine(windowSum);

        // set largest sum
        largestSum = (windowSum > largestSum) ? windowSum : largestSum;
    }

    Console.WriteLine($"Largest Sum: {largestSum}");
}
```
