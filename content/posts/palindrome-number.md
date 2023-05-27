---
title: "Palindrome Number"
date: 2023-05-27T01:52:00-05:00
draft: false 
---

![Palindrome Banner](/palindrome/palindrome_banner.png)

*Given - number n.*

Return - n is palindrome or not.

### Steps
1. Create a temporary variable to store the incoming number for later.
2. Create a variable to store the reconstructed reverse of the given number and initialize it to 0.
3. We take the idea of dividing (%) a number by 10 that gives the units digit as remainder. (Main step to remember while answering problems like this)
4. So, we keep a condition in while loop that number must not be 0.
5. In while loop we take a temporary variable to store the unit's digit of the given number (this will be updated at end of loop)
6. Now use the temp var like below
  1. reverseNumber = reverseNumber * 10 + temporaryVariable
7. At the end of loop we divide the given number n / 10 and update it to n, i.e n = n/10. We do this until we reach 0 and exit the loop.
8. After that we can check whether the reverseNumber == n to return boolean value.

![Palindrome Explanation](/palindrome/palindrome_number.png)

### Java Implementation
```java
Java Implementation
class Solution {
    public boolean isPalindrome(int x) {
        int temp = x;
        int reverseNumber = 0;
        if (x < 0) {
            return false;
        }

        while (x != 0) {
            int zeroUnitDigit = x % 10;
            reverseNumber = reverseNumber * 10 + zeroUnitDigit;
            x = x / 10;
        }
        return (reverseNumber == temp) ? true : false;
    }
}
```
