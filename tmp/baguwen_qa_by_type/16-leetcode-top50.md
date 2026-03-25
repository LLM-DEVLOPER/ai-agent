# LeetCode 高频 50 题速刷手册

> 用途：AI 开发/算法岗面试前刷题冲刺，每题给**题目意思 + 核心思路 + 关键代码**，不求全面，只求面试现场能手写出来。
> 分类：⭐ = 必刷，🔥 = 近期高频，💡 = AI 岗特色题

---

## Part 1：哈希 + 数组（7 题）

### 1. ⭐ 两数之和 [LC-1]
**题目**：给定整数数组和目标值 target，返回两个相加等于 target 的元素下标。
**思路**：哈希表存已见数字，遍历时查 target-nums[i] 是否在表中。O(n)/O(n)。
```python
def twoSum(nums, target):
    seen = {}
    for i, n in enumerate(nums):
        if target - n in seen:
            return [seen[target - n], i]
        seen[n] = i
```

---

### 2. ⭐ 字母异位词分组 [LC-49]
**题目**：给定字符串数组，将所有字母异位词（字母组成相同但顺序不同）归为一组。
**思路**：对每个单词排序后的字符串作为 key，相同 key 归为一组。O(n·k·log k)。
```python
from collections import defaultdict
def groupAnagrams(strs):
    d = defaultdict(list)
    for s in strs:
        d[tuple(sorted(s))].append(s)
    return list(d.values())
```

---

### 3. ⭐ 最长连续序列 [LC-128]
**题目**：给定未排序整数数组，找出最长连续整数序列的长度（如 [1,2,3,4] 长度为 4），要求 O(n)。
**思路**：把所有数放入 set，只从序列起点（num-1 不在 set 中）开始往后数长度。O(n)。
```python
def longestConsecutive(nums):
    s = set(nums)
    res = 0
    for n in s:
        if n - 1 not in s:
            cur = n
            length = 1
            while cur + 1 in s:
                cur += 1
                length += 1
            res = max(res, length)
    return res
```

---

### 4. ⭐ 滑动窗口最大值 [LC-239]
**题目**：给定数组和窗口大小 k，返回每个滑动窗口内最大值组成的数组。
**思路**：单调递减双端队列（deque），队列存索引，队头始终是当前窗口最大值的索引。O(n)。
```python
from collections import deque
def maxSlidingWindow(nums, k):
    dq, res = deque(), []
    for i, n in enumerate(nums):
        while dq and nums[dq[-1]] < n:
            dq.pop()
        dq.append(i)
        if dq[0] < i - k + 1:
            dq.popleft()
        if i >= k - 1:
            res.append(nums[dq[0]])
    return res
```

---

### 5. ⭐ 前 K 个高频元素 [LC-347]
**题目**：给定整数数组，返回出现频率最高的 k 个元素（顺序不限）。
**思路**：Counter 计频，heapq.nlargest 或桶排序（按频率分桶）。O(n log k)。
```python
import heapq
from collections import Counter
def topKFrequent(nums, k):
    count = Counter(nums)
    return heapq.nlargest(k, count.keys(), key=count.get)
```

---

### 6. ⭐ 有效的字母异位词 [LC-242]
**题目**：判断两个字符串是否互为字母异位词（字母相同、出现次数相同，顺序可不同）。
**思路**：Counter 或排序后比较。O(n)。
```python
from collections import Counter
def isAnagram(s, t):
    return Counter(s) == Counter(t)
```

---

### 7. ⭐ 乘积最大子数组 [LC-152]
**题目**：给定整数数组（含负数），找出乘积最大的连续子数组，返回该乘积。
**思路**：同时维护当前最大值和最小值（负数乘以负数变最大）。
```python
def maxProduct(nums):
    res = max_p = min_p = nums[0]
    for n in nums[1:]:
        max_p, min_p = max(n, max_p*n, min_p*n), min(n, max_p*n, min_p*n)
        res = max(res, max_p)
    return res
```

---

## Part 2：双指针 + 滑动窗口（5 题）

### 8. ⭐ 无重复字符的最长子串 [LC-3]
**题目**：给定字符串，找出不含重复字符的最长子串的长度。
**思路**：滑动窗口 + set，右指针扩展，遇到重复字符左指针收缩。O(n)。
```python
def lengthOfLongestSubstring(s):
    seen = set()
    l = res = 0
    for r, c in enumerate(s):
        while c in seen:
            seen.remove(s[l])
            l += 1
        seen.add(c)
        res = max(res, r - l + 1)
    return res
```

---

### 9. ⭐ 三数之和 [LC-15]
**题目**：给定整数数组，找出所有不重复的三元组 [a, b, c]，使得 a + b + c = 0。
**思路**：排序后，固定第一个数，剩下两数用双指针。注意去重（跳过相同元素）。O(n²)。
```python
def threeSum(nums):
    nums.sort()
    res = []
    for i, n in enumerate(nums):
        if i > 0 and n == nums[i-1]: continue
        l, r = i+1, len(nums)-1
        while l < r:
            s = n + nums[l] + nums[r]
            if s == 0:
                res.append([n, nums[l], nums[r]])
                while l < r and nums[l] == nums[l+1]: l += 1
                while l < r and nums[r] == nums[r-1]: r -= 1
                l += 1; r -= 1
            elif s < 0: l += 1
            else: r -= 1
    return res
```

---

### 10. ⭐ 接雨水 [LC-42]
**题目**：给定柱状图高度数组，计算柱子之间能接住多少单位雨水。
**思路**：双指针，左右各维护一个最大高度，较小侧决定当前能接的水量。O(n)。
```python
def trap(height):
    l, r = 0, len(height) - 1
    maxL = maxR = res = 0
    while l < r:
        if height[l] <= height[r]:
            maxL = max(maxL, height[l])
            res += maxL - height[l]
            l += 1
        else:
            maxR = max(maxR, height[r])
            res += maxR - height[r]
            r -= 1
    return res
```

---

### 11. ⭐ 最小覆盖子串 [LC-76]
**题目**：给定字符串 s 和 t，在 s 中找出包含 t 所有字符的最短子串（含重复字符要求）。
**思路**：滑动窗口，记录 need 和 window 字符计数，have/need 计数控制窗口收缩时机。O(n)。
```python
from collections import Counter
def minWindow(s, t):
    need = Counter(t)
    window = {}
    have, total = 0, len(need)
    res, res_len = [-1, -1], float('inf')
    l = 0
    for r, c in enumerate(s):
        window[c] = window.get(c, 0) + 1
        if c in need and window[c] == need[c]:
            have += 1
        while have == total:
            if r - l + 1 < res_len:
                res_len = r - l + 1
                res = [l, r]
            window[s[l]] -= 1
            if s[l] in need and window[s[l]] < need[s[l]]:
                have -= 1
            l += 1
    l, r = res
    return s[l:r+1] if res_len != float('inf') else ""
```

---

### 12. ⭐ 盛最多水的容器 [LC-11]
**题目**：给定高度数组，选两根柱子和 x 轴围成容器，求能盛放的最大水量。
**思路**：双指针，每次移动较短的那侧（移动较长的侧只会让容量更小）。O(n)。
```python
def maxArea(height):
    l, r = 0, len(height) - 1
    res = 0
    while l < r:
        res = max(res, min(height[l], height[r]) * (r - l))
        if height[l] < height[r]: l += 1
        else: r -= 1
    return res
```

---

## Part 3：链表（5 题）

### 13. ⭐ 反转链表 [LC-206]
**题目**：给定单链表头节点，反转整个链表并返回新头节点。
**思路**：三指针迭代（prev, curr, next），或递归。O(n)/O(1)。
```python
def reverseList(head):
    prev = None
    curr = head
    while curr:
        nxt = curr.next
        curr.next = prev
        prev = curr
        curr = nxt
    return prev
```

---

### 14. ⭐ 合并两个有序链表 [LC-21]
**题目**：将两个升序链表合并为一个新的升序链表，返回合并后的头节点。
**思路**：哨兵节点，双指针比较合并。O(m+n)。
```python
def mergeTwoLists(l1, l2):
    dummy = cur = ListNode(0)
    while l1 and l2:
        if l1.val <= l2.val:
            cur.next = l1; l1 = l1.next
        else:
            cur.next = l2; l2 = l2.next
        cur = cur.next
    cur.next = l1 or l2
    return dummy.next
```

---

### 15. ⭐ 环形链表 II（找入口）[LC-142]
**题目**：给定链表，如果存在环，返回环的入口节点；不存在则返回 null。
**思路**：快慢指针找相遇点，再从 head 和相遇点各走一步，再次相遇即为入口。
```python
def detectCycle(head):
    slow = fast = head
    while fast and fast.next:
        slow = slow.next
        fast = fast.next.next
        if slow == fast:
            p = head
            while p != slow:
                p = p.next
                slow = slow.next
            return p
    return None
```

---

### 16. ⭐ K 个一组翻转链表 [LC-25]
**题目**：每 k 个节点为一组反转链表，不足 k 个的节点保持原顺序。
**思路**：每次取 k 个节点翻转，连接前后段，注意剩余不足 k 个时不翻转。O(n)。
```python
def reverseKGroup(head, k):
    dummy = ListNode(0, head)
    prev = dummy
    while True:
        kth = prev
        for _ in range(k):
            kth = kth.next
            if not kth: return dummy.next
        curr, tail = prev.next, prev.next
        nxt = kth.next
        p = None
        while curr != nxt:
            tmp = curr.next
            curr.next = p
            p = curr
            curr = tmp
        prev.next = kth
        tail.next = nxt
        prev = tail
```

---

### 17. ⭐ LRU 缓存 [LC-146] 💡
**题目**：实现 LRU（最近最少使用）缓存，支持 get(key) 和 put(key, value) 操作，均 O(1)。容量满时淘汰最久未使用的键。
**思路**：OrderedDict（Python）或自实现 HashMap + 双向链表。get/put 均 O(1)。
```python
from collections import OrderedDict
class LRUCache:
    def __init__(self, capacity):
        self.cap = capacity
        self.cache = OrderedDict()
    def get(self, key):
        if key not in self.cache: return -1
        self.cache.move_to_end(key)
        return self.cache[key]
    def put(self, key, value):
        if key in self.cache:
            self.cache.move_to_end(key)
        self.cache[key] = value
        if len(self.cache) > self.cap:
            self.cache.popitem(last=False)
```

---

## Part 4：栈与队列（5 题）

### 18. ⭐ 有效的括号 [LC-20]
**题目**：给定只含括号的字符串，判断括号是否有效（每种括号必须正确配对和闭合）。
**思路**：栈，遇到左括号入栈，遇到右括号判断栈顶是否匹配。
```python
def isValid(s):
    stack = []
    pairs = {')':'(', ']':'[', '}':'{'}
    for c in s:
        if c in pairs:
            if not stack or stack[-1] != pairs[c]: return False
            stack.pop()
        else:
            stack.append(c)
    return not stack
```

---

### 19. ⭐ 每日温度 [LC-739]
**题目**：给定每天温度数组，对每天返回"需要再等几天温度才会升高"，若之后不会升高则为 0。
**思路**：单调递减栈，存索引。遇到比栈顶大的元素，弹出并计算距离。
```python
def dailyTemperatures(temperatures):
    res = [0] * len(temperatures)
    stack = []  # 存索引
    for i, t in enumerate(temperatures):
        while stack and temperatures[stack[-1]] < t:
            idx = stack.pop()
            res[idx] = i - idx
        stack.append(i)
    return res
```

---

### 20. ⭐ 最小栈 [LC-155]
**题目**：设计支持 push、pop、top、getMin 操作的栈，其中 getMin 必须是 O(1)。
**思路**：辅助栈同步记录当前最小值，push 时同步 min，pop 时同步 pop。
```python
class MinStack:
    def __init__(self):
        self.stack = []
        self.min_stack = []
    def push(self, val):
        self.stack.append(val)
        self.min_stack.append(min(val, self.min_stack[-1] if self.min_stack else val))
    def pop(self):
        self.stack.pop(); self.min_stack.pop()
    def top(self): return self.stack[-1]
    def getMin(self): return self.min_stack[-1]
```

---

### 21. 🔥 用栈实现队列 [LC-232]
**题目**：只使用两个栈，实现先进先出（FIFO）队列，支持 push、pop、peek、empty 操作。
**思路**：两个栈，in_stack 和 out_stack。push 到 in_stack，pop/peek 时若 out_stack 空则把 in_stack 全倒进去。均摊 O(1)。
```python
class MyQueue:
    def __init__(self):
        self.in_s, self.out_s = [], []
    def push(self, x): self.in_s.append(x)
    def _move(self):
        if not self.out_s:
            while self.in_s: self.out_s.append(self.in_s.pop())
    def pop(self): self._move(); return self.out_s.pop()
    def peek(self): self._move(); return self.out_s[-1]
    def empty(self): return not self.in_s and not self.out_s
```

---

### 22. ⭐ 柱状图中最大的矩形 [LC-84]
**题目**：给定柱状图的高度数组，求可以勾勒出来的最大矩形面积（矩形必须在柱状图范围内）。
**思路**：单调递增栈，存索引。每次弹出时计算以该高度为最短边的矩形面积。
```python
def largestRectangleArea(heights):
    stack = [-1]
    res = 0
    heights.append(0)
    for i, h in enumerate(heights):
        while stack[-1] != -1 and heights[stack[-1]] >= h:
            height = heights[stack.pop()]
            width = i - stack[-1] - 1
            res = max(res, height * width)
        stack.append(i)
    return res
```

---

## Part 5：二叉树（7 题）

### 23. ⭐ 二叉树的层序遍历 [LC-102]
**题目**：给定二叉树根节点，返回其节点值的层序遍历（从左到右，逐层）结果。
**思路**：BFS，队列逐层处理，每层开始时记录当前层节点数。
```python
from collections import deque
def levelOrder(root):
    if not root: return []
    res, q = [], deque([root])
    while q:
        level = []
        for _ in range(len(q)):
            node = q.popleft()
            level.append(node.val)
            if node.left: q.append(node.left)
            if node.right: q.append(node.right)
        res.append(level)
    return res
```

---

### 24. ⭐ 二叉树的最大深度 [LC-104]
**题目**：给定二叉树，返回从根节点到最远叶子节点的最大深度（层数）。
**思路**：递归，max(left_depth, right_depth) + 1。
```python
def maxDepth(root):
    if not root: return 0
    return 1 + max(maxDepth(root.left), maxDepth(root.right))
```

---

### 25. ⭐ 验证二叉搜索树 [LC-98]
**题目**：给定二叉树，验证它是否是有效的二叉搜索树（左子树所有节点 < 根 < 右子树所有节点）。
**思路**：递归传递 min/max 约束，左子树节点必须 < 当前节点，右子树节点必须 > 当前节点。
```python
def isValidBST(root, lo=float('-inf'), hi=float('inf')):
    if not root: return True
    if root.val <= lo or root.val >= hi: return False
    return isValidBST(root.left, lo, root.val) and isValidBST(root.right, root.val, hi)
```

---

### 26. ⭐ 二叉树的直径 [LC-543]
**题目**：给定二叉树，求任意两节点之间路径长度的最大值（路径不需要经过根节点）。
**思路**：后序遍历，对每个节点计算左右子树最大深度之和更新答案，返回该节点的最大深度。
```python
def diameterOfBinaryTree(root):
    res = 0
    def dfs(node):
        nonlocal res
        if not node: return 0
        l, r = dfs(node.left), dfs(node.right)
        res = max(res, l + r)
        return 1 + max(l, r)
    dfs(root)
    return res
```

---

### 27. ⭐ 从前序与中序遍历序列构造二叉树 [LC-105]
**题目**：给定二叉树的前序遍历和中序遍历结果，重建并返回原二叉树。
**思路**：前序第一个元素是根，在中序中找根的位置，左右递归。用哈希表加速查找。
```python
def buildTree(preorder, inorder):
    idx = {v: i for i, v in enumerate(inorder)}
    def helper(pre_l, pre_r, in_l, in_r):
        if pre_l > pre_r: return None
        root_val = preorder[pre_l]
        root = TreeNode(root_val)
        m = idx[root_val]
        left_size = m - in_l
        root.left = helper(pre_l+1, pre_l+left_size, in_l, m-1)
        root.right = helper(pre_l+left_size+1, pre_r, m+1, in_r)
        return root
    return helper(0, len(preorder)-1, 0, len(inorder)-1)
```

---

### 28. ⭐ 二叉树中的最大路径和 [LC-124]
**题目**：给定二叉树，路径可以经过任意节点（不需要过根），求路径上节点值之和的最大值。
**思路**：后序遍历，对每个节点计算包含该节点的最大路径和（可以只取一侧），更新全局最大值，返回单侧最大值。
```python
def maxPathSum(root):
    res = [root.val]
    def dfs(node):
        if not node: return 0
        l = max(dfs(node.left), 0)
        r = max(dfs(node.right), 0)
        res[0] = max(res[0], node.val + l + r)
        return node.val + max(l, r)
    dfs(root)
    return res[0]
```

---

### 29. ⭐ 二叉树的右视图 [LC-199]
**题目**：从右侧观察二叉树，返回每层最右侧可见的节点值列表（从上到下）。
**思路**：BFS 层序遍历，每层最后一个节点就是右视图。
```python
from collections import deque
def rightSideView(root):
    if not root: return []
    res, q = [], deque([root])
    while q:
        size = len(q)
        for i in range(size):
            node = q.popleft()
            if i == size - 1: res.append(node.val)
            if node.left: q.append(node.left)
            if node.right: q.append(node.right)
    return res
```

---

## Part 6：动态规划（7 题）

### 30. ⭐ 爬楼梯 [LC-70]
**题目**：每次可以走 1 或 2 步，爬 n 阶楼梯共有多少种不同的走法。
**思路**：dp[i] = dp[i-1] + dp[i-2]，斐波那契。
```python
def climbStairs(n):
    a, b = 1, 1
    for _ in range(n - 1):
        a, b = b, a + b
    return b
```

---

### 31. ⭐ 最长递增子序列 [LC-300]
**题目**：给定整数数组，找出最长严格递增子序列（子序列不要求连续）的长度。
**思路**：O(n²) DP，或 O(n log n) 贪心+二分（维护一个尽量小的递增序列 tails）。
```python
import bisect
def lengthOfLIS(nums):
    tails = []
    for n in nums:
        pos = bisect.bisect_left(tails, n)
        if pos == len(tails): tails.append(n)
        else: tails[pos] = n
    return len(tails)
```

---

### 32. ⭐ 零钱兑换 [LC-322]
**题目**：给定不同面值的硬币和总金额，求凑成总金额所需最少硬币数；无法凑成返回 -1。
**思路**：完全背包，dp[i] = min(dp[i], dp[i-coin]+1)。
```python
def coinChange(coins, amount):
    dp = [float('inf')] * (amount + 1)
    dp[0] = 0
    for coin in coins:
        for i in range(coin, amount + 1):
            dp[i] = min(dp[i], dp[i - coin] + 1)
    return dp[amount] if dp[amount] != float('inf') else -1
```

---

### 33. ⭐ 最长公共子序列 [LC-1143]
**题目**：给定两个字符串 text1 和 text2，返回它们最长公共子序列（LCS）的长度（子序列不要求连续）。
**思路**：经典 DP，dp[i][j] 表示 text1[:i] 和 text2[:j] 的 LCS 长度。
```python
def longestCommonSubsequence(text1, text2):
    m, n = len(text1), len(text2)
    dp = [[0] * (n + 1) for _ in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if text1[i-1] == text2[j-1]:
                dp[i][j] = dp[i-1][j-1] + 1
            else:
                dp[i][j] = max(dp[i-1][j], dp[i][j-1])
    return dp[m][n]
```

---

### 34. ⭐ 编辑距离 [LC-72]
**题目**：给定两个字符串 word1 和 word2，求将 word1 转换成 word2 所需的最少操作数（插入/删除/替换）。
**思路**：dp[i][j] = 将 word1[:i] 转成 word2[:j] 的最少操作。三种操作：删除/插入/替换。
```python
def minDistance(word1, word2):
    m, n = len(word1), len(word2)
    dp = [[0] * (n + 1) for _ in range(m + 1)]
    for i in range(m + 1): dp[i][0] = i
    for j in range(n + 1): dp[0][j] = j
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if word1[i-1] == word2[j-1]:
                dp[i][j] = dp[i-1][j-1]
            else:
                dp[i][j] = 1 + min(dp[i-1][j], dp[i][j-1], dp[i-1][j-1])
    return dp[m][n]
```

---

### 35. ⭐ 打家劫舍 [LC-198]
**题目**：沿街房屋排成一排，不能偷相邻的房屋，给定各房屋金额，求能偷到的最大金额。
**思路**：dp[i] = max(dp[i-1], dp[i-2] + nums[i])，滚动数组优化到 O(1) 空间。
```python
def rob(nums):
    prev2 = prev1 = 0
    for n in nums:
        prev2, prev1 = prev1, max(prev1, prev2 + n)
    return prev1
```

---

### 36. 🔥 单词拆分 [LC-139]
**题目**：给定字符串 s 和单词字典，判断 s 是否可以被字典中的单词拆分（单词可重复使用）。
**思路**：dp[i] = s[:i] 是否可以被字典中的单词拆分；枚举所有分割点 j，检查 s[j:i] 是否在字典中。
```python
def wordBreak(s, wordDict):
    words = set(wordDict)
    dp = [False] * (len(s) + 1)
    dp[0] = True
    for i in range(1, len(s) + 1):
        for j in range(i):
            if dp[j] and s[j:i] in words:
                dp[i] = True
                break
    return dp[-1]
```

---

## Part 7：图与 BFS/DFS（5 题）

### 37. ⭐ 岛屿数量 [LC-200]
**题目**：给定由 '1'（陆地）和 '0'（水）组成的二维网格，计算其中岛屿的数量（陆地相连为一个岛屿）。
**思路**：DFS，遇到 '1' 就 DFS 把整个岛屿标记为已访问（改成 '0'），计数加一。O(m×n)。
```python
def numIslands(grid):
    def dfs(i, j):
        if i < 0 or i >= len(grid) or j < 0 or j >= len(grid[0]) or grid[i][j] != '1': return
        grid[i][j] = '0'
        dfs(i+1,j); dfs(i-1,j); dfs(i,j+1); dfs(i,j-1)
    count = 0
    for i in range(len(grid)):
        for j in range(len(grid[0])):
            if grid[i][j] == '1':
                dfs(i, j)
                count += 1
    return count
```

---

### 38. ⭐ 课程表（拓扑排序）[LC-207]
**题目**：给定 n 门课和依赖关系（先修课列表），判断能否完成所有课程（即依赖图中是否有环）。
**思路**：构建入度表和邻接表，BFS（Kahn 算法）从入度为 0 的节点开始，判断是否有环。
```python
from collections import deque
def canFinish(numCourses, prerequisites):
    indegree = [0] * numCourses
    graph = [[] for _ in range(numCourses)]
    for a, b in prerequisites:
        graph[b].append(a)
        indegree[a] += 1
    q = deque(i for i in range(numCourses) if indegree[i] == 0)
    count = 0
    while q:
        node = q.popleft()
        count += 1
        for nei in graph[node]:
            indegree[nei] -= 1
            if indegree[nei] == 0: q.append(nei)
    return count == numCourses
```

---

### 39. ⭐ 单词接龙（BFS 最短路）[LC-127]
**题目**：从 beginWord 到 endWord，每次只改变一个字母且中间词必须在字典中，求最短变换序列的长度。
**思路**：BFS，每次对当前单词每个位置替换 a-z，如果在 word_set 中则入队。
```python
from collections import deque
def ladderLength(beginWord, endWord, wordList):
    word_set = set(wordList)
    if endWord not in word_set: return 0
    q = deque([(beginWord, 1)])
    visited = {beginWord}
    while q:
        word, steps = q.popleft()
        for i in range(len(word)):
            for c in 'abcdefghijklmnopqrstuvwxyz':
                nw = word[:i] + c + word[i+1:]
                if nw == endWord: return steps + 1
                if nw in word_set and nw not in visited:
                    visited.add(nw)
                    q.append((nw, steps + 1))
    return 0
```

---

### 40. ⭐ 腐烂的橘子（多源 BFS）[LC-994]
**题目**：网格中有新鲜/腐烂橘子，腐烂橘子每分钟感染相邻新鲜橘子，求所有橘子腐烂所需最少分钟数。
**思路**：多源 BFS，所有腐烂橘子同时入队，每轮 BFS 代表 1 分钟，统计最终是否还有新鲜橘子。
```python
from collections import deque
def orangesRotting(grid):
    m, n = len(grid), len(grid[0])
    q = deque()
    fresh = 0
    for i in range(m):
        for j in range(n):
            if grid[i][j] == 2: q.append((i, j, 0))
            elif grid[i][j] == 1: fresh += 1
    time = 0
    while q:
        i, j, t = q.popleft()
        for di, dj in [(1,0),(-1,0),(0,1),(0,-1)]:
            ni, nj = i+di, j+dj
            if 0<=ni<m and 0<=nj<n and grid[ni][nj]==1:
                grid[ni][nj] = 2
                fresh -= 1
                time = t + 1
                q.append((ni, nj, t+1))
    return time if fresh == 0 else -1
```

---

### 41. 🔥 被围绕的区域 [LC-130]
**题目**：矩阵中有 'X' 和 'O'，将所有被 'X' 完全包围（不与边界相连）的 'O' 替换为 'X'。
**思路**：从边界上的 'O' 开始 DFS/BFS 标记为 'S'（安全），最后 'O' 变 'X'，'S' 变 'O'。
```python
def solve(board):
    if not board: return
    m, n = len(board), len(board[0])
    def dfs(i, j):
        if i < 0 or i >= m or j < 0 or j >= n or board[i][j] != 'O': return
        board[i][j] = 'S'
        dfs(i+1,j); dfs(i-1,j); dfs(i,j+1); dfs(i,j-1)
    for i in range(m):
        for j in range(n):
            if (i in [0, m-1] or j in [0, n-1]) and board[i][j] == 'O':
                dfs(i, j)
    for i in range(m):
        for j in range(n):
            if board[i][j] == 'O': board[i][j] = 'X'
            elif board[i][j] == 'S': board[i][j] = 'O'
```

---

## Part 8：回溯（4 题）

### 42. ⭐ 全排列 [LC-46]
**题目**：给定不含重复数字的整数数组，返回所有可能的全排列。
**思路**：回溯，used 数组标记已用元素，到达叶子节点时记录结果。
```python
def permute(nums):
    res = []
    def backtrack(path, used):
        if len(path) == len(nums):
            res.append(path[:])
            return
        for i, n in enumerate(nums):
            if used[i]: continue
            used[i] = True
            path.append(n)
            backtrack(path, used)
            path.pop()
            used[i] = False
    backtrack([], [False] * len(nums))
    return res
```

---

### 43. ⭐ 括号生成 [LC-22]
**题目**：给定 n 对括号，生成所有有效的括号组合（每种括号必须正确闭合）。
**思路**：回溯，维护 left 和 right 计数，left < n 时可加 '('，right < left 时可加 ')'。
```python
def generateParenthesis(n):
    res = []
    def bt(s, l, r):
        if len(s) == 2 * n:
            res.append(s); return
        if l < n: bt(s + '(', l+1, r)
        if r < l: bt(s + ')', l, r+1)
    bt('', 0, 0)
    return res
```

---

### 44. ⭐ 子集 [LC-78]
**题目**：给定不含重复元素的整数数组，返回所有可能的子集（幂集），结果不能重复。
**思路**：回溯，每次从 start 开始选，可以不选（直接记录当前 path）。
```python
def subsets(nums):
    res = []
    def bt(start, path):
        res.append(path[:])
        for i in range(start, len(nums)):
            path.append(nums[i])
            bt(i + 1, path)
            path.pop()
    bt(0, [])
    return res
```

---

### 45. ⭐ 组合总和 [LC-39]
**题目**：给定无重复元素的候选数组，找出所有和为 target 的组合（同一数字可无限次使用）。
**思路**：回溯，元素可重复使用，每次从 start 开始，target 减到 0 时记录结果。
```python
def combinationSum(candidates, target):
    res = []
    def bt(start, path, remain):
        if remain == 0: res.append(path[:]); return
        if remain < 0: return
        for i in range(start, len(candidates)):
            path.append(candidates[i])
            bt(i, path, remain - candidates[i])
            path.pop()
    bt(0, [], target)
    return res
```

---

## Part 9：二分查找（3 题）

### 46. ⭐ 搜索旋转排序数组 [LC-33]
**题目**：原本升序的数组在某个位置被旋转，给定目标值，返回其下标；不存在返回 -1，要求 O(log n)。
**思路**：二分，先判断哪侧有序，再判断 target 在哪侧。
```python
def search(nums, target):
    l, r = 0, len(nums) - 1
    while l <= r:
        mid = (l + r) // 2
        if nums[mid] == target: return mid
        if nums[l] <= nums[mid]:  # 左侧有序
            if nums[l] <= target < nums[mid]: r = mid - 1
            else: l = mid + 1
        else:  # 右侧有序
            if nums[mid] < target <= nums[r]: l = mid + 1
            else: r = mid - 1
    return -1
```

---

### 47. ⭐ 寻找旋转排序数组中的最小值 [LC-153]
**题目**：给定旋转后的升序数组（无重复元素），找出其中的最小值，要求 O(log n)。
**思路**：二分，若 nums[mid] > nums[r]，最小值在右侧；否则在左侧（含 mid）。
```python
def findMin(nums):
    l, r = 0, len(nums) - 1
    while l < r:
        mid = (l + r) // 2
        if nums[mid] > nums[r]: l = mid + 1
        else: r = mid
    return nums[l]
```

---

### 48. ⭐ 在排序数组中查找元素的第一个和最后一个位置 [LC-34]
**题目**：给定升序数组和目标值，找出目标值在数组中的起始和结束位置；不存在返回 [-1, -1]，要求 O(log n)。
**思路**：两次二分，一次找左边界，一次找右边界。
```python
import bisect
def searchRange(nums, target):
    l = bisect.bisect_left(nums, target)
    r = bisect.bisect_right(nums, target) - 1
    if l <= r and l < len(nums) and nums[l] == target:
        return [l, r]
    return [-1, -1]
```

---

## Part 10：AI 岗特色题（2 题）

### 49. 💡 并发限制调度器（AI 岗高频）
**题目**：实现一个调度器，限制最多同时运行 N 个任务，超出部分排队等待，适用于并发调用多个工具/模型 API 的场景。
**思路**：asyncio.Semaphore 控制并发数，使用 asyncio.gather 并行提交所有任务。
```python
import asyncio

class Scheduler:
    def __init__(self, max_concurrent):
        self.sem = asyncio.Semaphore(max_concurrent)

    async def run(self, tasks):
        async def wrapped(task):
            async with self.sem:
                return await task
        return await asyncio.gather(*[wrapped(t) for t in tasks])

# 同步版（线程）
from concurrent.futures import ThreadPoolExecutor, as_completed
def run_with_limit(fns, max_workers=5):
    results = []
    with ThreadPoolExecutor(max_workers=max_workers) as executor:
        futures = [executor.submit(fn) for fn in fns]
        for f in as_completed(futures):
            results.append(f.result())
    return results
```

---

### 50. 💡 令牌桶限流器（AI 岗高频）
**题目**：实现线程安全的令牌桶限流器，支持设置补充速率（tokens/s）和桶容量，用于控制对 LLM API 的调用速率（TPM 限流）。
**思路**：每次 acquire 前先按时间差补充令牌，判断令牌是否充足，用 threading.Lock 保证线程安全。
```python
import time
import threading

class TokenBucket:
    def __init__(self, rate, capacity):
        """rate: 每秒补充令牌数, capacity: 桶容量"""
        self.rate = rate
        self.capacity = capacity
        self.tokens = capacity
        self.last_time = time.time()
        self.lock = threading.Lock()

    def acquire(self, tokens=1):
        with self.lock:
            now = time.time()
            # 补充令牌
            elapsed = now - self.last_time
            self.tokens = min(self.capacity, self.tokens + elapsed * self.rate)
            self.last_time = now
            # 判断是否足够
            if self.tokens >= tokens:
                self.tokens -= tokens
                return True
            return False

    def wait_and_acquire(self, tokens=1):
        while not self.acquire(tokens):
            time.sleep(0.01)

# 使用：
# bucket = TokenBucket(rate=10, capacity=100)  # 每秒 10 tokens，最多 100
# if bucket.acquire():
#     call_llm_api()
```

---

## 速查表

| 分类 | 题目 | 关键数据结构 | 复杂度 |
|------|------|------------|--------|
| **哈希** | 两数之和 | HashMap | O(n) |
| **哈希** | 最长连续序列 | Set | O(n) |
| **单调栈** | 每日温度 | 递减栈 | O(n) |
| **单调栈** | 滑动窗口最大值 | 单调队列 | O(n) |
| **双指针** | 接雨水 | 双指针 | O(n) |
| **滑动窗口** | 最小覆盖子串 | HashMap | O(n) |
| **链表** | LRU 缓存 | OrderedDict/双向链表 | O(1) |
| **链表** | 环形链表 | 快慢指针 | O(n) |
| **树** | 二叉树直径 | 后序 DFS | O(n) |
| **树** | 最大路径和 | 后序 DFS | O(n) |
| **DP** | 最长递增子序列 | 贪心+二分 | O(n log n) |
| **DP** | 零钱兑换 | 完全背包 | O(n×amount) |
| **DP** | 编辑距离 | 二维 DP | O(m×n) |
| **图** | 课程表 | 拓扑排序 BFS | O(V+E) |
| **图** | 腐烂橘子 | 多源 BFS | O(m×n) |
| **回溯** | 全排列 | used 数组 | O(n×n!) |
| **回溯** | 组合总和 | 剪枝回溯 | O(2^n) |
| **二分** | 旋转数组搜索 | 判断有序侧 | O(log n) |
| **AI 特色** | 并发调度器 | Semaphore | O(1) |
| **AI 特色** | 令牌桶限流 | 计数器+锁 | O(1) |

---

## 面试时写代码的流程（必读）

1. **先复述题意**："我理解输入是...，输出是...，边界条件是空数组/负数/重复元素，对吗？"
2. **说思路**："我的思路是用...数据结构，时间复杂度 O(...)，空间 O(...)"
3. **写代码时边说边写**，说关键逻辑而不是每行注释
4. **写完主动 walk through**：用一个具体例子跑一遍，找边界 bug
5. **被追问"能否优化"**：先说当前方案的瓶颈，再说优化方向
6. **完全卡住时**：直接说"我先写暴力解法"，暴力能写出来比沉默强得多
