# Maximum of subarrays

[solution in R](solution-r.md) <br>
[solution in Python](solution-python.md)

Given an array and an integer A, find the maximum for each contiguous subarray of size A.

```
Input: array = [1, 2, 3, 1, 4, 5, 2, 3, 6], A = 3
Output: 3 3 4 5 5 5 6
```

Below is a more detailed walkthrough of what you should be trying to code, using the example above:


subarray 1 = [**1**, **2**, **3**, 1, 4, 5, 2, 3, 6] <br>
maximum of subarray 1 = 3


subarray 2 = [1, **2**, **3**, **1**, 4, 5, 2, 3, 6] <br>
maximum of subarray 2 = 3



subarray 3 = [1, 2, **3**, **1**, **4**, 5, 2, 3, 6] <br>
maximum of subarray 3 = 4

Etc.

[back](https://project-dmaestro.github.io/data-interview-qs/)
