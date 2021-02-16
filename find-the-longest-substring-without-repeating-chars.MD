#### https://leetcode.com/problems/longest-substring-without-repeating-characters/

# Solution 1  

```
var lengthOfLongestSubstring = function (s) {

  if (!!!s.length || typeof s !== "string") return 0; //if our string is empty or it's not a

  if (s.length == 1) return 1;
  //if the length is 1, return 1;

  let hashTable = {}; //our hashTable to hold our characters and index;
  let longestSubstringLength = 0; //length of longest substring
  let start = 0; //start index
  let length = s.length; //length of the array.

  //convert our strings to an array;
  const strings = s.split("");

  //iterate over the array
  for (let i = 0; i < length; i++) {
  
    //if the character exist and the value of the character is greater or equal to our start index
    if (hashTable[strings[i]] !== undefined && hashTable[strings[i]] >= start) {
    
      //change the value of start to one higher than the value of our current character
      start = hashTable[strings[i]] + 1;
      
    }
    
    //add the current index and it's value to the hashTable
    hashTable[strings[i]] = i;
    
    //find the length of the longest substring by comparing the value with the value of the current index minus the start value plus 1
    longestSubstringLength = Math.max(longestSubstringLength, i - start + 1);
  }

  //return the longestSubstringLength as our final answer
  return longestSubstringLength;
};
```
  

# Solution 2 (without Map)
```
function lengthOfLongestSubstring(s) {
    let stringLength = s.length; 
    let maxLength = 0;
    const charMap = new Map(); 
    let pos = 0;
    for (let i = 0; i < stringLength; i++) {
        if (charMap.has(s[i])) {
        pos = Math.max(charMap.get(s[i]), pos);
    }
    maxLength = Math.max(maxLength, i - pos + 1);
    charMap.set(s[i], i + 1);
  }
  console.log(maxLength);   
}
``` 

# Test Data   
"abcabcabccdabc" //3   
"pwwkew" //3   
"bbbbb" //1   
