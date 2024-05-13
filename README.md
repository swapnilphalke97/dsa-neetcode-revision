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







