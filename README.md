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
| [1944. Number of Visible People in a Queue](https://leetcode.com/problems/number-of-visible-people-in-a-queue/description/)  | `null` | A guy can see the people on his right, these people's height should be in increasing order and less than the guy's height. Therefore, by iterating the array from right to left, and using a monotonous stack to maintain the increasing rule, the popped elements are the people that the current guy can see.  |⭐️⭐️⭐️⭐️|
| [907. Sum of Subarray Minimums](https://leetcode.com/problems/sum-of-subarray-minimums/description/)  | `Contribution Method` `Combinatorics` | Iterating the array, assume currently iterate to $x$, try to find the index of the first element that is smaller than current and define it as $i$, also find the index of the first element that is smaller or equal to current and define it as $j$. The minimum value in range $[i + 1, j - 1]$ should be $nums[x]$. <br> But how to find it? Usually using a monotonous stack is a good way. Since we are looking for the minimums, so try to maintain an increasing order in a monotonous stack. <br> After done that, calculate the combinations with **Multiplicative Principle** - $(x - i) * (j - x)$. |⭐️⭐️⭐️⭐️|

<br><br>
## Graph



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
| [3320. Count The Number of Winning Sequences](https://leetcode.com/problems/count-the-number-of-winning-sequences/description/)  | `null` | Define $memo[i][j][k]$ as a start from $i$ th character, the current award balance is $j$ and pre-summon is $k$, the number of distinct sequences Bob can use to beat Alice. |⭐️⭐️⭐️⭐️⭐️|


<br><br>
### Linear DP
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3434. Maximum Frequency After Subarray Operation](https://leetcode.com/problems/maximum-frequency-after-subarray-operation/description/)  | `Enumeration` | By using Kadane algorithm, Kadane algorithm is a kind of Linear DP, I will find a template later to discuss it. Kadane can calculate the maximum subarray sum of a one-dimensional array efficiently, $dp[i] = \max(dp[i-1] + contribution, nums[i])$. By enumerating the value, since the value's constraints are smaller enough. Try to let as much of the value $i$ become $k$, each value $i$ will contribute to the result, but each value $k$ will consume the contribution. |⭐️⭐️⭐️⭐️|


<br><br>
### Multi-dimensional DP
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3429. Paint House IV](https://leetcode.com/problems/paint-house-iv/description/)  | `null` | Three dimensional, if we currently decide to paint the colour of the $i$ th house, the $n-i+1$th house should also be chosen to paint, so two other states are the left previous painted colour and the right previous painted colour. |⭐️⭐️⭐️⭐️|

<br><br>
### State Compression DP
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3444. Minimum Increments for Target Multiples in an Array](https://leetcode.com/problems/minimum-increments-for-target-multiples-in-an-array/description/)  | `Math` | There are at most only 4 elements inside $target$ array, state compression could be used to solve this problem. By iterating the $nums$ array, for $nums[i]$, consider implementing $n$ times of incrementation for it to become a multiple of some elements inside $target$(Not just one element, it could be multiple). And use a binary bit set to represent the usage condition of $i$ th element in $target$. If already considered the $i$ th element, then set the $i$ th bit from $0$ to $1$. And then follow the state compression DP step to solve it. Also you should know how to quickly calculate LCM. |⭐️⭐️⭐️⭐️|

<br><br>
### Digit DP
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3348. Smallest Divisible Digit Product II](https://leetcode.com/problems/smallest-divisible-digit-product-ii/description/)  | `Math` | Digit DP is not used to solve this question. However, the intuition is extended from Digit DP. <br> 1. Decomposition into Prime Factors. Assume there is $k$ number of such factors, and the string $num$ has length $n$. So firstly compare $k$ and $n$ to add pre $0$ to the $num$. Why do we need pre $0$, try to think of $num=999$ and $t=2$ such example. <br> 2. Up to here, you should be familiar with $isLimit$, if you don't, please learn the digit DP template. Do classification: <br>  2.1 Still have limits, but the current step is inside the pre $0$, possible to pick up from $0$ to $9$. <br>  2.2 Still have limits, but the current step is outside the pre $0$, the lower should be greater than $0$. <br>  2.3 No limits, you can pick up from $1$ to $9$. <br> 3. Add $visited$ to check if the 'node' has already been visited, there are two states, $memo[i][j]$ means by formatting the elements start from $i$ to end, is it possible to get a product that is divisible by $j$ <br> That's all the intuition you need, maybe considered the rest with code would be better. |⭐️⭐️⭐️⭐️⭐️⭐️⭐️|

<br><br>
### Output Tracking
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3441. Minimum Cost Good Caption](https://leetcode.com/problems/minimum-cost-good-caption/description/)  | `Math` | Define $f[i][j]$ as the minimum cost let substring from $i$ to end become good when choosing $j$ at $i$. There are two options: <br> 1. Still choose the same character from the previous one, $f[i][j] = f[i + 1][j] + \lvert s[j] - j \lvert$ <br> 2. Choose a different character from the previous one, and do not break the rule that it should have at least 3 consecutive characters. So $f[i][j] = \min_{k=0}^{25} f[i + 3][k] + \lvert s[j] - j \lvert + \lvert s[j + 1] - j \lvert + \lvert s[j + 2] - j \lvert$. Such an option can only chosen when $i <= n - 6$, $n$ is the length of the string, cause you should leave enough positions for constructing a consecutive sub caption.   |⭐️⭐️⭐️⭐️⭐️⭐️|


<br><br>
## Data Structure
### Dynamic update in a K range
| Question                                  | Other Related Tags         |    Supplementary   | Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [1825. Finding MK Average](https://leetcode.com/problems/finding-mk-average/description/)  | `Priority Queue`  | A template to main a range of elements inside one data set.  |  ⭐️⭐️⭐️⭐️⭐️ |
| [3321. Find X-Sum of All K-Long Subarrays II](https://leetcode.com/problems/find-x-sum-of-all-k-long-subarrays-ii/description/)  | `Priority Queue`, `Sorted Map`  | To be updated. |  ⭐️⭐️⭐️⭐️⭐️ |

<br><br>
### Segment Tree
| Question                                  | Other Related Tags         |    Supplementary   | Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3382. Maximum Area Rectangle With Point Constraints II](https://leetcode.com/problems/maximum-area-rectangle-with-point-constraints-ii/description/)  | `Hash Table`, `Offline + Enumeration`, `Static 2D Points`    |  The way of using Hash Table is similar to "two sum" |  ⭐️⭐️⭐️⭐️⭐️ |
| [G. Unusual Entertainment](https://codeforces.com/problemset/problem/1899/G)  | `DFS Order`, `Offline + Differ`, `Static 2D Points` | 1. Using DFS order to quickly check if one node is the child of one tree. <br> 2. Organizing in advance which query operations should be executed for each index position serves as a “bridge” between offline processing and the concept of difference-based methods. |⭐️⭐️⭐️⭐️⭐️⭐️|

<br><br>
## Math
### Modular Multiplicative Inverse
| Question                                  | Other Related Tags         |    Supplementary   | Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3428. Maximum and Minimum Sums of at Most Size K Subsequences](https://leetcode.com/problems/maximum-and-minimum-sums-of-at-most-size-k-subsequences/description/)  | `Combinatrics` `Quick Pow`    | A template question using modular multiplicative inverse. Know more from [here](https://leetcode.cn/circle/discuss/mDfnkW/) |  ⭐️⭐️⭐️⭐️ |


<br><br>
### Combinatorics
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3395. Subsequences with a Unique Middle Mode I](https://leetcode.com/problems/subsequences-with-a-unique-middle-mode-i/description/)  | `Prefix`, `Suffix` |  Since the wanted subsequences should meet a length of 5, it is not a big task for us to do the classification. So let's start with iterating the mid element, and assume the mid element's value is 'x': <br><br> 1. Find two elements on the left and two elements on the right that are not equal to 'x'. <br> 2. Find two elements with value 'y' on the left, find another 'x' on the right. <br> 3. Find two elements with value 'y' on the right, find another 'x' on the left. <br>  4. Find one 'y' and one 'x' on the left, and one 'y' on the right. <br>  5. Find one 'y' on the left, find one 'y' and one 'x' on the right. <br><br> Above cases don't satisfy the request, we can calculate the total number of subsequences of size 5 and then minus the above results to get the answer.|⭐️⭐️⭐️⭐️⭐️|
| [3430. Maximum and Minimum Sums of at Most Size K Subarrays](https://leetcode.com/problems/maximum-and-minimum-sums-of-at-most-size-k-subarrays/description/)  | `Monotonous Stack` | Extension of this [question](https://leetcode.com/problems/sum-of-subarray-minimums/description/). After knowing the trick to using monotonous stack, this problem mainly deals with combinatorics, I'm still not clear to explain the combinations, so currently just leave the [description](https://leetcode.cn/problems/maximum-and-minimum-sums-of-at-most-size-k-subarrays/solutions/3051552/gong-xian-fa-dan-diao-zhan-pythonjavacgo-9gz3/) here. |  ⭐️⭐️⭐️⭐️⭐️⭐️ |
| [3317. Find the Number of Possible Ways for an Event](https://leetcode.com/problems/find-the-number-of-possible-ways-for-an-event/description/)  | `null` |  1. From $x$ stages, choose $i$ stages and consider the order, which is $A(n,i)$. <br> 2. The number of ways to divide $n$ people into $i$ non-empty sets (where the order of these $i$ sets does not matter), which is $S(n,i)$. <br> 3. Each program has $y$ scoring methods. According to the multiplication principle, $i$ programs would have $y^{i}$ number of scoring methods. |⭐️⭐️⭐️⭐️⭐️|

<br><br>
## Greedy Algorithm
### Keep the first K maximum/minimum
| Question                                  | Other Related Tags         |    Supplementary   |  Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3440. Reschedule Meetings for Maximum Free Time II](https://leetcode.com/problems/reschedule-meetings-for-maximum-free-time-ii/description/)  | `Enumeration`    |  Maintain the three largest empty spaces, ensuring that at least one of them is not adjacent to the meeting. Move the meeting to this empty space. Then enumerate each meeting, and try to move it to other places. |⭐️⭐️⭐️⭐️|

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
A great technique to understand Z - [Z Algorithm demo](https://personal.utdallas.edu/~besp/demo/John2010/z-algorithm.htm)
| Question                                  | Other Related Tags         |    Supplementary   | Difficulty  |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [1668. Maximum Repeating Substring](https://leetcode.com/problems/maximum-repeating-substring/description/)  | `DP`    | Z + DP  |⭐️⭐️⭐️|
| [3292. Minimum Number of Valid Strings to Form Target II](https://leetcode.com/problems/minimum-number-of-valid-strings-to-form-target-ii/description/)  | `Greedy`    | [Interval covering greedy](#interval-covering)  |⭐️⭐️⭐️⭐️|

<br><br>
### Aho-Corasick
| Question                                  | Other Related Tags         |    Supplementary   | Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3292. Minimum Number of Valid Strings to Form Target II](https://leetcode.com/problems/minimum-number-of-valid-strings-to-form-target-ii/description/)  | `Greedy`    | [Interval covering greedy](#interval-covering) |⭐️⭐️⭐️⭐️|

<br><br>
### String Hash
| Question                                  | Other Related Tags         |    Supplementary   | Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3327. Check if DFS Strings Are Palindromes](https://leetcode.com/problems/check-if-dfs-strings-are-palindromes/description/)  | `DFS` | The Main idea is to find an efficient way to check if two strings are equal, so string hash is needed. Try to calculate the pre-order formatted string's hash and the post-order formatted string's hash.  |⭐️⭐️⭐️⭐️⭐️|

<br><br>
## Constructive
| Question                                  | Other Related Tags         |    Supplementary   | Difficulty |
|-------------------------------------------|----------------------------|-------------------------------|-----------|
| [3435. Frequencies of Shortest Supersequences](https://leetcode.com/problems/frequencies-of-shortest-supersequences/description/)  | `DFS`, `Bit Manipulation`, `Greedy` | 1. Greedy: Treat the sequences as the graph, for example, $["ab", "bc", "cb", "ba"]$ for such example to get the shortest supersequence, you can construct a sequence with a character two times and others just one time in the best situation, like put one of character on the left, and another on the right. <br> 2. Bit Manipulation: Make the $i$ th bit $1$ if use it two times, $0$ if use it just one time. <br> 3. DFS: Used to check if the graph has a cycle, if there is a cycle, one of the characters inside the cycle must appear two times.  |⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️|
| [3311. Construct 2D Grid Matching Graph Layout](https://leetcode.com/problems/construct-2d-grid-matching-graph-layout/description/)  | `DFS` | 1. If there is a 2D grid, there are 4 vertices only connected to 2 neighbours, which are placed at the corners. And for vertices on the boundary rather than the corners, these vertices have 3 neighbours. There could also be another kind of vertices on the grid's inner part, they should have 4 neighbours. <br> 2. Are there any special cases? Yes, if the 2D grid only has one row, which becomes a 1D grid, then there are two vertices that only have 1 neighbour and others have 2 neighbours. <br> 3. If it is a 2D grid, find one of the boundaries as the first row of the grid. How exactly get such information? By iterating the whole vertices, until you find one vertice has 2 neighbours, and do layer DFS until find another vertice that has 2 neighbours. After constructing the first row, what about the second row? For the first vertices in the second row, it is actually finding the vertex which hasn't been visited and also is the neighbour of the first vertice in the previous row. For the rest of the vertices, we can check each vertex's left vertex and top vertex, by tracking two vertices' common neighbours to determine it. Implement such a way to construct the rest of the row. <br> 4. If it is a 1D grid, we can just do one DFS for one of the corners vertex to construct it. |⭐️⭐️⭐️⭐️⭐️⭐️⭐️|

