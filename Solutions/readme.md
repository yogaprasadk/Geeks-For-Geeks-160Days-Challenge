<h1>Array</h1>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/second-largest3735">Problem 1</a></h3>

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
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/move-all-zeroes-to-end-of-array0751">Problem 2</a></h3>

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
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/reverse-an-array">Problem 3</a></h3>

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

<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/rotate-array-by-n-elements-1587115621">Problem 4</a></h3>

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
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/next-permutation5226">Problem 5</a></h3>

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
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/majority-vote">Problem 6</a></h3>

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
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/stock-buy-and-sell2615">Problem 7</a></h3>

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
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/buy-stock-2">Problem 8</a></h3>

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

<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/minimize-the-heights3351">Problem 9</a></h3>
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
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/kadanes-algorithm-1587115620">Problem 10</a></h3>

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
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/maximum-product-subarray3604">Problem 11</a></h3>

```java
lass Solution {
    // Function to find maximum product subarray
    int maxProduct(int[] arr) {
         if (arr == null || arr.length == 0) return 0;

        int max_product = arr[0];  // Initialize max_product to the first element
        int min_product = arr[0];  // Initialize min_product to the first element
        int result = arr[0];       // To store the final result

        // Traverse through the array starting from the second element
        for (int i = 1; i < arr.length; i++) {
            // If the current element is negative, swap max_product and min_product
            if (arr[i] < 0) {
                int temp = max_product;
                max_product = min_product;
                min_product = temp;
            }

            // Update max_product and min_product
            max_product = Math.max(arr[i], max_product * arr[i]);
            min_product = Math.min(arr[i], min_product * arr[i]);

            // Update the result with the maximum product found so far
            result = Math.max(result, max_product);
        }

        return result;
    }
}
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/max-circular-subarray-sum-1587115620">Problem 12</a>
</h3>

```js


class Solution {

    // a: input array
    // n: size of array
    // Function to find maximum circular subarray sum.
    public int circularSubarraySum(int arr[]) {
        int n = arr.length;
        int suffixSum = arr[n - 1];

        // maxSuffix array to store the value of 
        // maximum suffix occurred so far.
        int[] maxSuffix = new int[n + 1];
        maxSuffix[n - 1] = arr[n - 1];

        for(int i = n - 2; i >= 0; i--) {
            suffixSum = suffixSum + arr[i];
            maxSuffix[i] = Math.max(maxSuffix[i + 1], suffixSum);
        }

        // circularSum is Maximum sum of circular subarray
        int circularSum = arr[0];

        // normalSum is Maximum sum subarray considering 
        // the array is non-circular
        int normalSum = arr[0];

        int currSum = 0;
        int prefix = 0;

        for(int i = 0; i < n; i++) {
            
            // Kadane's algorithm
            currSum = Math.max(currSum + arr[i], arr[i]);
            normalSum = Math.max(normalSum, currSum);
          
            // Calculating maximum Circular Sum
            prefix = prefix + arr[i];
            circularSum = Math.max(circularSum, prefix + maxSuffix[i + 1]);
        }

        return Math.max(circularSum, normalSum);

        // Your code here
    }
}
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/smallest-positive-missing-number-1587115621">Problem 13</a></h3>

```js
class Solution {
    // Function to find the smallest positive number missing from the array.
    public int missingNumber(int[] arr) {
        // Your code here
        int n = arr.length;

        // To mark the occurrence of elements
        boolean[] vis = new boolean[n];
        for (int i = 0; i < n; i++) {

            // if element is in range from 1 to n
            // then mark it as visited
            if (arr[i] > 0 && arr[i] <= n)
                vis[arr[i] - 1] = true;
        }

        // Find the first element which is unvisited
        // in the original array
        for (int i = 1; i <= n; i++) {
            if (!vis[i - 1]) {
                return i;
            }
        }

        // if all elements from 1 to n are visited
        // then n+1 will be first positive missing number
        return n + 1;
    }
}
```

<h1>String</h1>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/string-gfg-160/problem/implement-atoi">Problem 1</a></h3>

```java
class Solution {
    public int myAtoi(String s) {
        // Your code here
         int sign = 1, res = 0, idx = 0;

        // Ignore leading whitespaces
        while (idx < s.length() && s.charAt(idx) == ' ') {
            idx++;
        }

        // Store the sign of number
        if (idx < s.length() && (s.charAt(idx) == '-' 
                                 || s.charAt(idx) == '+')) {
            if (s.charAt(idx++) == '-') {
                sign = -1;
            }
        }

        // Construct the number digit by digit
        while (idx < s.length() && s.charAt(idx) >= '0' 
                                       && s.charAt(idx) <= '9') {
            
            // Handling overflow/underflow test case
            if (res > Integer.MAX_VALUE / 10 || 
                   (res == Integer.MAX_VALUE / 10 && s.charAt(idx) - '0' > 7)) {
                return sign == 1 ? Integer.MAX_VALUE : Integer.MIN_VALUE;
            }
          
            // Append current digit to the result
            res = 10 * res + (s.charAt(idx++) - '0');
        }
        return res * sign;
    }
}
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/string-gfg-160/problem/add-binary-strings3805">Problem 2</a></h3>

```js
lass Solution {
    static String trimLeadingZeros(String s) {

        // Find the position of the first '1'
        int firstOne = s.indexOf('1');
        return (firstOne == -1) ? "0"
                                : s.substring(firstOne);
    }
    
    public String addBinary(String s1, String s2) {
        // code here
        s1 = trimLeadingZeros(s1);
        s2 = trimLeadingZeros(s2);
        
        int n = s1.length();
        int m = s2.length();

        // Swap the strings if s1 is of smaller length
        if (n < m) {
            return addBinary(s2, s1);
        }

        int j = m - 1;
        int carry = 0;
        StringBuilder result = new StringBuilder();

        // Traverse both strings from the end
        for (int i = n - 1; i >= 0; i--) {

            // Current bit of s1
            int bit1 = s1.charAt(i) - '0';
            int sum = bit1 + carry;

            // If there are remaining bits in s2, add them
            // to the sum
            if (j >= 0) {

                // Current bit of s2
                int bit2 = s2.charAt(j) - '0';
                sum += bit2;
                j--;
            }

            // Calculate the result bit and update carry
            int bit = sum % 2;
            carry = sum / 2;

            // Update the current bit in result
            result.append((char)(bit + '0'));
        }

        // If there's any carry left, update the result
        if (carry > 0)
            result.append('1');

        return result.reverse().toString();
    }
}
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/string-gfg-160/problem/anagram-1587115620">Problem 3</a></h3>

```java
class Solution {
    // Function is to check whether two strings are anagram of each other or not.
    static final int MAX_CHAR = 26;
    public static boolean areAnagrams(String s1, String s2) {

        // Your code here
        int[] freq = new int[MAX_CHAR];

        // Count frequency of each character in string s1
        for (int i = 0; i < s1.length(); i++)
            freq[s1.charAt(i) - 'a']++;

        // Count frequency of each character in string s2
        for (int i = 0; i < s2.length(); i++)
            freq[s2.charAt(i) - 'a']--;

        // Check if all frequencies are zero
        for (int count : freq) {
            if (count != 0)
                return false;
        }

        return true;
    }
}
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/string-gfg-160/problem/non-repeating-character-1587115620">Problem 4</a></h3>

```java
class Solution {
    // Function to find the first non-repeating character in a string
    static final int MAX_CHAR = 26;
    static char nonRepeatingChar(String s) {
        // Your code here
        int[] freq = new int[MAX_CHAR];

        // Count the frequency of all characters
        for (char c : s.toCharArray()) 
            freq[c - 'a']++;

        // Find the first character with frequency 1
        for (int i = 0; i < s.length(); ++i) {
            if (freq[s.charAt(i) - 'a'] == 1)
                return s.charAt(i);
        }
    
        // If no character with a frequency of 1 is 
        // found, then return '$'
        return '$';
    }
}
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/string-gfg-160/problem/search-pattern0205">Problem 5</a></h3>

```java
class Solution {
    
    static void constructLps(String pat, int[] lps) {
        
        // len stores the length of longest prefix which 
        // is also a suffix for the previous index
        int len = 0;

        // lps[0] is always 0
        lps[0] = 0;

        int i = 1;
        while (i < pat.length()) {
            
            // If characters match, increment the size of lps
            if (pat.charAt(i) == pat.charAt(len)) {
                len++;
                lps[i] = len;
                i++;
            }
            
            // If there is a mismatch
            else {
                if (len != 0) {
                    
                    // Update len to the previous lps value 
                    // to avoid redundant comparisons
                    len = lps[len - 1];
                } 
                else {
                    
                    // If no matching prefix found, set lps[i] to 0
                    lps[i] = 0;
                    i++;
                }
            }
        }
    }
    ArrayList<Integer> search(String pat, String txt) {
        // your code here
        
        int n = txt.length();
        int m = pat.length();

        int[] lps = new int[m];
        ArrayList<Integer> res = new ArrayList<>();

        constructLps(pat, lps);

        // Pointers i and j, for traversing 
        // the text and pattern
        int i = 0;
        int j = 0;

        while (i < n) {
            // If characters match, move both pointers forward
            if (txt.charAt(i) == pat.charAt(j)) {
                i++;
                j++;

                // If the entire pattern is matched 
                // store the start index in result
                if (j == m) {
                    res.add(i - j);
                    
                    // Use LPS of previous index to 
                    // skip unnecessary comparisons
                    j = lps[j - 1];
                }
            }
            
            // If there is a mismatch
            else {
                
                // Use lps value of previous index
                // to avoid redundant comparisons
                if (j != 0)
                    j = lps[j - 1];
                else
                    i++;
            }
        }
        return res; 
        
    }
}
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/string-gfg-160/problem/minimum-characters-to-be-added-at-front-to-make-string-palindrome">Problem 6</a></h3>

```js
class Solution {

    static int[] computeLPSArray(String pat) {
        int n = pat.length();
        int[] lps = new int[n];

        // lps[0] is always 0
        lps[0] = 0;
        int len = 0;

        // loop calculates lps[i] for i = 1 to n-1
        int i = 1;
        while (i < n) {

            // If the characters match, increment len
            // and set lps[i]
            if (pat.charAt(i) == pat.charAt(len)) {
                len++;
                lps[i] = len;
                i++;
            }

            // If there is a mismatch
            else {

                // If len is not zero, update len to
                // the last known prefix length
                if (len != 0) {
                    len = lps[len - 1];
                }

                // No prefix matches, set lps[i] to 0
                else {
                    lps[i] = 0;
                    i++;
                }
            }
        }
        return lps;
    }

    // Method returns minimum character to be added at
    // front to make string palindrome
    static int minChar(String s) {
        int n = s.length();
        String rev
            = new StringBuilder(s).reverse().toString();

        // Get concatenation of string, special character
        // and reverse string
        s = s + "$" + rev;

        // Get LPS array of this concatenated string
        int[] lps = computeLPSArray(s);

        // By subtracting last entry of lps array from
        // string length, we will get our result
        return (n - lps[lps.length - 1]);
    }
}
```

<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/string-gfg-160/problem/check-if-strings-are-rotations-of-each-other-or-not-1587115620">Problem 7</a></h3>

```java
class Solution {
    // Function to check if two strings are rotations of each other or not.
     static int[] computeLPSArray(String pat) {
        int n = pat.length();
        int[] lps = new int[n];
      
        // Length of the previous longest prefix suffix
        int len = 0;

        // lps[0] is always 0
        lps[0] = 0;

        // loop calculates lps[i] for i = 1 to n-1
        int i = 1;
        while (i < n) {
          
            // If the characters match, increment len 
            // and extend the matching prefix
            if (pat.charAt(i) == pat.charAt(len)) {
                len++;
                lps[i] = len;
                i++;
            }
          
            // If there is a mismatch
            else {
              
                // If len is not zero, update len to
                // last known prefix length
                if (len != 0) {
                    len = lps[len - 1];
                }
              
                // No prefix matches, set lps[i] = 0
                // and move to the next character
                else {
                    lps[i] = 0;
                    i++;
                }
            }
        }
        return lps;
    }
    public static boolean areRotations(String s1, String s2) {
        // Your code here
         String txt = s1 + s1;
        String pat = s2;
        
        // search the pattern string s2 in the concatenation string 
        int n = txt.length();
        int m = pat.length();

        // Create lps[] that will hold the longest prefix suffix
        // values for pattern
        int[] lps = computeLPSArray(pat);
      
        int i = 0; 
        int j = 0;
        while (i < n) {
            if (pat.charAt(j) == txt.charAt(i)) {
                j++;
                i++;
            }

            if (j == m) {
                return true;
            }

            // Mismatch after j matches
            else if (i < n && pat.charAt(j) != txt.charAt(i)) {

                // Do not match lps[0..lps[j-1]] characters,
                // they will match anyway
                if (j != 0)
                    j = lps[j - 1];
                else
                    i = i + 1;
            }
        }
        return false;
    }
}
```
<h1>Sorting</h1>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/sorting-gfg-160/problem/sort-an-array-of-0s-1s-and-2s4231">Problem 1</a></h3>

```java
class Solution {
    // Function to sort an array of 0s, 1s, and 2s
    public void sort012(int[] arr) {
        // code here
         int n = arr.length;
        int lo = 0;
        int hi = n - 1;
        int mid = 0, temp = 0;

        // Iterate till all the elements are sorted
        while (mid <= hi) 
        {
            if (arr[mid] == 0) {
                swap(arr, mid, lo);
                lo++;
                mid++;
            }
            else if (arr[mid] == 1) {
                mid++;
            }
            else {
                swap(arr, mid, hi);
                hi--;
            }
        }
    }
    
    static void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
}
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/sorting-gfg-160/problem/find-h-index--165609">Problem 2</a></h3>

```java
class Solution {
    // Function to find hIndex
    public int hIndex(int[] citations) {
        // code here
        int n = citations.length;
        int[] freq = new int[n + 1];

        // Count the frequency of citations
        for (int i = 0; i < n; i++) {
            if (citations[i] >= n)
                freq[n] += 1;
            else
                freq[citations[i]] += 1;
        }

        int idx = n;
        
        // Variable to keep track of the count of papers
        // having at least idx citations
        int s = freq[n]; 
        while (s < idx) {
            idx--;
            s += freq[idx];
        }
        
        // Return the largest index for which the count of 
        // papers with at least idx citations becomes >= idx
        return idx;
    }
}
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/sorting-gfg-160/problem/inversion-of-array-1587115620">Problem 3</a></h3>

```java
 int n = arr.length; 
        int invCount = 0;  

        for (int i = 0; i < n - 1; i++) {
            for (int j = i + 1; j < n; j++) {
              
                // If the current element is greater than the next,
                // increment the count
                if (arr[i] > arr[j])
                    invCount++;
            }
        }
        return invCount; 
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/sorting-gfg-160/problem/overlapping-intervals--170633">Problem 4</a></h3>

```java
class Solution {
    public List<int[]> mergeOverlap(int[][] arr) {
        // Code here // Code here
        Arrays.sort(arr, (a, b) -> Integer.compare(a[0], b[0]));

        // Step 2: Initialize a list to hold the merged intervals
        List<int[]> merged = new ArrayList<>();

        // Step 3: Iterate through the sorted intervals
        for (int[] interval : arr) {
            // If merged is empty or no overlap, simply add the interval
            if (merged.isEmpty() || merged.get(merged.size() - 1)[1] < interval[0]) {
                merged.add(interval);
            } else {
                // There is overlap, merge the current interval with the last merged one
                int[] lastInterval = merged.get(merged.size() - 1);
                lastInterval[1] = Math.max(lastInterval[1], interval[1]);
            }
        }

        // Step 4: Return the merged intervals
        return merged;
    }
}
```

<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/sorting-gfg-160/problem/insert-interval-1666733333">Problem 5</a></h3>

```java
class Solution {
    static ArrayList<int[]> insertInterval(int[][] intervals, int[] newInterval) {
        // code here
        ArrayList<int[]> result = new ArrayList<>();
        
        int i = 0;
        int n = intervals.length;

        // 1. Add all intervals that come before newInterval (no overlap).
        while (i < n && intervals[i][1] < newInterval[0]) {
            result.add(intervals[i]);
            i++;
        }

        // 2. Merge all overlapping intervals with newInterval.
        while (i < n && intervals[i][0] <= newInterval[1]) {
            newInterval[0] = Math.min(newInterval[0], intervals[i][0]);
            newInterval[1] = Math.max(newInterval[1], intervals[i][1]);
            i++;
        }
        
        // Add the merged newInterval.
        result.add(newInterval);

        // 3. Add the remaining intervals that come after newInterval.
        while (i < n) {
            result.add(intervals[i]);
            i++;
        }

        return result;
    }
}
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/sorting-gfg-160/problem/non-overlapping-intervals">Problem 6</a></h3>

```java
class Solution {
    static int minRemoval(int intervals[][]) {
        // code here
        Arrays.sort(intervals, (a, b) -> a[1] - b[1]);
        
        // Step 2: Initialize variables
        int end = intervals[0][1];  // End of the last added interval
        int removals = 0;            // Number of intervals to remove
        
        // Step 3: Iterate through the intervals starting from the second one
        for (int i = 1; i < intervals.length; i++) {
            // If the current interval overlaps with the last added interval
            if (intervals[i][0] < end) {
                removals++;  // We need to remove the current interval
            } else {
                end = intervals[i][1];  // Update the last selected interval's end
            }
        }
        
        // Step 4: Return the minimum number of removals
        return removals;
    }
}
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/sorting-gfg-160/problem/merge-two-sorted-arrays-1587115620">Problem 7</a></h3>

```java
class Solution {
    // Function to merge the arrays.
    public void mergeArrays(int a[], int b[]) {
        // code here
        int n = a.length;
        int m = b.length;
        int gap = (n + m + 1) / 2;

        while (gap > 0) {
            int i = 0, j = gap;

            while (j < n + m) {
              
                // If both pointers are in the first array a[]
                if (j < n && a[i] > a[j]) {
                    int temp = a[i];
                    a[i] = a[j];
                    a[j] = temp;
                } 
              
                // If first pointer is in a[] and 
                // the second pointer is in b[]
                else if (i < n && j >= n && a[i] > b[j - n]) {
                    int temp = a[i];
                    a[i] = b[j - n];
                    b[j - n] = temp;
                } 
              
                // Both pointers are in the second array b
                else if (i >= n && b[i - n] > b[j - n]) {
                    int temp = b[i - n];
                    b[i - n] = b[j - n];
                    b[j - n] = temp;
                }
                i++;
                j++;
            }

            // After operating for gap of 1 break the loop
            if (gap == 1) break;

            // Calculate the next gap
            gap = (gap + 1) / 2;
        }
        // The arrays a[] and b[] are now merged
    }
}

```

<h1>Searching</h1>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/searching-gfg-160/problem/number-of-occurrence2259">Problem 1</a></h3>

```java
class Solution {
    int countFreq(int[] arr, int target) {
        // code here
        int count = 0;
        for (int i = 0;i<arr.length;i++){
            if(arr[i] == target){
                count++;
            }
        }
        return count;
    }
}
```
<h3><a href="https://www.geeksforgeeks.org/find-minimum-element-in-a-sorted-and-rotated-array/">Problem 2</a></h3>

```js

class Solution {
    public int findMin(int[] arr) {
        // complete the function here
        int lo = 0, hi = arr.length - 1;

        while (lo < hi) {
          
            // The current subarray is already sorted, 
            // the minimum is at the low index
            if (arr[lo] < arr[hi])        
                return arr[lo];
               
            // We reach here when we have at least
            // two elements and the current subarray
            // is rotated
          
            int mid = (lo + hi) / 2;

            // The right half is not sorted. So 
            // the minimum element must be in the
            // right half.
            if (arr[mid] > arr[hi])
                lo = mid + 1;
          
            // The right half is sorted. Note that in 
            // this case, we do not change high to mid - 1
            // but keep it to mid. As the mid element
            // itself can be the smallest
            else
                hi = mid;
        }

        return arr[lo]; 
    }
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/searching-gfg-160/problem/search-in-a-rotated-array4618">Problem 3</a></h3>

```js
class Solution {
    int search(int[] arr, int key) {
        // Complete this function
        int left = 0;
        int right = arr.length - 1;
        
        while (left <= right) {
            int mid = left + (right - left) / 2;

            // Check if mid is the key
            if (arr[mid] == key) {
                return mid;
            }

            // Left half is sorted
            if (arr[left] <= arr[mid]) {
                // Check if key lies within the left half
                if (key >= arr[left] && key < arr[mid]) {
                    right = mid - 1; // Narrow down to the left half
                } else {
                    left = mid + 1; // Narrow down to the right half
                }
            }
            // Right half is sorted
            else {
                // Check if key lies within the right half
                if (key > arr[mid] && key <= arr[right]) {
                    left = mid + 1; // Narrow down to the right half
                } else {
                    right = mid - 1; // Narrow down to the left half
                }
            }
        }

        // If the key is not found
        return -1;
    }
}
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/searching-gfg-160/problem/peak-element">Problem 4</h3>

```java

class Solution {

    public int peakElement(int[] arr) {
        // code here
        int low = 0;
        int high = arr.length - 1;

        while (low <= high) {
            int mid = low + (high - low) / 2;

            // Check if arr[mid] is a peak element
            if ((mid == 0 || arr[mid - 1] <= arr[mid]) && (mid == arr.length - 1 || arr[mid + 1] <= arr[mid])) {
                return mid;
            }
            // If the left neighbor is greater, the peak lies on the left half
            else if (mid > 0 && arr[mid - 1] > arr[mid]) {
                high = mid - 1;
            }
            // If the right neighbor is greater, the peak lies on the right half
            else {
                low = mid + 1;
            }
        }
        return -1;
    }
}
```

<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/searching-gfg-160/problem/k-th-element-of-two-sorted-array1317"></a>Problem 5</h3>

```java
if (a.length > b.length) {
            return kthElement(b, a, k);
        }
        
        int n1 = a.length, n2 = b.length;
        int low = Math.max(0, k - n2), high = Math.min(k, n1);
        
        while (low <= high) {
            int cut1 = (low + high) / 2; // Elements taken from a
            int cut2 = k - cut1;         // Elements taken from b
            
            // Handle edges of the arrays
            int left1 = (cut1 == 0) ? Integer.MIN_VALUE : a[cut1 - 1];
            int left2 = (cut2 == 0) ? Integer.MIN_VALUE : b[cut2 - 1];
            int right1 = (cut1 == n1) ? Integer.MAX_VALUE : a[cut1];
            int right2 = (cut2 == n2) ? Integer.MAX_VALUE : b[cut2];
            
            // Valid partition
            if (left1 <= right2 && left2 <= right1) {
                return Math.max(left1, left2);
            } else if (left1 > right2) {
                high = cut1 - 1; // Reduce elements from a
            } else {
                low = cut1 + 1; // Increase elements from a
            }
        }
        
        throw new IllegalArgumentException("Invalid input");
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/searching-gfg-160/problem/aggressive-cows">Problem 6</a>

```java
class Solution {
    
    public static int aggressiveCows(int[] stalls, int k) {
        Arrays.sort(stalls); // Step 1: Sort the stall positions
        
        int low = 1; // Minimum possible distance
        int high = stalls[stalls.length - 1] - stalls[0]; // Maximum possible distance
        int result = 0;
        
        // Step 2: Binary Search to find the maximum minimum distance
        while (low <= high) {
            int mid = low + (high - low) / 2; // Calculate the mid distance
            
            if (canPlaceCows(stalls, k, mid)) {
                result = mid;  // Update result if placement is possible
                low = mid + 1; // Try for a larger minimum distance
            } else {
                high = mid - 1; // Try for a smaller minimum distance
            }
        }
        
        return result;
    }
    
    private static boolean canPlaceCows(int[] stalls, int k, int distance) 
    {
        int cowsPlaced = 1; // Place the first cow in the first stall
        int lastPosition = stalls[0];
        
        for (int i = 1; i < stalls.length; i++) {
            if (stalls[i] - lastPosition >= distance) {
                cowsPlaced++; // Place the next cow
                lastPosition = stalls[i]; // Update the last position
            }
            
            if (cowsPlaced == k) {
                return true; // All cows have been placed successfully
            }
        }
        
        return false; // Not enough cows placed
    }

```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/searching-gfg-160/problem/allocate-minimum-number-of-pages0937">Problem 7</a></h3>

```js

class Solution {
    public static int findPages(int[] arr, int k) {
        // code here
        if (arr.length < k) {
            return -1;
        }

        // Calculate the sum of pages and maximum pages
        int sum = 0;
        int maxPages = 0;
        for (int i = 0; i < arr.length; i++) {
            sum += arr[i];
            maxPages = Math.max(maxPages, arr[i]);
        }

        // Binary search to find the minimum possible maximum pages
        int low = maxPages, high = sum, result = -1;
        
        while (low <= high) {
            int mid = low + (high - low) / 2;

            // Check if it's possible to allocate books such that no student gets more than `mid` pages
            if (isPossible(arr, k, mid)) {
                result = mid;  // If it's possible, try to minimize the result
                high = mid - 1;  // Try for smaller maximum pages
            } else {
                low = mid + 1;  // Increase the maximum pages
            }
        }
        return result;
    }

    // Helper function to check if it's possible to allocate books with the max pages constraint
    private static boolean isPossible(int[] arr, int k, int maxPages) {
        int studentsRequired = 1;  // Start with the first student
        int currentPages = 0;

        for (int i = 0; i < arr.length; i++) {
            // If adding this book exceeds the maxPages for the current student
            if (currentPages + arr[i] > maxPages) {
                studentsRequired++;  // Allocate to the next student
                currentPages = arr[i];  // Start with this book for the new student
                
                // If we exceed the number of students, it's not possible
                if (studentsRequired > k) {
                    return false;
                }
            } else {
                currentPages += arr[i];  // Add this book to the current student
            }
        }
        return true;
    }
}
```
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/searching-gfg-160/problem/kth-missing-positive-number-in-a-sorted-array">Problem 8</a></h3>

```java
class Solution {
    public int kthMissing(int[] arr, int k) {
        // code here
        int n = arr.length;
        int missing_count = 0;
        int i = 0;
        int current = 1;  // Start checking from the number 1

        while (i < n) {
            if (arr[i] != current) {
                missing_count++;
                if (missing_count == k) {
                    return current;
                }
            } else {
                i++;
            }
            current++;
        }

        // If we exit the loop, it means the kth missing number is after the last element of arr[]
        return arr[n - 1] + (k - missing_count);
        
    }
}
```

<h1>Matrix</h1>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/matrix-gfg-160/problem/spirally-traversing-a-matrix-1587115621"></h3>

```js
class Solution {
    // Function to return a list of integers denoting spiral traversal of matrix.
    public ArrayList<Integer> spirallyTraverse(int mat[][]) {
        // code here
            ArrayList<Integer> result = new ArrayList<>();
        
        int n = mat.length;     // number of rows
        int m = mat[0].length;  // number of columns
        
        int top = 0, bottom = n - 1, left = 0, right = m - 1;
        
        while (top <= bottom && left <= right) {
            // Traverse from left to right along the top row
            for (int i = left; i <= right; i++) {
                result.add(mat[top][i]);
            }
            top++;
            
            // Traverse from top to bottom along the right column
            for (int i = top; i <= bottom; i++) {
                result.add(mat[i][right]);
            }
            right--;
            
            // Traverse from right to left along the bottom row
            if (top <= bottom) { // Check if there are rows remaining
                for (int i = right; i >= left; i--) {
                    result.add(mat[bottom][i]);
                }
                bottom--;
            }
            
            // Traverse from bottom to top along the left column
            if (left <= right) { // Check if there are columns remaining
                for (int i = bottom; i >= top; i--) {
                    result.add(mat[i][left]);
                }
                left++;
            }
        }
        
        return result;
    }
}

```

<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/matrix-gfg-160/problem/rotate-by-90-degree-1587115621">Problem 2</a></h3>

```java
class Solution {
    // Function to rotate matrix anticlockwise by 90 degrees.
    static void rotateby90(int mat[][]) {
        // code here
        int n = mat.length;

        // Step 1: Transpose the matrix
        for (int i = 0; i < n; i++) {
            for (int j = i; j < n; j++) {
                // Swap mat[i][j] with mat[j][i]
                int temp = mat[i][j];
                mat[i][j] = mat[j][i];
                mat[j][i] = temp;
            }
        }

        // Step 2: Reverse each column
        for (int j = 0; j < n; j++) {
            int start = 0, end = n - 1;
            while (start < end) {
                // Swap mat[start][j] with mat[end][j]
                int temp = mat[start][j];
                mat[start][j] = mat[end][j];
                mat[end][j] = temp;
                start++;
                end--;
            }
        }
    }
}
```

<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/matrix-gfg-160/problem/search-in-a-matrix17201720">Problem 3 </a></h3>

```java
class Solution {
    public static boolean matSearch(int mat[][], int x) {
        // your code here
         int n = mat.length;    // Number of rows
        int m = mat[0].length; // Number of columns
        
        // Start from top-right corner of the matrix
        int i = 0, j = m - 1;
        
        while (i < n && j >= 0) {
            if (mat[i][j] == x) {
                return true;  // Element found
            } else if (mat[i][j] < x) {
                i++;  // Move down
            } else {
                j--;  // Move left
            }
        }
        
        return false;  // Element not found
    }
}
```

<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/matrix-gfg-160/problem/search-in-a-row-wise-sorted-matrix">Problem 4</a></h3>

```js
public boolean searchMatrix(int[][] mat, int x) {
    int n = mat.length; // number of rows
    int m = mat[0].length; // number of columns
    
    // Binary search over the entire matrix
    int low = 0, high = n * m - 1;
    
    while (low <= high) {
        int mid = low + (high - low) / 2;
        int midElement = mat[mid / m][mid % m];
        
        if (midElement == x) {
            return true; // Found the element
        } else if (midElement < x) {
            low = mid + 1; // Search in the right half
        } else {
            high = mid - 1; // Search in the left half
        }
    }
    
    return false; // Element not found
}
```

<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/matrix-gfg-160/problem/search-in-a-matrix-1587115621">PRoblem 5</a></h3>

```js
public void setMatrixZeroes(int[][] mat) {
    int n = mat.length;
    int m = mat[0].length;

    // Use variables to track if the first row and first column need to be set to zero
    boolean firstRowZero = false;
    boolean firstColZero = false;

    // Check if the first row has any zeros
    for (int j = 0; j < m; j++) {
        if (mat[0][j] == 0) {
            firstRowZero = true;
            break;
        }
    }

    // Check if the first column has any zeros
    for (int i = 0; i < n; i++) {
        if (mat[i][0] == 0) {
            firstColZero = true;
            break;
        }
    }

    // Use first row and first column to mark zeros
    for (int i = 1; i < n; i++) {
        for (int j = 1; j < m; j++) {
            if (mat[i][j] == 0) {
                mat[i][0] = 0;
                mat[0][j] = 0;
            }
        }
    }

    // Zero out rows based on markers in the first column
    for (int i = 1; i < n; i++) {
        if (mat[i][0] == 0) {
            for (int j = 1; j < m; j++) {
                mat[i][j] = 0;
            }
        }
    }

    // Zero out columns based on markers in the first row
    for (int j = 1; j < m; j++) {
        if (mat[0][j] == 0) {
            for (int i = 1; i < n; i++) {
                mat[i][j] = 0;
            }
        }
    }

    // Zero out the first row if needed
    if (firstRowZero) {
        for (int j = 0; j < m; j++) {
            mat[0][j] = 0;
        }
    }

    // Zero out the first column if needed
    if (firstColZero) {
        for (int i = 0; i < n; i++) {
            mat[i][0] = 0;
        }
    }
```

<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/matrix-gfg-160/problem/search-in-a-matrix-1587115621">Problem 6</a></h3>

```js
int n = mat.length;
        int m = mat[0].length;

        // Variables to check if the first row or first column needs to be zeroed
        boolean firstRowZero = false;
        boolean firstColZero = false;

        // Check if the first row contains a zero
        for (int j = 0; j < m; j++) {
            if (mat[0][j] == 0) {
                firstRowZero = true;
                break;
            }
        }

        // Check if the first column contains a zero
        for (int i = 0; i < n; i++) {
            if (mat[i][0] == 0) {
                firstColZero = true;
                break;
            }
        }

        // Use the first row and first column to mark rows and columns to be zeroed
        for (int i = 1; i < n; i++) {
            for (int j = 1; j < m; j++) {
                if (mat[i][j] == 0) {
                    mat[i][0] = 0; // Mark the first column
                    mat[0][j] = 0; // Mark the first row
                }
            }
        }

        // Zero out cells based on the marks in the first row and first column
        for (int i = 1; i < n; i++) {
            for (int j = 1; j < m; j++) {
                if (mat[i][0] == 0 || mat[0][j] == 0) {
                    mat[i][j] = 0;
                }
            }
        }

        // Zero out the first row if needed
        if (firstRowZero) {
            for (int j = 0; j < m; j++) {
                mat[0][j] = 0;
            }
        }

        // Zero out the first column if needed
        if (firstColZero) {
            for (int i = 0; i < n; i++) {
                mat[i][0] = 0;
            }
        }
```
