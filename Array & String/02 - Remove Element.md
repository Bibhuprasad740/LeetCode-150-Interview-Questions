## 02. Remove Element

<span style="color: white; padding: 5px 20px; background-color: darkgreen; border-radius: 20px">Easy</span>

The link of the problem can be found [here](https://leetcode.com/problems/remove-element/description/?envType=study-plan-v2&envId=top-interview-150)

### My Approach

Start a pointer `nextElement` at 0. Now iterate over all the elements of the array. If the `currentElement` is not `targetElement`, then we can happily push this `currentElement` into our array, **But in what position?** That's why we have the `nextElement` pointer. At `arr[nextElement]` we will push the `currentElement` and increment `nextElement` pointer. In this manner, we can avoid pushing the target element in our array. At the end, `nextElement` will point to the new size of the array, so return it.

##### Algorithm:

    - Take a pointer nextElement = 0
    - For every element in the array do the following:
        If currentElement not equals to target:
            store currentElement at nextElement position
            increment nextElement
    - Return nextElement



### Time and Auxiliary Space Complexity:

- **Time Complexity:** `O(n)` where `n` is the size of `arr`.
- **Space complexity:** `O(1)` as I am not using any extra space.

### Code(C++)

```cpp
class Solution {
public:
    int removeElement(vector<int>& arr, int val) {
        int next = 0;
        int n = arr.size();
        for(int i = 0; i < n; i++){
            if(arr[i] != val){
                arr[next] = arr[i];
                next++;
            }
        }

        return next;
    }
};
```

- **If you find this solution helpful, consider supporting me by giving a `⭐ star` to the [LeetCode-150-Interview-Questions](https://github.com/Bibhuprasad740/LeetCode-150-Interview-Questions) repository.**

 ```cpp
 Made With ❤️ By Bibhu Prasad Sahoo
 ``` 
