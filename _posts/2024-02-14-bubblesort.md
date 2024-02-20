---
title: "Pattern: Bubble Sort"
date: 2024-02-14
---

# Bubble Sort

```

static void BubbleSort()
{
  // data
    int[] data = { 5,4,3,2,1 };
    
    // loop 1
    for(int i=1; i<=data.Length; i++)
    {
      // loop 2
        for(int j=0; j<=(data.Length-1)-i; j++)
        {
            // display
            for(int ii=0; ii<=data.Length-1; ii++)
            {
              Console.Write(data[ii] + ",");
            }
            Console.WriteLine("");
            
            // compare and swap
            if(data[j] > data[j+1])
            {
              // swap
                int temp = data[j];
                data[j] = data[j+1];
                data[j+1] = temp;
                
                // display
                for(int ii=0; ii<=data.Length-1; ii++)
                {
                    Console.Write(data[ii] + ",");
                }
                Console.WriteLine("");
            }
        } // for 2
        Console.WriteLine(" ");
    } // for 1
    
    // display
    for(int i=0; i<=data.Length-1; i++)
    {
      Console.WriteLine(data[i]);
    }
}

```
