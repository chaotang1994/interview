# interviewBNY

283. Move Zeroes
Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.
Input: nums = [0,1,0,3,12]
Output: [1,3,12,0,0]
Input: nums = [0]
Output: [0]

class Solution {
    public void moveZeroes(int[] nums) {
        int keyMark = 0;
        for(int i=0; i< nums.length; i++){
            if(nums[i]!=0){
                nums[keyMark++] = nums[i];
            }
        }
        for(int i=keyMark; i<nums.length; i++){
            nums[i]=0;
        }
    }
}



35. Search Insert Position

Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.

You must write an algorithm with O(log n) runtime complexity.

Example 1:

Input: nums = [1,3,5,6], target = 5
Output: 2
Example 2:

Input: nums = [1,3,5,6], target = 2
Output: 1
Example 3:

Input: nums = [1,3,5,6], target = 7
Output: 4

class Solution {
    public int searchInsert(int[] nums, int target) {
        int lo=0 , hi=nums.length-1;
        
        while(lo<=hi){
            int mid = lo + (hi-lo)/2;
            
            if(nums[mid] == target) return mid;
            else if(nums[mid] < target){
                lo = mid+1;
            }
            else{
                hi = mid-1;
            }
        }
        return lo;
    }
}
