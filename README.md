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

