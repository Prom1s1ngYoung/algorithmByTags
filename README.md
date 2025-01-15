# Algorithm By Tags
## Sliding window/Two pointers
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3420. Count Non-Decreasing Subarrays After K Operations](https://leetcode.cn/problems/count-non-decreasing-subarrays-after-k-operations/solutions/3045053/on-xian-xing-zuo-fa-dan-diao-zhan-di-qia-ay5b/)  | `Monotonous Stack`, `Monotonous Queue` | If a longer subarray satisfies the conditions, then a shorter subarray will also satisfy the conditions, the sliding window can be used. When the right pointer moves to next, an element on the right goes into the window, this element should be incremented to the maximum element in the window. When the left pointer moves to next, an element on the left leaves the window, this case is tricky to think of, please redirect to this [solution](https://leetcode.cn/problems/count-non-decreasing-subarrays-after-k-operations/solutions/3045053/on-xian-xing-zuo-fa-dan-diao-zhan-di-qia-ay5b/). |⭐️⭐️⭐️⭐️⭐️⭐️⭐️|


<br><br>
## Binary Search
### Maximize the minimum/Minimize the maximum
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3399. Smallest Substring With Identical Characters II](https://leetcode.com/problems/smallest-substring-with-identical-characters-ii/description/)  | `Special Case Optimization`    | By considering the "01010101...01" and "101010...10" such patterns separately. |⭐️⭐️⭐️⭐️|
| [3419. Minimize the Maximum Edge Weight of Graph](https://leetcode.com/problems/minimize-the-maximum-edge-weight-of-graph/description/)  | `DFS` | Define upper edge weight is $x$, the greater the $x$, the more possibility to visit all the nodes from node zero. So we can use binary search to find the minimum of the maximum edge weight. For each iteration inside the binary search, create the graph, then use DFS to check if all nodes can be visited.  |⭐️⭐️⭐️⭐|

<br><br>
### Maximum/Minimum


<br><br>
## Monotonous Stack/Monotonous Queue
### Monotonous Stack
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [1944. Number of Visible People in a Queue](https://leetcode.com/problems/number-of-visible-people-in-a-queue/description/)  |  | A guy can see the people on his right, these people's height should be in increasing order and less than the guy's height. Therefore, by iterating the array from right to left, and using a monotonous stack to maintain the increasing rule, the popped elements are the people that the current guy can see.  |⭐️⭐️⭐️⭐️|


<br><br>
## Dynamic Programming
### Grid
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3363. Find the Maximum Number of Fruits Collected](https://leetcode.com/problems/find-the-maximum-number-of-fruits-collected/description/)  | `Brain Teaser` | The first time you read the question, there seem to be three options. But after reading carefully, the children start at (0,0) and have only one path to reach the end. So we only need to consider the other two and they are separate questions. |⭐️⭐️⭐️⭐️|

<br><br>
### Knapsack Problem
#### Multiple Knapsack Problem
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3333. Find the Original Typed String II](https://leetcode.com/problems/find-the-original-typed-string-ii/description/)  | `Reverse Thinking`, `Prefix Optimization` | 1. Parse the final string word to find consecutive runs of the same character. For each run, if it has length $L$, it could have originated from $1$ to $L$ occurrences of that character in the original string. <br> 2. If there are $m$ runs, and the $i-th$ run has length $L_i$, then the unrestricted number of possible original strings is $\text{totalWays} = \prod_{i=1}^m L_i \quad (\text{mod } 10^9+7)$. <br> 3. We only want original strings of length **at least k**. We can: Count how many possible original strings of all lengths (unrestricted) = $\text{totalWays}$, and then subtract the number of possible original strings of length **less than k**. <br> 4. Use DP for counting|⭐️⭐️⭐️⭐️⭐️|


<br><br>
### State Machine DP
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3389. Minimum Operations to Make Character Frequencies Equal](https://leetcode.com/problems/minimum-operations-to-make-character-frequencies-equal/description/)  | `Enumeration` |  1. Not hard to think that the outer iteration is to enumerate the occurrence of a character. But what should it do in the inner? <br> 2. DP is a good way to solve, but defining states is tricky here. Try to find out how to go from specific to general. |⭐️⭐️⭐️⭐️⭐️|


<br><br>
### Digit DP
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3348. Smallest Divisible Digit Product II](https://leetcode.com/problems/smallest-divisible-digit-product-ii/description/)  | `Math` | Digit DP is not used to solve this question. However, the intuition is extended from Digit DP. <br> 1. Decomposition into Prime Factors. Assume there is $k$ number of such factors, and the string $num$ has length $n$. So firstly compare $k$ and $n$ to add pre $0$ to the $num$. Why do we need pre $0$, try to think of $num=999$ and $t=2$ such example. <br> 2. Up to here, you should be familiar with $isLimit$, if you don't, please learn the digit DP template. Do classification: <br>  2.1 Still have limits, but the current step is inside the pre $0$, possible to pick up from $0$ to $9$. <br>  2.2 Still have limits, but the current step is outside the pre $0$, the lower should be greater than $0$. <br>  2.3 No limits, you can pick up from $1$ to $9$. <br> 3. Add $visited$ to check if the 'node' has already been visited, there are two states, $memo[i][j]$ means by formatting the elements start from $i$ to end, is it possible to get a product that is divisible by $j$ <br> That's all the intuition you need, maybe considered the rest with code would be better. |⭐️⭐️⭐️⭐️⭐️⭐️⭐️|


<br><br>
## Data Structure
### Hash Table


<br><br>
### Segment Tree
| Question                                  | Other Related Tags         |    Supplementary   | Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3382. Maximum Area Rectangle With Point Constraints II](https://leetcode.com/problems/maximum-area-rectangle-with-point-constraints-ii/description/)  | `Hash Table`, `Offline + Enumeration`, `Static 2D Points`    |  The way of using Hash Table is similar to "two sum" |  ⭐️⭐️⭐️⭐️⭐️ |
| [G. Unusual Entertainment](https://codeforces.com/problemset/problem/1899/G)  | `DFS Order`, `Offline + Differ`, `Static 2D Points` | 1. Using DFS order to quickly check if one node is the child of one tree. <br> 2. Organizing in advance which query operations should be executed for each index position serves as a “bridge” between offline processing and the concept of difference-based methods. |⭐️⭐️⭐️⭐️⭐️⭐️|

<br><br>
## Math
### Permutation
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3395. Subsequences with a Unique Middle Mode I](https://leetcode.com/problems/subsequences-with-a-unique-middle-mode-i/description/)  | `Prefix`, `Suffix` |  Since the wanted subsequences should meet a length of 5, it is not a big task for us to do the classification. So let's start with iterating the mid element, and assume the mid element's value is 'x': <br><br> 1. Find two elements on the left and two elements on the right that are not equal to 'x'. <br> 2. Find two elements with value 'y' on the left, find another 'x' on the right. <br> 3. Find two elements with value 'y' on the right, find another 'x' on the left. <br>  4. Find one 'y' and one 'x' on the left, and one 'y' on the right. <br>  5. Find one 'y' on the left, find one 'y' and one 'x' on the right. <br><br> Above cases don't satisfy the request, we can calculate the total number of subsequences of size 5 and then minus the above results to get the answer.|⭐️⭐️⭐️⭐️⭐️|

<br><br>
## Greedy Algorithm
### Interval Greedy
#### Interval Covering
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [45. Jump Game II](https://leetcode.com/problems/jump-game-ii/description/)  | `null`    |  null |⭐️⭐️|

<br><br>
## String
### KMP
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [1668. Maximum Repeating Substring](https://leetcode.com/problems/maximum-repeating-substring/description/)  | `DP`  | KMP + DP  |⭐️⭐️⭐️|

<br><br>
### Z Algorithm
Great technique to understand Z - [Z Algorithm demo](https://personal.utdallas.edu/~besp/demo/John2010/z-algorithm.htm)
| Question                                  | Other Related Tags         |    Supplementary   | Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [1668. Maximum Repeating Substring](https://leetcode.com/problems/maximum-repeating-substring/description/)  | `DP`    | Z + DP  |⭐️⭐️⭐️|
| [3292. Minimum Number of Valid Strings to Form Target II](https://leetcode.com/problems/minimum-number-of-valid-strings-to-form-target-ii/description/)  | `Greedy`    | [Interval covering greedy](#interval-covering)  |⭐️⭐️⭐️⭐️|

<br><br>
### Aho-Corasick
| Question                                  | Other Related Tags         |    Supplementary Techniques   | Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3292. Minimum Number of Valid Strings to Form Target II](https://leetcode.com/problems/minimum-number-of-valid-strings-to-form-target-ii/description/)  | `Greedy`    | [Interval covering greedy](#interval-covering) |⭐️⭐️⭐️⭐️|

