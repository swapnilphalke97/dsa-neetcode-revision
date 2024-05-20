# dsa-neetcode-revision [NeetCode RoadMap](https://neetcode.io/roadmap)

## Arrays & Hashing

### [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/description/)
Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

*Approach 1:* Sort the array and iterate through to check for duplicates. Time complexity - O(n)

*Approach 2:* Use a hash set to store encountered elements. Iterate through the array, checking if an element is already in the set. If so, return true.

### [Valid Anagram](https://leetcode.com/problems/valid-anagram/description/)
Given two strings s and t, return true if t is an anagram of s, and false otherwise. An anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

*Approach 1:* Sort both strings by converting them to character arrays and check if they are equal.

*Approach 2:* Create a hashmap<Character, Integer>. Count the frequency of characters in the first string, then decrement the frequency of characters in the second string. Iterate through the hashmap and check if any character has a non-zero frequency.

*Approach 3:* Create int[] count = new int[26], increment the count of frequency for the first string count[x - 'a']++, then do the same for the second string. Check if at the end all frequencies are zero.

### [Two Sum](https://leetcode.com/problems/two-sum/description/)
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target. Input: nums = [2,7,11,15], target = 9 Output: [0,1]

*Approach 1:* Create a HashMap. While iterating through the array, store each element's index in the map. If the current element's complement (target - current element) exists in the map, return the indices.

### [Group Anagrams](https://leetcode.com/problems/group-anagrams/description/)
Given an array of strings, group anagrams together.

*Approach:* 
Create a hashmap where the key is a sorted version of each string in the array, and the value is a list of strings that are anagrams of each other. Iterate through the array, sort each string, and check if the sorted string exists as a key in the hashmap. If it does, add the original string to the corresponding list. If not, create a new list with the original string as its only element and add it to the hashmap with the sorted string as the key. Finally, return the values of the hashmap.

### [Top K Frequent Elements](https://leetcode.com/problems/top-k-frequent-elements/description/)
Given an integer array nums, return the k most frequent elements. You may return the answer in any order.

*Approach1 :*
1. *Frequency Counting:* 
   Create a hashmap to count the frequency of each element in the array.

2. *Bucket Sorting:*
   Utilize bucket sorting to group elements by their frequency. Create an array of lists where each index represents the frequency of elements. Iterate through the frequency map and distribute elements into their respective buckets based on their frequency.

3. *Extract Top K Elements:*
   Traverse the array of lists in reverse order (from highest frequency to lowest) and extract elements until we have collected the top k frequent elements.
   
*Approach2 :*
1. *Frequency Counting:* 
   Create a hashmap to count the frequency of each element in the array.

2. *Priority Queue:*
   Use a priority queue to store elements based on their frequency, with the highest frequency elements at the top. Iterate through the hashmap and add elements to the priority queue. Once the priority queue's size exceeds k, remove the element with the lowest frequency. Finally, return the elements remaining in the priority queue.


### [Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/description/)
Given an array nums of n integers where n > 1, return an array output such that output[i] is equal to the product of all the elements of nums except nums[i].

*Approach 1 :*
1. *Left and Right Product Arrays:*
   Iterate through the input array nums twice to construct two arrays, leftProducts and rightProducts, representing the product of all elements to the left and right of each element, respectively. 
   
2. *Construct Output Array:*
   For each index i in the input array, the product of all elements except nums[i] is the product of leftProducts[i] and rightProducts[i]. Create the output array by multiplying corresponding elements from leftProducts and rightProducts.
   
*Approach 2 :* Similar to approch 1, but try to do inplace prefix suffix calculation to avoid extra space complexity.


## Two Pointers
### [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/description/)
Given a string s, determine if it is a valid palindrome. A valid palindrome is defined as a string that reads the same backward as forward, ignoring cases and non-alphanumeric characters.

*Approach:*
1. *Two-Pointer Technique:*
   Use two pointers, one starting from the beginning of the string and the other starting from the end. Move both pointers towards the center, comparing characters at each step. Ignore non-alphanumeric characters and consider only alphanumeric characters for comparison. If the characters at corresponding positions are not equal, the string is not a palindrome.

### [Two Sum II - Input Array is Sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/description/)
Given an array of integers numbers that is already sorted in non-decreasing order, and an integer target, return indices of the two numbers such that they add up to target.

*Approach:*
1. *Two-Pointer Technique:*
   Initialize two pointers, one at the beginning and the other at the end of the sorted array. Iterate through the array while the pointers do not overlap. Calculate the sum of the elements pointed to by the two pointers. If the sum is equal to the target, return the indices of the two elements. If the sum is less than the target, increment the left pointer to increase the sum. If the sum is greater than the target, decrement the right pointer to decrease the sum.

### [Three Sum](https://leetcode.com/problems/3sum/)
Given an array nums of n integers, return all unique triplets [nums[i], nums[j], nums[k]] such that nums[i] + nums[j] + nums[k] == 0.

*Approach:*
1. *Two-Pointer Technique:*
   Sort the input array nums. Iterate through the array with a fixed element nums[i]. Use two pointers, one starting from the element after nums[i] and the other starting from the end of the array. Move the two pointers towards each other, checking if the sum of nums[i], nums[left], and nums[right] is equal to zero. If the sum is less than zero, increment the left pointer. If the sum is greater than zero, decrement the right pointer. If the sum is zero, add [nums[i], nums[left], nums[right]] to the result list. Skip duplicate elements to avoid duplicate triplets.

### [Container With Most Water](https://leetcode.com/problems/container-with-most-water/description/)
Given n non-negative integers height representing the heights of bars in a bar chart where the width of each bar is 1, compute the area of the largest rectangle that can be formed by the bars. 

*Approach:*
1. *Two-Pointer Technique:*
   Initialize two pointers, one at the start of the array and the other at the end. Calculate the area of the rectangle formed by the two pointers (width = distance between the pointers, height = minimum height of the two bars). Move the pointer with the smaller height towards the other pointer. Update the maximum area encountered so far. Repeat this process until the two pointers meet.

## Binary Search
### [Binary Search](https://leetcode.com/problems/binary-search/description/)

Given a sorted array and a target value, binary search efficiently locates the target within the array.

*Approach:* 
1. Initialize two pointers, left and right, at the start and end of the array, respectively.
2. While left is less than or equal to right, calculate the middle index as (left + right) / 2.
   - If the middle element equals the target, return its index.
   - If the middle element is greater than the target, update right to mid - 1.
   - If the middle element is less than the target, update left to mid + 1.
3. If the target is not found, return -1.

### [Search a 2D Matrix](https://leetcode.com/problems/search-a-2d-matrix/description/)

Given a 2D matrix where each row is sorted in ascending order and the first integer of each row is greater than the last integer of the previous row, efficiently search for a target value.

*Approach:* 
1. Start from the top-right corner of the matrix.
2. Compare the target value with the current element:
   - If the target is equal to the current element, return true.
   - If the target is less than the current element, move left to explore smaller elements in the same row.
   - If the target is greater than the current element, move down to explore larger elements in the same column.
3. Repeat the process until the target is found or the boundaries of the matrix are exceeded.
4. If the target is not found after exploration, return false.

### [Koko Eating Bananas](https://leetcode.com/problems/koko-eating-bananas/description/)

Koko loves to eat bananas, and she wants to finish eating all the bananas as quickly as possible. She has n piles of bananas, and the i-th pile has piles[i] bananas. The piles are arranged in a row. Koko can only eat at most one pile per hour, and she must eat the bananas in the order they are presented. 

Given an integer array piles representing the number of bananas in each pile and an integer h representing the number of hours Koko has to eat all the bananas, the task is to find the minimum integer k such that Koko can eat all the bananas within h hours.

*Approach:* 
1. *Binary Search on Speed:*
   - Initialize low to 1 (minimum speed) and high to the maximum pile size (maximum speed).
   - While low is less than or equal to high, calculate the mid speed mid as (low + high) / 2.
   - Check if Koko can finish eating all the bananas within h hours at the speed mid:
     - For each pile, calculate the time required to eat its bananas at the speed mid.
     - Sum up the time for all piles.
     - If the total time is less than or equal to h, update high to mid, indicating that Koko can eat at a lower speed.
     - Otherwise, update low to mid + 1, indicating that Koko needs to eat faster.
   - After the binary search, return low as the minimum speed required for Koko to eat all the bananas within h hours.

## Linked List
### (Reverse a Linked List)[https://leetcode.com/problems/reverse-linked-list/description/]

Given the head of a singly linked list, reverse the list and return the reversed list.

*Approach:* 
1. *Iterative Method:*
   - Initialize three pointers: prev as null, current as head, and next as null.
   - While current is not null, do the following:
     - Store the next node: next = current.next.
     - Reverse the current node's pointer: current.next = prev.
     - Move the pointers one position forward: set prev to current and current to next.
   - At the end of the loop, prev will be the new head of the reversed list.
   - Return prev as the new head of the reversed list.
     
### [Merge Two Sorted Arrays](https://leetcode.com/problems/merge-two-sorted-lists/)

Given two sorted arrays nums1 and nums2, merge them into a single sorted array.

*Approach:* 
1. *Two Pointers Method:*
   - Initialize two pointers: i at the beginning of nums1 and j at the beginning of nums2.
   - Initialize an empty array merged to store the merged elements.
   - While both pointers are within the bounds of their respective arrays, compare the elements at nums1[i] and nums2[j]:
     - If nums1[i] is less than or equal to nums2[j], append nums1[i] to merged and increment i.
     - Otherwise, append nums2[j] to merged and increment j.
   - If there are remaining elements in nums1, append them to merged.
   - If there are remaining elements in nums2, append them to merged.
   - Return the merged array.
  
### [Reorder List](https://leetcode.com/problems/reorder-list/description/)

Given a singly linked list, reorder it to follow the specific pattern: L0 → Ln → L1 → Ln-1 → L2 → Ln-2 → ....

*Approach:* 
1. *Find the Middle of the List:*
   - Use the slow and fast pointer technique to find the middle node of the list.
   - Initialize slow and fast pointers at the head of the list. Move slow by one step and fast by two steps until fast reaches the end.
2. *Reverse the Second Half:*
   - From the middle node, reverse the second half of the list.
   - Initialize three pointers: prev as null, current as the middle node, and next as null.
   - While current is not null, reverse the pointers and move forward.
3. *Merge the Two Halves:*
   - Initialize two pointers: first at the head of the list and second at the head of the reversed second half.
   - Alternate between the nodes of the first half and the reversed second half to form the reordered list.
   - Use a temporary pointer to keep track of the next nodes during the merge.
4. *Update the Next Pointers:*
   - Continue merging until all nodes are reordered.
   - Ensure the last node of the reordered list points to null.
   - 
### [Remove Nth Node From End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/description/)

Given the head of a singly linked list, remove the nth node from the end of the list and return its head.

*Approach:* 
1. *Two-Pointer Technique:*
   - Initialize two pointers, first and second, both starting at the head of the list.
   - Move the first pointer n steps forward.
   - If first becomes null after moving n steps, it means the head needs to be removed, so return head.next.
   - Otherwise, move both first and second pointers one step at a time until first reaches the end of the list.
   - By this point, the second pointer will be just before the node to be removed.
   - Adjust the next pointer of the second node to skip the nth node from the end.
2. *Edge Cases:*
   - If the list has only one node and n is 1, return null.
   - Ensure proper handling of the edge case where the node to be removed is the head node.
