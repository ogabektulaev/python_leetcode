# python_leetcode
#  Longest Substring Without Repeating Characters

class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        store = ''
        result=[]
        for i in range(len(s)):
            if s[i] in store:
                result.append(store)
                index = store.find(s[i])
                store = store[index+1::]+s[i]
            else:
                store+=s[i]
        result.append(store)

        last_result = 0
        for j in result:
            if len(j)>last_result:
                last_result = len(j)
        
        return last_result


  
