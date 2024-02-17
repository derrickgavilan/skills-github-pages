# Pattern: Cyclical Sort

```
static void CyclicSort()
{
    int[] data = { 5, 4, 1, 2, 3 };
    int i = 0;
    while (i <= data.Length - 1)
    {
        // target index to compare
        int correctIndex = data[i] - 1;

        Console.WriteLine($"{data[correctIndex]} == {data[i]}?");

        if (data[i] != data[correctIndex])
        {
            // swap
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
