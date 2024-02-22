---
title: "Challenge: Coin Change"
date: 2024-02-20
---

# Coin Change

```

public int Solution(int[] coins, int amount)
{
    // dp will hold the number of coins
    int[] dp = new int[amount + 1];

    // populate all elements of array with value amount + 1
    for (int i = 0; i <= dp.Length - 1; i++)
    {
        dp[i] = amount + 1;
    }

    // base case
    // represents 0 coins
    dp[0] = 0;

    // loop through coins
    foreach (int coin in coins)
    {
        // loop through dp[] array
        for (int amt = coin; amt <= amount; amt++)
        {
            Console.WriteLine($"dp[{amt}] = {Math.Min(dp[amt], dp[amt - coin] + 1)} --> {dp[amt]} or {dp[amt - coin] + 1}");
            // 1 - the coin count for this iteration
            // dp[amt] - contains the coin count
            // amt - value we are adding coins to
            dp[amt] = Math.Min(dp[amt], dp[amt - coin] + 1);
        }
        Console.WriteLine("");
    }
    int solution = dp[amount];
    Console.WriteLine($"{solution}");
    return solution;
}

```
