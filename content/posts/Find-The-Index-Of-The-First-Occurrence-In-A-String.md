---
title: "Find the Index of the First Occurrence in a String"
date: 2023-05-27T02:15:01-05:00
draft: false 
---

*Given 2 strings - haystack and needle.*

### Problem statement

Find the index of needle substring if present in haystack and return starting index of the first occurrence, else return -1.

### Intuition: Use Window Sliding technique

Idea is to iterate from 0 till length of haystack - length of needle, this will help us not to overrun the last index.

### Algorithm
```java
function find_occurence{
    loop i: 0 to haystack.length-needle.length{
        haystack.substring(i, i+needle.length) == needle
        return index
    }
    return -1
}
```
### Example:

**haystack**: hadel, **needle**: ade

**In first iteration,**

- haystack substring from 0, 0+3 is had.
- checking had equal to ade
- not equal going to next iteration.

**In second iteration,**

- haystack substring from 1, 1+3 is ade
- checking ade equals to ade
- true, return index i i.e., 1

### Java Implementation

```java
class Solution {
    public int strStr(String haystack, String needle) {
        // taking lengths of both the given strings

        int ln = needle.length();
        int lh = haystack.length();

        for (int i = 0; i <= lh - ln; i++) {

            // checking if substring of haystack of size needle string from
            // current index to the needle string.
            if (haystack.substring(i, i + ln).equals(needle)) {
                // we found needle string in haystack, we'll return index i
                // to save time and computation, since we only need index of 
                // first occurence.
                return i;
            }
        }
        // Finally we return -1 since we haven't found needle in haystack :)
        return -1;
    }

}
```
