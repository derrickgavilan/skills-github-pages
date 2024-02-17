---
title: "Pattern: Cyclical Sort"
date: 2024-02-14
---


# Cyclical Sort

```
static void CyclicSort()
{
    // Set up the data
    int[] data = { 5, 4, 1, 2, 3 };

    int i = 0;
    while (i <= data.Length - 1)
    {
        // get the index of the element we are swapping
        int correctIndex = data[i] - 1;

        Console.WriteLine($"{data[correctIndex]} == {data[i]}?");

        // compare element values
        if (data[i] != data[correctIndex])
        {
            // swap element values
            // do not increment i

            int temp = data[i];
            data[i] = data[correctIndex];
            data[correctIndex] = temp;

            Console.WriteLine("swap");
            Console.WriteLine($"{data[correctIndex]} <-- {data[i]}\n");
        }
        else
        {
            // move to next element
            Console.WriteLine("move to next element\n");
            i++;
        }
    }

    Console.WriteLine("\nsort done.\n");

    for (int j = 0; j <= data.Length - 1; j++)
    {
        Console.WriteLine(data[j]);
    }
}
```
