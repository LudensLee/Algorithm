## 答案
* 迭代
```
/**
 * Definition for singly-linked list.
 * function ListNode(val, next) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.next = (next===undefined ? null : next)
 * }
 */
/**
 * @param {ListNode} head
 * @return {ListNode}
 */
var reverseList = function(head) {
   // 头节点的前一个节点为null，故定义变量prev为null
   let prev = null
   // 定义变量curr保存当前节点的引用值，初始化为传进来的head头节点 
   let curr = head
   //当curr不为空时，循环
   while(curr){
        // 定义变量next保存当前节点未翻转前的next
        const next = curr.next;
        // 将当前节点的next指向上一个节点，则变量prev中的值 
        curr.next = prev;
        // 由于翻转之后，当前的节点为下一个节点的next，故将变量prev的值改为当前的节点
        prev = curr
        //将当前的节点指向下个节点
        curr = next
    }
    // 以输入[1，2，3]为例，那每次循环以prev为头节点的链表为
    // 第一次循环 [1，null]
    // 第二次循环 [2，1，null]
    // 第三次循环 [3，2，1，null]
    // 由于3的next为null 故退出循环体，链表反转结束，return当前的头节点prev
    return prev
};
```