<h3>Second Largest Element In an array</h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/article/MTQ4NDk1">Article🚀</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/video/Mjc4NzQ%3D">Video🚀</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/second-largest3735">Problem🚀</a></h3>

```java
class Solution {
    public int getSecondLargest(int[] arr) {
        // Code Her
        int len = arr.length;
        Arrays.sort(arr);
       
        for(int i = arr.length - 2;i>=0;i--){
            if(arr[i] != arr[len - 1]){
                return arr[i];
            }
        }
        return -1;       
    }
}
```

<h3>Second Largest Element In an array</h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/article/MTIzNDkz">Article</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/video/Mjc4OTY%3D">Video</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/move-all-zeroes-to-end-of-array0751">Problem🚀</a></h3>

```java
class Solution {
    void pushZerosToEnd(int[] arr) {
        // code here
        int count = 0;
        for(int i = 0;i<arr.length;i++){
            if(arr[i] != 0){
                int temp = arr[i];
                arr[i] = arr[count];
                arr[count] = temp;
                count++;
            }
        }
    }
}

```

<h3>Array Reverse</h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/article/MjU2Nw%3D%3D">Article🚀</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/video/Mjc4OTc%3D">Video🚀</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/reverse-an-array">Problem🚀</a></h3>

```java
class Solution {
    public void reverseArray(int arr[]) {
        // code here
        int left = 0;
        int right = arr.length - 1;
        while (left < right) {
            
            // Swap the elements at left and right position
            int temp = arr[left];
            arr[left] = arr[right];
            arr[right] = temp;

            // Increment the left pointer
            left++;

            // decrement the right pointer
            right--;
        }
    }
}
```

<h3>Rotate Array</h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/article/MjM5OA%3D%3D">Article🚀</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/video/Mjc4OTg%3D">Video🚀</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/rotate-array-by-n-elements-1587115621">Problem🚀</a></h3>

```java

class Solution {
    // Function to rotate an array by d elements in counter-clockwise direction.
    static void rotateArr(int arr[], int d) {
        int len = arr.length; //length of array;
    
        d = d % len; // d need to be greater than size of array
        
        // reverse function
        
        
        reverse(arr,0,d - 1); // reverse element by d 
        
        reverse(arr,d,len - 1); //reverse elements by remainging d places
        
        reverse(arr,0,len - 1); //reverse the entire array
        
        
    }
    
    
    // reverse an array
    static void reverse(int[] arr,int left,int right)
    {
        while(left < right)
        {
            int temp = arr[left];
            arr[left] = arr[right];
            arr[right] = temp;
            left++;
            right--;
        }
    }
}}
```
<!-- Problem 5 -->
<h3>Next Permutation</h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/article/ODc2MzQw">Article🚀</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/video/MjgwMjI%3D">Video🚀</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/next-permutation5226">Problem🚀</a></h3>

```java
class Solution {
    void nextPermutation(int[] arr)
    {
        // code here
    
        int n = arr.length;

        // Find the pivot index
        int pivot = -1;
        for (int i = n - 2; i >= 0; i--) {
            if (arr[i] < arr[i + 1]) {
                pivot = i;
                break;
            }
        }

        // If pivot point does not exist, reverse the whole array
        if (pivot == -1) {
            reverse(arr, 0, n - 1);
            return ;
        }

        // Find the element from the right that is greater than pivot
        for (int i = n - 1; i > pivot; i--) {
            if (arr[i] > arr[pivot]) {
                swap(arr, i, pivot);
                break;
            }
        }

        // Reverse the elements from pivot + 1 to the end
        reverse(arr, pivot + 1, n - 1);
    }
    // Helper method to reverse array
    private static void reverse(int[] arr, int start, int end) {
        while (start < end) {
            swap(arr, start++, end--);
        }
    }

    // Helper method to swap two elements
    private static void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
    
}
```

<!-- Problem 6-->
<h3>Majority Element II</h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/article/NDkxMDM3">Article🚀</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/video/MjgwNDE%3D">Video🚀</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/majority-vote">Problem🚀</a></h3>

```js
class Solution {
    // Function to find the majority elements in the array
    public List<Integer> findMajority(int[] nums) {
        // Your code goes here.
         int num1 = -1;
        int num2 = -1;
        int f1 = 0;
        int f2 = 0;
        for(int num : nums){
            if(num == num1){
                ++f1;
            }
            else if(num == num2){
                ++f2;
            }
            else if(f1 == 0){
                num1 = num;
                ++f1;
            }
            else if(f2 == 0){
                num2 = num;
                ++f2;
            }
            else{
                --f1;
                --f2;
            }
        }
        
        f1 = 0;
        f2 = 0;
        
        for(int num : nums){
            if(num == num1){
                ++f1;
            }
            else if(num == num2){
                ++f2;
            }
        }
        
        int n = nums.length;
        List<Integer> res = new ArrayList<>();
        if(f1 > n / 3){
            res.add(num1);
        }
        
        if(f2 > n / 3){
            res.add(num2);
        }
        
        if(res.size() == 2){
            if(res.get(0) > res.get(1)){
                int temp = res.get(0);
                res.set(0, res.get(1));
                res.set(1, temp);
            }
        }
        
        return res;
        
    }
}
```
<!-- Solution 7-->
<h3>Stock buy and sell </h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/article/MTE2Mjgz">Article🚀</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/video/MjgwNDA%3D">Video🚀</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/stock-buy-and-sell2615">Problem🚀</a></h3>

```js
class Solution {
    public int maximumProfit(int prices[]) {
        // code here
        int n = prices.length;
        int maxProfit = 0;
        
        for (int i = 1; i < n; i++) {

            if (prices[i] > prices[i - 1]) {
                maxProfit += prices[i] - prices[i - 1];
            }
        }
        
        return maxProfit;
    }
}
```
<!-- solution 8 -->
<h3>Stock buy and sell </h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/article/NTExNTc0">Article🚀</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/video/MjgwNzc%3D">Video🚀</a></h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/buy-stock-2">Problem🚀</a></h3>

```java
class Solution {
    public int maximumProfit(int prices[]) {
        if (prices == null || prices.length <= 1) {
            return 0;
        }

        int minPrice = Integer.MAX_VALUE;  // Initialize minPrice to a very large value
        int maxProfit = 0;  // Initialize maxProfit to 0

        // Traverse through the prices array
        for (int i = 0; i < prices.length; i++) {
            // Update the minimum price encountered so far
            if (prices[i] < minPrice) {
                minPrice = prices[i];
            }
            // Calculate profit if we sold at the current price
            int profit = prices[i] - minPrice;
            // Update the maximum profit
            if (profit > maxProfit) {
                maxProfit = profit;
            }
        }

        // Return the maximum profit that can be made
        return maxProfit;
    }
}
```

<!-- Solution 9-->
```js
int n = arr.length;
        Arrays.sort(arr);

        // If we increase all heights by k or decrease all
        // heights by k, the result will be arr[n - 1] - arr[0]
        int res = arr[n - 1] - arr[0];

        // For all indices i, increment arr[0...i-1] by k and
        // decrement arr[i...n-1] by k
        for (int i = 1; i < arr.length; i++) {

            // Impossible to decrement height of ith tower by k, 
            // continue to the next tower
            if (arr[i] - k < 0)
                continue;

            // Minimum height after modification
            int minH = Math.min(arr[0] + k, arr[i] - k);

            // Maximum height after modification
            int maxH = Math.max(arr[i - 1] + k, arr[n - 1] - k);

            // Store the minimum difference as result
            res = Math.min(res, maxH - minH);
        }
        return res;
```

<!-- Solution 10-->
```java
class Solution {

    // arr: input array
    // Function to find the sum of contiguous subarray with maximum sum.
    int maxSubarraySum(int[] arr) {

        int maxSoFar = Integer.MIN_VALUE;  // This will store the maximum sum found
        int maxEndingHere = 0;             // This will store the sum of the subarray ending here

        // Traverse the array
        for (int i = 0; i < arr.length; i++) {
            // Update maxEndingHere by including the current element
            maxEndingHere = Math.max(arr[i], maxEndingHere + arr[i]);

            // Update maxSoFar if maxEndingHere is greater
            maxSoFar = Math.max(maxSoFar, maxEndingHere);
        }

        return maxSoFar;

    }
}
```
