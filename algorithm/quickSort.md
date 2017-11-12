> 快速排序使用分治法（Divide and conquer）策略来把一个序列（list）分为两个子序列（sub-lists）。

步骤为：
- 从数列中挑出一个元素，称为"基准"（pivot），
- 重新排序数列，所有比基准值小的元素摆放在基准前面，所有比基准值大的元素摆在基准后面（相同的数可以到任何一边）。
    在这个分区结束之后，该基准就处于数列的中间位置。这个称为分区（partition）操作。
- 递归地（recursively）把小于基准值元素的子数列和大于基准值元素的子数列排序。

递归到最底部时，数列的大小是零或一，也就是已经排序好了。这个算法一定会结束，因为在每次的迭代（iteration）中，
它至少会把一个元素摆到它最后的位置去。
```
Array.prototype.quick_sort = function(){
   var len = this.length
   if (len <= 1){
       return this.slice(0)
   }
   var left=[]
   var right=[]
   var mid=[this[0]]
   for(var i=1;i<len;i++){
       if(this[i]<mid[0])
        left.push(this[i])
       else
        right.push(this[i])
   }
   return left.quick_sort().concat(mid.concat(right.quck_sort()))
}
```
- 平均时间复杂度O(n*logn) 
- 最好情况O(n*logn) 
- 最坏情况(n^2) 
- 空间复杂度O(nlogn)