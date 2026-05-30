# 第一次复盘：二叉树与指针

## 1. 错题
今天在做leetcodeT2236判断子节点之和的题时，写了这样一行报错的代码：
`root->left + root->right == root->val`

## 2. 错因
！`root->left` 是一个指针，代表的是地址。
我这行代码，是在试图把左右孩子节点的地址值相加，然后去和根节点的数据值比较是否相等。

## 3. 复盘
**做算术（加上 `->val`）；接地址用纯指针**

**正确代码：**
```c
if (root->left->val + root->right->val == root->val) {
    return true;
}
