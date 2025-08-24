# Leetcode-125.-Valid-Palindrome
# Description
A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.
# Solution
We are given a string s , and we have to check whether all the alphanumeric characters in the string is palindromic or not i.e the forward and backward characters are the same .

Example 1:

Input: s = "A man, a plan, a canal: Panama"

Output: true

Explanation: "amanaplanacanalpanama" is a palindrome.

Example 2:

Input: s = "race a car"

Output: false

Explanation: "raceacar" is not a palindrome.

Example 3:

Input: s = " "

Output: true

Explanation: s is an empty string "" after removing non-alphanumeric characters.

Since an empty string reads the same forward and backward, it is a palindrome.

Intuition:
1. We will use 2 poinster technique which uses left and right pointers initialised as 0 and len(s)-1 .
2. These pointers will check if the characters of left and right are either alphabet or numbers and if it is not then we will ignore and increase or decrease the l and r pointers.

# Algorithm
1. Initialise 2 poinster l and r as 0 and len(s)-1.
2. Use while loop until l<r and check if s[l] is alphabet or numerical , if it is not then increment l+=1
3. Use while loop until l<r and check if s[r] is alphabet or numerical , if it is not then decrement r-=1
4. Check if s[l] and s[r] are equal o rnot , if they are not equal it means they are not palindromic , hence return False.
5. Else increment l pointer as l+=1 and decrement right pointer as r-=1.
6. Return True if no invalid characters match .
# Code
class Solution:

    def isPalindrome(self, s: str) -> bool:
        l,r=0,len(s)-1

        while l<r:
            while l<r and  not s[l].isalnum():
                l+=1
            while l<r and not s[r].isalnum():
                r-=1

            if s[l].lower()!=s[r].lower():
                return False
            l+=1
            r-=1
        return True
# Complexity

Time complexity:

 while l<r:
 
            while l<r and  not s[l].isalnum():
                l+=1
            while l<r and not s[r].isalnum():
                r-=1
  These operations take O(n) time complexity for looping through the entire array.

  Total time complexity : O(n)

  Space Complexity:

  Use of variables like l and r pointers take linear O(1) space .
