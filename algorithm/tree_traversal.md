# 树的遍历

## 树结构

```javascript
// Definition for a Node.
function Node(val, children) {
    this.val = val
    this.left = null
    this.right = null
};
```

## 前序遍历

recursive

```javascript
let res = []
function preorder(root){
    if(root === null){
        return
    }
    res.push(root.val)
    preorder(root.left)
    preorder(root.right)
}
```

iterative(using stack)

```javascript
function preorder(root){
    let arr = [root]
    let res = []
    while(arr.length){
        let node = arr.shift()
        if(node){
            res.push(node.val)
            arr.unshift([root.left, root.right])
        }
    }
    return res
}
```

## 后序遍历

recursive

```javascript
/**
 * @param {Node} root
 * @return {number[]}
 */
var postorder = function(root) {
    let res = []
    function post(root){
        if(root === null){
            return
        }
        root.children.forEach(ele => post(ele))
        res.push(root.val)
    }
    post(root)
    return res
};
```

iterative

```javascript
var postorder = function(root) {
    let res = []
    let arr = [root]
    let i = 0
    while(arr.length){
        let node = arr.pop()
        if(node){
            arr.push(...node.children)
            res.unshift(node.val)
        }
    }
    return res
};
```

## 前序遍历+中序遍历 构建二叉树

## 层序遍历

```javascript
function PrintFromTopToBottom(root)
{
    let queue = [root]
    let res = []
    while(queue.length){
        let node = queue.shift()
        if(node){
            res.push(node.val)
            queue.push(...[node.left, node.right])
        }
    }
    return res
}
```