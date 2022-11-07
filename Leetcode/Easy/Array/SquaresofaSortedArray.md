Given an integer array nums sorted in non-decreasing order, return an array of the squares of each number sorted in non-decreasing order.

Example 1:

Input: nums = [-4,-1,0,3,10]
Output: [0,1,9,16,100]
Explanation: After squaring, the array becomes [16,1,0,9,100].
After sorting, it becomes [0,1,9,16,100].
Example 2:

Input: nums = [-7,-3,2,3,11]
Output: [4,9,9,49,121]

Constraints:

1 <= nums.length <= 104
-104 <= nums[i] <= 104
nums is sorted in non-decreasing order.

```java
class Solution {
    public int[] sortedSquares(int[] nums) {
        int[] result = new int[nums.length];
        int temp=0;
        int n = nums.length;
        for(int i=0; i<nums.length;i++) {
            result[i] = nums[i]*nums[i];
        };

        while(n != 0) {
            for(int j=0; j<result.length;j++){
                if(j == result.length-1) break;
                 if(result[j]>result[j+1]) {
                     temp = result[j];
                    result[j] = result[j+1];
                    result[j+1] = temp;
               }
            }
            n--;
        }
        return result;
    }
}
```
