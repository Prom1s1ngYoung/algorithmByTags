# Algorithm By Tags
## Binary Search
### Maximize the minimum/Minimize the maximum
| Question                                  | Other Related Tags         |    Supplementary Techniques   |  Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3399. Smallest Substring With Identical Characters II](https://leetcode.com/problems/smallest-substring-with-identical-characters-ii/description/)  | `Special Case Optimization`    | By considering the "01010101...01" and "101010...10" such patterns separately. |⭐️⭐️⭐️⭐️|

<br><br>
## Dynamic Programming
### State Machine DP
| Question                                  | Other Related Tags         |    Supplementary Techniques   |  Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3389. Minimum Operations to Make Character Frequencies Equal](https://leetcode.com/problems/minimum-operations-to-make-character-frequencies-equal/description/)  | `Enumeration` |  1. Not hard to think that the outer iteration is to enumerate the occurrence of a character. But what should it do in the inner?<br><br> 2. DP is a good way to solve, but defining states is tricky here. Try to find how to from specific to general. |⭐️⭐️⭐️⭐️⭐️|

<br><br>
## Data Structure
### Hash Table
| Question                                  | Other Related Tags         |    Supplementary Techniques   |  Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|


<br><br>
### Segment Tree
| Question                                  | Other Related Tags         |    Supplementary Techniques   | Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3382. Maximum Area Rectangle With Point Constraints II](https://leetcode.com/problems/maximum-area-rectangle-with-point-constraints-ii/description/)  | `Hash Table`, `Offline + Enumeration`, `Static 2D Points`    |  The way of using Hash Table is similar to "two sum" |  ⭐️⭐️⭐️⭐️⭐️ |
| [G. Unusual Entertainment](https://codeforces.com/problemset/problem/1899/G)  | `DFS Order`, `Offline + Differ`, `Static 2D Points` | 1. Using DFS order to quickly check if one node is the child of one tree. <br><br>2. Organizing in advance which query operations should be executed for each index position serves as a “bridge” between offline processing and the concept of difference-based methods. |⭐️⭐️⭐️⭐️⭐️⭐️|

<br><br>
## Math
### Permutation
| Question                                  | Other Related Tags         |    Supplementary Techniques   |  Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3395. Subsequences with a Unique Middle Mode I](https://leetcode.com/problems/subsequences-with-a-unique-middle-mode-i/description/)  | `Prefix`, `Suffix` |  Since the wanted subsequences should meet a length of 5, it is not a big task for us to do the classification. So let's start with iterating the mid element, and assume the mid element's value is 'x': <br><br> 1. Find two elements on the left and two elements on the right that are not equal to 'x'. <br> 2. Find two elements with value 'y' on the left, find another 'x' on the right. <br> 3. Find two elements with value 'y' on the right, find another 'x' on the left. <br>  4. Find one 'y' and one 'x' on the left, and one 'y' on the right. <br>  5. Find one 'y' on the left, find one 'y' and one 'x' on the right. <br><br> Above cases don't satisfy the request, we can calculate the total number of subsequences of size 5 and then minus the above results to get the answer.|⭐️⭐️⭐️⭐️⭐️|

<br><br>
## Greedy Algorithm
### Interval Greedy
#### Interval Covering
| Question                                  | Other Related Tags         |    Supplementary Techniques   |  Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [45. Jump Game II](https://leetcode.com/problems/jump-game-ii/description/)  | `null`    |  null |⭐️⭐️|

<br><br>
## String
### KMP
| Question                                  | Other Related Tags         |    Supplementary Techniques   |  Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [1668. Maximum Repeating Substring](https://leetcode.com/problems/maximum-repeating-substring/description/)  | `DP`  | KMP + DP  |⭐️⭐️⭐️|

<br><br>
### Z Algorithm
Great technique to understand Z - [Z Algorithm demo](https://personal.utdallas.edu/~besp/demo/John2010/z-algorithm.htm)
| Question                                  | Other Related Tags         |    Supplementary Techniques   | Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [1668. Maximum Repeating Substring](https://leetcode.com/problems/maximum-repeating-substring/description/)  | `DP`    | Z + DP  |⭐️⭐️⭐️|
| [3292. Minimum Number of Valid Strings to Form Target II](https://leetcode.com/problems/minimum-number-of-valid-strings-to-form-target-ii/description/)  | `Greedy`    | [Interval covering greedy](#interval-covering)  |⭐️⭐️⭐️⭐️|

<br><br>
### Aho-Corasick
| Question                                  | Other Related Tags         |    Supplementary Techniques   | Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3292. Minimum Number of Valid Strings to Form Target II](https://leetcode.com/problems/minimum-number-of-valid-strings-to-form-target-ii/description/)  | `Greedy`    | [Interval covering greedy](#interval-covering) |⭐️⭐️⭐️⭐️|

