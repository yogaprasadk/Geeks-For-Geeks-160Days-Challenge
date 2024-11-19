<h3>Second Largest Element In an array</h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/article/MTQ4NDk1"></a>Article</h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/video/Mjc4NzQ%3D"></a>Video/h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/second-largest3735"></a>Problem</h3>

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
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/article/MTIzNDkz"></a>Article</h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/video/Mjc4OTY%3D"></a>Video/h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/move-all-zeroes-to-end-of-array0751"></a>Problem</h3>

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
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/article/MjU2Nw%3D%3D"></a>Article</h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/video/Mjc4OTc%3D"></a>Video/h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/reverse-an-array"></a>Problem</h3>

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
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/article/MjM5OA%3D%3D"></a>Article</h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/video/Mjc4OTg%3D"></a>Video/h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/rotate-array-by-n-elements-1587115621"></a>Problem</h3>

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
<h3><a href=""></a>Article</h3>
<h3><a href=""></a>Video/h3>
<h3><a href="https://www.geeksforgeeks.org/batch/gfg-160-problems/track/arrays-gfg-160/problem/next-permutation5226"></a>Problem</h3>

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
