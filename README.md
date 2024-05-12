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



