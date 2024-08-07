# leetcode-learning
用于记录力扣刷题学习的过程。

刷题顺序来自于[代码随想录](https://programmercarl.com/)

# 目录
## 数组
1. [二分查找](1.数组/1.二分查找.md) --- leetcode 704
2. [移除元素](1.数组/2.移除元素.md) --- leetcode 27
3. [有序数组的平方](1.数组/3.有序数组的平方.md) --- leetcode 977
4. [长度最小的子数组](1.数组/4.长度最小的子数组.md) --- leetcode 209
5. [螺旋矩阵Ⅱ](1.数组/5.螺旋矩阵Ⅱ.md) --- leetcode 59

## 链表
1. [移除链表元素](2.链表/1.移除链表元素.md) --- leetcode 203
2. [设计链表](2.链表/2.设计链表.md) --- leetcode 707
3. [反转链表](2.链表/3.反转链表.md) --- leetcode 206
4. [两两交换链表中的节点](2.链表/4.两两交换链表中的节点.md) --- leetcode 24
5. [删除链表的倒数第N个节点](2.链表/5.删除链表的倒数第N个节点.md) --- leetcode 19
6. [链表相交](2.链表/6.链表相交.md) --- leetcode 160
7. [环形链表Ⅱ](2.链表/7.环形链表Ⅱ.md) --- leetcode 142   <font color="red">【重要】</font> 
    - 快慢指针, 快指针2step, 慢指针1step, 环内相遇
    - 新指针从头, 与慢指针相遇, 到达环入口

## 哈希表
1. [哈希结构理论基础](3.哈希表/1.理论基础.md)
2. [有效的字母异位词](3.哈希表/2.有效的字母异位词.md) --- leetcode 242
3. [两个数组的交集](3.哈希表/3.两个数组的交集.md) --- leetcode 349
4. [快乐数](3.哈希表/4.快乐数.md) --- leetcode 202
5. [两数之和](3.哈希表/5.两数之和.md) --- leetcode 1
6. [四数相加Ⅱ](3.哈希表/6.四数相加Ⅱ.md) --- leetcode 454
7. [赎金信](3.哈希表/7.赎金信.md) --- leetcode 383
8. [三数之和](3.哈希表/8.三数之和.md) --- leetcode 15 <font color="red">【重要】</font>
9. [四数之和](3.哈希表/9.四数之和.md) --- leetcode 18 <font color="red">【重要】</font> 
    - 排序, 两个外层循环遍历
    - 内层双指针
    - 注意: 去重, 剪枝， 求和溢出

## 字符串
1. [反转字符串](4.字符串/1.反转字符串.md) --- leetcode 344
2. [反转字符串Ⅱ](4.字符串/2.反转字符串Ⅱ.md) --- leetcode 541
3. [替换数字](4.字符串/3.替换数字.md) --- KamaCoder 54
4. [反转字符串](4.字符串/4.反转字符串.md) --- leetcode 151
5. [右旋字符串](4.字符串/5.右旋字符串.md) --- KamaCoder 55 <font color="red">【重要】</font> 
    - 活用 多次反转
6. [找出字符串中第一个匹配项的下标](4.字符串/6.找出字符串中第一个匹配项的下标.md) --- leetcode 28 <font color="red">【重要】</font>
    - KMP算法
    - 求next数组: 初始化, 不等的情况(回退), 相等的情况(前进), 更新next
    - 主函数: 初始化, 不等的情况(回退), 相等的情况(前进), 判断是否匹配完成
7. [重复的子字符串](4.字符串/7.重复的子字符串.md) --- leetcode 459 <font color="red">【重要】</font>
    - 拼接新字符串: 将 输入字符串 复制一份并拼接, 去头去尾
    - 使用KMP查找 字符串 是否在 新字符串 出现

## 栈与队列
1. [用栈实现队列](5.栈与队列/1.用栈实现队列.md) --- leetcode 232
    - 使用 两个栈 进行转换
2. [用队列实现栈](5.栈与队列/2.用队列实现栈.md) --- leetcode 225
    - 1个队列, pop时循环移出移入
3. [有效的括号](5.栈与队列/3.有效的括号.md) --- leetcode 20
4. [删除字符串中的所有相邻重复项](5.栈与队列/4.删除字符串中的所有相邻重复项.md) --- leetcode 1047
5. [逆波兰表达式求值](5.栈与队列/5.逆波兰表达式求值.md) --- leetcode 150
    - 注意 字符串 转 int: stoi(string), atoi(char*)
6. [滑动窗口最大值](5.栈与队列/6.滑动窗口最大值.md) --- leetcode 239 <font color="red">【重要】</font>
    - 单调队列: 队列内元素保持 单调不增(前面 >= 后面), 队首为最大值
    - 实现push, 在队尾操作 (干掉前面小于当前值的值)
    - 实现pop, 在队首操作
7. [前K个高频元素](5.栈与队列/7.前K个高频元素.md) --- leetcode 347 <font color="red">【重要】</font>
    1. map + sort O(n log n)
        - 遍历记录每个元素出现的次数map
        - map转vector: vector<pair<int, int>> vec(map.begin(), map.end())
        - 定义 比较函数 根据次数排大小
            ```
            bool valueCmp(pair<int, int> a, pair<int, int> b) {
                return a.second > b.second;
            }
            ```
        - sort, 取前K个
    2. 优先级队列(大顶堆/小顶堆) O(n log k)
        - c++ stl: priority_queue
        - 遍历记录每个元素出现的次数map
        - 同上定义 比较函数
            ```
            struct valueCmp {
                bool operator()(pair<int, int> a, pair<int, int> b) {
                    return a.second > b.second;
                }
            };
            ```
        - 维持一个大小为k的优先级队列, 使用小顶堆: priority_queue<pair<int,int>, vector<pair<int,int>>, valueCmp> pq;
        - 遍历map, 返回优先级队列的内容

## 二叉树
1. [二叉树的前序遍历](6.二叉树/1.二叉树的前序遍历.md) --- leetcode 144
2. [二叉树的中序遍历](6.二叉树/2.二叉树的中序遍历.md) --- leetcode 94
3. [二叉树的后序遍历](6.二叉树/3.二叉树的后序遍历.md) --- leetcode 145
    - 迭代: 用栈记录pair<TreeNode*, bool>, 节点指针 和 状态(是否被遍历过)
    - 递归: 确定 终止条件, 返回值, 参数, 处理
4. [二叉树的层序遍历](6.二叉树/4.二叉树的层序遍历.md) --- leetcode 102
5. [二叉树的层序遍历Ⅱ](6.二叉树/5.二叉树的层序遍历Ⅱ.md) --- leetcode 107
6. [二叉树的右视图](6.二叉树/6.二叉树的右视图.md) --- leetcode 199
7. [二叉树的层平均值](6.二叉树/7.二叉树的层平均值.md) --- leetcode 637
8. [N叉树的层序遍历](6.二叉树/8.N叉树的层序遍历.md) --- leetcode 429
9. [在每个树行中找最大值](6.二叉树/9.在每个树行中找最大值.md) --- leetcode 515
10. [填充每个节点的下一个右侧节点指针](6.二叉树/10.填充每个节点的下一个右侧节点指针.md) --- leetcode 116
11. [填充每个节点的下一个右侧节点指针Ⅱ](6.二叉树/11.填充每个节点的下一个右侧节点指针Ⅱ.md) --- leetcode 117
12. [二叉树的最大深度](6.二叉树/12.二叉树的最大深度.md) --- leetcode 104
13. [二叉树的最小深度](6.二叉树/13.二叉树的最小深度.md) --- leetcode 111
14. [翻转二叉树](6.二叉树/14.翻转二叉树.md) --- leetcode 226
15. [对称二叉树](6.二叉树/15.对称二叉树.md) --- leetcode 101
16. [完全二叉树的节点个数](6.二叉树/16.完全二叉树的节点个数.md) --- leetcode 222
17. [平衡二叉树](6.二叉树/17.平衡二叉树.md) --- leetcode 110
18. [二叉树的所有路径](6.二叉树/18.二叉树的所有路径.md) --- leetcode 257
    - 注意: 数字转string: to_string()
19. [左叶子之和](6.二叉树/19.左叶子之和.md) --- leetcode 404
20. [找树左下角的值](6.二叉树/20.找树左下角的值.md) --- leetcode 513
21. [路径总和](6.二叉树/21.路径总和.md) --- leetcode 112
22. [从中序与后序遍历序列构造二叉树](6.二叉树/22.从中序与后序遍历序列构造二叉树.md) --- leetcode 106
23. [最大二叉树](6.二叉树/23.最大二叉树.md) --- leetcode 654
    - 和上一题类似, 切割数组, 只不过本题是穿 子数组的 开始下标 和 结束下标
24. [合并二叉树](6.二叉树/24.合并二叉树.md) --- leetcode 617
    - 同时遍历多个树, 每次将多个树对应的节点一起放入到队列中
25. [二叉搜索树中的搜索](6.二叉树/25.二叉搜索树中的搜索.md) --- leetcode 700
26. [验证二叉搜索树](6.二叉树/26.验证二叉搜索树.md) --- leetcode 98
    -和上一题一样, 利用二叉搜索树的性质: 中序遍历为升序
27. [二叉搜索树的最小绝对差](6.二叉树/27.二叉搜索树的最小绝对差.md) --- leetcode 530
28. [二叉搜索树中的众数](6.二叉树/28.二叉搜索树中的众数.md) --- leetcode 501
    - 背模板, 中序 递归 保存前一个节点指针
29. [二叉树的最近公共祖先](6.二叉树/29.二叉树的最近公共祖先.md) --- leetcode 236
    - 后序 递归
30. [二叉搜索树的最近公共祖先](6.二叉树/30.二叉搜索树的最近公共祖先.md) --- leetcode 235
31. [二叉搜索树中的插入操作](6.二叉树/31.二叉搜索树中的插入操作.md) --- leetcode 701
32. [删除二叉搜索树中的节点](6.二叉树/32.删除二叉搜索树中的节点.md) --- leetcode 450
33. [修剪二叉搜索树](6.二叉树/33.修剪二叉搜索树.md) --- leetcode 669
    - 分别循环删除小于low的节点及其左子树, 大于high的节点及其右子树
34. [将有序数组转换为二叉搜索树](6.二叉树/34.将有序数组转换为二叉搜索树.md) --- leetcode 108
35. [把二叉搜索树转换为累加树](6.二叉树/35.把二叉搜索树转换为累加树.md) --- leetcode 538
    - 右 -> 中 -> 左 递归

## 回溯算法

1. [基础理论+回溯模板](7.回溯算法/1.基础理论+回溯模版.md)
    - 需要背模板
2. [组合](7.回溯算法/2.组合.md) --- leetcode 77
3. [组合总和Ⅲ](7.回溯算法/3.组合总和Ⅲ.md) --- leetcode 216
4. [电话号码的字母组合](7.回溯算法/4.电话号码的字母组合.md) --- leetcode 17
    - 对于const char* cstr = "Hello";
    - std::string s3(cstr, 5); // 从字符数组构造, 构造字符串的前5个
    - std::string s4(5, 'A'); // 重复字符构造, 构造5个 A
    - std::string s6(s2, 1, 3); // 从另一个字符串的子串构造, 从字符串下标为1的字符开始, 构造长度为3的字符串
5. [组合总和](7.回溯算法/5.组合总和.md) --- leetcode 39
6. [组合总和Ⅱ](7.回溯算法/6.组合总和Ⅱ.md) --- leetcode 40
7. [分割回文串](7.回溯算法/7.分割回文串.md) --- leetcode 131
8. [复原IP地址](7.回溯算法/8.复原IP地址.md) --- leetcode 93
9. [子集](7.回溯算法/9.子集.md) --- leetcode 78
10. [子集Ⅱ](7.回溯算法/10.子集Ⅱ.md) --- leetcode 90
    - 上述的题 基本都是 模板 + 排序 + 剪枝 + 去重(循环跳过相同的数)
11. [非递减子序列](7.回溯算法/11.非递减子序列.md) --- leetcode 491
    - 去重: 使用set对每一层迭代 记录 使用过的数字
12. [全排列](7.回溯算法/12.全排列.md) --- leetcode 46
    - 使用一个等长的数组来记录哪些元素访问过, 哪些没访问过
13. [全排列Ⅱ](7.回溯算法/13.全排列Ⅱ.md) --- leetcode 47
    - 注意: 总和了上述两个题
        - 使用一个等长的数组来记录哪些元素访问过, 哪些没访问过
        - 去重: 使用set对每一层迭代 记录 使用过的数字
14. [重新安排行程](7.回溯算法/14.重新安排行程.md) --- leetcode 332
15. [N皇后](7.回溯算法/15.N皇后.md) --- leetcode 332
16. [解数独](7.回溯算法/16.解数独.md) --- leetcode 37

## 贪心算法 [难爆了QAQ]
1. [分发饼干](8.贪心算法/1.分发饼干.md) --- leetcode 455
2. [摆动序列](8.贪心算法/2.摆动序列.md) --- leetcode 376
    - 记录方向改变的次数
3. [最大子数组和](8.贪心算法/3.最大子数组和.md) --- leetcode 53
    - 记录当前的和sum, 根据sum的大小进行更新
4. [买卖股票的最佳时机Ⅱ](8.贪心算法/4.买卖股票的最佳时机Ⅱ.md) --- leetcode 122
5. [跳跃游戏](8.贪心算法/5.跳跃游戏.md) --- leetcode 55
    - 记录能到达的最远位置
6. [跳跃游戏Ⅱ](8.贪心算法/6.跳跃游戏Ⅱ.md) --- leetcode 45
    - 每一跳遍历最大覆盖区域, 判断是否能到终点
7. [K次取反后最大化的数组和](8.贪心算法/7.K次取反后最大化的数组和.md) --- leetcode 1005 
8. [加油站](8.贪心算法/8.加油站.md) --- leetcode 134
    - 油和 > 开销和
9. [分发糖果](8.贪心算法/9.分发糖果.md) --- leetcode 135 
    - 从左向右遍历, 保证右边的一定比左边的大, i 和 i-1 比
    - 从右向左遍历, 保证左边的一定比右边的大, i 和 i+1 比
10. [柠檬水找零](8.贪心算法/10.柠檬水找零.md) --- leetcode 860 

## 动态规划
1. [斐波那契数](9.动态规划/1.斐波那契数.md) --- leetcode 509
2. [爬楼梯](9.动态规划/2.爬楼梯.md) --- leetcode 70
    - dp 记录能到达 当前位置 的路径条数
3. [使用最小花费爬楼梯](9.动态规划/3.使用最小花费爬楼梯.md) --- leetcode 746 
    - dp 记录能到达 当前位置 的最小花费
4. [不同路径](9.动态规划/4.不同路径.md) --- leetcode 62 
    - dp 记录能到达 当前位置 的路径条数
5. [不同路径Ⅱ](9.动态规划/5.不同路径Ⅱ.md) --- leetcode 63 
6. [整数拆分](9.动态规划/6.整数拆分.md) --- leetcode 343
    - dp 记录当前整数的最大乘积, 对于每个整数, 都从1开始进行划分
    - dp[i] = max(dp[i], k*(i-k), k*dp[i-k])
7. [不同的二叉搜索树](9.动态规划/7.不同的二叉搜索树.md) --- leetcode 96 
    - dp 节点个数可以组成的二叉搜索树, 然后以1-n的值分别作根节点
    - dp[i] += dp[j-1] * dp[i-j] j当根节点时, 左子树个数 × 右子树个数
8. [携带研究材料](9.动态规划/8.携带研究材料.md) --- KamaCoder 46 
    - dp[i][j] 表示从第1个到第i个物品中进行任意选取, 在背包容量为j的时候, 能选的最大价值
    - 当前物品 i+1, 要么装不下:  dp[i+1][j] =  dp[i][j]
    - 要么能装下(当前物品价值 和 剩余容量能装下的最大价值):  dp[i+1][j] = values[i+1] + dp[i][j-weights[i]]
    - 能装下的时候, 需要判断装下后的价值 和 不装他的价值 谁更大(能装下也可以不装)
9. [分割等和子集](9.动态规划/9.分割等和子集.md) --- leetcode 416
    - dp[i][j] 表示从 1 到 i 个数中选取, 在背包容量为 j 时的最大值
    - 当背包装下 sum/2 时, 返回true
10. [最后一块石头的重量Ⅱ](9.动态规划/10.最后一块石头的重量Ⅱ.md) --- leetcode 1049
    - dp[i][j] 表示 从第1个到第i个元素进行随机选择, 在和小于等于j时, 能取到的最大值
    - 划分两个数组, 让这两个数组和 的差值 最小即可
11. [目标和](9.动态规划/11.目标和.md) --- leetcode 494 
    - dp[i][j] 表示 在第i个元素进行 + 或者 - 后, 等于 j 的个数
12. [一和零](9.动态规划/12.一和零.md) --- leetcode 474  
    - 用二维数组表示背包容量, dp[i][j][k] 表示从1到i个元素中选择, 在背包 0 容量为 j 和 1 容量为 k 的条件下, 能选择的最大元素个数
13. [携带研究材料](9.动态规划/13.携带研究材料.md) --- KamaCoder 52 
    - 完全背包(一个物品可以无限选): 从当前层更新
    - 01背包(一个物品只能选一次): 从上一层更新 
14. [零钱兑换Ⅱ](9.动态规划/15.零钱兑换Ⅱ.md) --- leetcode 518
    - dp[i][j] 表示从1到i个硬币中选取, 容量恰好为j的组合数
 
## 背包问题模板

### 01背包
通过上一轮计算得出
``` 
for (int i = 1; i < nums + 1; i++) {
    for (int j = 1; j < totalspace + 1; j++) {
        dp[i][j] = dp[i-1][j];
        if (j - weights[i] >= 0) {
            dp[i][j] = max(dp[i][j], dp[i-1][j-weights[i]] + values[i]);  # 看这里
        }
    }
}
```
### 完全背包
通过这一轮计算得出
```
for (int i = 1; i < nums + 1; i++) {
    for (int j = 1; j < totalspace + 1; j++) {
        dp[i][j] = dp[i-1][j];
        if (j - weights[i] >= 0) {
            dp[i][j] = max(dp[i][j], dp[i][j-weights[i]] + values[i]);    # 看这里
        }
    }
}
```

### 多重背包
1. 转换为01背包, 每个物品重复多次
2. 将相同物品的个数 用二进制表示

例如有10个相同的物品, 就可以用 1 2 4 (10-4-2-1)来表示, 即  0 1 1 0表示选了6个物品
```
1   0
2   1
4   1
3   0
```
```
输入格式:
2 1 100
3 3 200
1 4 300
物品1的价值, 物品1的重量, 物品1的个数
vector<int> v, w;  划分后的物品价值和重量
int pos = 0; 记录第几个物品
for (int i = 1; i <= n;i++) {
    int k = 1;          # 从1开始 1 2 4 8 ...
    while(k <= s) {     # s为总数100
        v[pos] = v1 * k;        # 将k个物品变为1个, 因此价格和重量都要乘以k
        w[pos++] = w1 * k;
        s -= k;
        k *= 2;
    }
    if (s) {         # 不为2的n次方, 剩下一位是多少就表示多少即可(多1为能表示的数*2)
        v[pos] = v1 * s;
        w[pos++] = w1 * s;
    }
}
# 此时已转换为01背包, 套01背包的模板即可
```