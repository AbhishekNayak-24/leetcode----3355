# leetcode----3355
Zero Array Transformation I
//code in java
class Solution {
    public boolean isZeroArray(int[] nums, int[][] queries) {
        int n = nums.length;
        int[] diff = new int[n + 1];

        for (int[] query : queries) {
            int left = query[0];
            int right = query[1];
            diff[left]++;
            diff[right + 1]--;
        }

        int current = 0;
        for (int i = 0; i < n; i++) {
            current += diff[i];
            if (nums[i] > current) {
                return false;
            }
        }

        return true;
    }
}
