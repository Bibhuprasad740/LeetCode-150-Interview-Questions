## 01. Merge Sorted Array

<span style="color: white; padding: 5px 20px; background-color: darkgreen; border-radius: 20px">Easy</span>

The link of the problem can be found [here](https://leetcode.com/problems/merge-sorted-array/?envType=study-plan-v2&envId=top-interview-150)

### My Approach

There are two arrays `arr1` and `arr2`. It is given that `arr1` already has space to accomodate the elements of `arr2`. **Start comparing from end of both the arrays.** Keep a pointer `k` to mark the insertion in the sorted array `arr1`. **It is important that** we are not creating an extra array to store the elements in sorted manner; so it at the end of our loop there are elements left uncompared in `arr1`, then it's perfectly fine because we are given in the question that both `arr1` and `arr2` are sorted. Now it's just a matter of implementation.

##### Algorithm:

    - Take an integer k = m + n - 1 
    - Do the following while m > 0 and n > 0 :
    - If (m - 1)th element of arr1 is greater than (n - 1)th element of arr2:
        store (m - 1)th element at kth position of arr1
        decrement m
        decrement k
    - Otherwise
        store (n - 1)th element at kth position of arr1
        decrement n
        decrement k
    - Check till n is greater than 0
        store (n - 1)th element at kth position of arr1
        decrement n
        decrement k

### Time and Auxiliary Space Complexity:

- **Time Complexity:** `O(m + n)` where `m` is the size of `arr1` and `n` is the size of `arr2`.
- **Space complexity:** `O(1)` as I am not using any extra space.

### Code(C++)

```cpp
class Solution {
public:
    void merge(vector<int>& arr1, int m, vector<int>& arr2, int n) {
        int k = m + n - 1;
        while(m > 0 and n > 0) {
            if(arr1[m - 1] > arr2[n - 1]){
                arr1[k] = arr1[m - 1];
                m --;
            } else {
                arr1[k] = arr2[n - 1];
                n --;
            }
            k--;
        }
        
        // check if there are elements left in arr2
        while(n > 0){
            arr1[k] = arr2[n - 1];
            n --;k--;
        }
    }
};
```

- **If you find this solution helpful, consider supporting me by giving a `⭐ star` to the [LeetCode-150-Interview-Questions](https://github.com/Bibhuprasad740/LeetCode-150-Interview-Questions) repository.**

 ```cpp
 Made With ❤️ By Bibhu Prasad Sahoo
 ``` 
