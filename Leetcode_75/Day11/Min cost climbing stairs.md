# Min cost climbing stairs
- ## Question:
>You are given an integer array cost where cost[i] is the cost of ith step on a staircase. Once you pay the cost, you can either climb one or two steps.
>
>You can either start from the step with index 0, or the step with index 1.
>
>Return the minimum cost to reach the top of the floor.

- Example :

      Input: cost = [10,15,20]
      Output: 15
      Explanation: You will start at index 1.
      - Pay 15 and climb two steps to reach the top.
      The total cost is 15.
      
- ## Solution:
```cpp
class Solution {
public:
    int minCostClimbingStairs(vector<int>& cost) {
         int n = cost.size();
         vector<int> dp(n+1,-1);
        
         if(n<=1)return 0;
             
         dp[0] = 0;
	     dp[1] = 0;

	     for(int j=2;j<=n;j++){
		     dp[j] = min(cost[j-1] + dp[j-1], cost[j-2] + dp[j-2]);
	     }
	  return dp[n]; 
    }
};
```

## Tags
`Array` `Dynamic Programming`





