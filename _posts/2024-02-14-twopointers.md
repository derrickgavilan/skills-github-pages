# Coding Pattern: Two Pointer

```
static void TwoPointer_v2(int targetSum)
{
    int[] data = { 1, 2, 3, 7, 8, 9, 11, 22, 33 };

    // loop through array
    int i = 0;
    int leftIndex = 0;
    int rightIndex = data.Length - 1;

    while (i <= data.Length)
    {
        int sumElements = data[leftIndex] + data[rightIndex];
        if (sumElements == targetSum)
        {
            Console.WriteLine($"targetSum '{targetSum}' found in data[{leftIndex}]:{data[leftIndex]}, data[{rightIndex}]:{data[rightIndex]}");
            break;
        }
        else
        {
            // Move left or right index
            if (sumElements < targetSum)
            {
                leftIndex += 1;
            }
            else
            {
                rightIndex -= 1;
            }
        }
    }// while
}
```
