**Problem 5 in Top Interview Questions (medium)**

 Leetcode Problem 5: Longest Palindromic Substring 

Problem Link:  https://leetcode.com/problems/longest-palindromic-substring/

Explanation: 



 Java Solution: 
    n = number of characters in string
    
Time and Space Complexity
    => Space: O(1)
    => Time: O(n^2)

```java
class Solution {
    public String longestPalindrome(String s) {
        
        char[] carr = s.toCharArray();
        String palinS = "";
        int len = carr.length;
        int left, right;
        for(int curr = 0; curr < len; curr++){
            left = curr-1;
            right = curr+1;
        
            while(right < len && carr[curr] == carr[right]){ right++;}
            
            while(left >= 0 && right < len){
                if(carr[left] != carr[right]){ break; }
                left--;
                right++;
            }
            left++;
            if((right-left) > palinS.length()){
                palinS = s.substring(left, right);
            }
        }
        return palinS;
    }
}
```