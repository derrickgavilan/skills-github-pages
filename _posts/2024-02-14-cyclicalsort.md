---
title: "Pattern: Cyclical Sort"
date: 2024-02-14
---


# Cyclical Sort

```

static void CyclicSort()
{
    // data
    int[] data = { 5, 4, 1, 2, 3 };	
    
    // loop
    int i=0;
    while(i <= data.Length-1)
    {
        // get compare index
        int compare = data[i] - 1;
        
        // compare
        if(data[i] != data[compare])
        {
            // swap
            int temp = data[i];
            data[i] = data[compare];
            data[compare] = temp;
        }
        else
        {
            // move to next element
            i++;
        }
    }
    
    // display
    for(int j=0; j<=data.Length-1; j++)
    {
        Console.WriteLine($"{data[j]}");
    }
}

```
