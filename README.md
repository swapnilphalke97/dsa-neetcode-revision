# dsa-neetcode-revision [NeetCode RoadMap](https://neetcode.io/roadmap)

## Arrays & Hashing
### [Contains Duplicate](https://leetcode.com/problems/contains-duplicate/description/)
Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

Approach 1:- Sort an array, and iterate through array to check if there is any duplicate. Time complexity- O(n)

Approach 2:-Use a hash set data structure to store encountered elements. It iterates through the array, checking if an element is already in the set. 
            If so, it returns true. 

### [Valid Anagram](https://leetcode.com/problems/valid-anagram/description/)
Given two strings s and t, return true if t is an anagram of s, and false otherwise.
An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

Approach 1:- Sort both String by converting them to character array. And check if both arraya are equal.

Approach 2:- Create hashmap<Character, Integer> , take 1st string,count the frequency of characters. take 2nd string, Decrement the frequency of characters. Then iterate through hashmap and Check if any character has non-zero frequency.

Approach 3:- create int[] count = new int[26], increment count of frequency for 1st string count[x - 'a']++, take 2nd string and similarly decrement the count. checck if at end have all zero frequency.




