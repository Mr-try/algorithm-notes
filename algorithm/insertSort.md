> 插入排序的设计初衷是往有序的数组中快速插入一个新的元素. 它的算法思想是: 把要排序的数组分为了两个部分, 一部分是数组的全部元素(除去待插入的元素), 另一部分是待插入的元素; 先将第一部分排序完成, 然后再插入这个元素. 其中第一部分的排序也是通过再次拆分为两部分来进行的.
插入排序由于操作不尽相同, 可分为 直接插入排序 , 折半插入排序(又称二分插入排序), 链表插入排序 , 希尔排序 

- 直接插入排序
> 它的基本思想是: 将待排序的元素按照大小顺序, 依次插入到一个已经排好序的数组之中, 直到所有的元素都插入进去.
 ```
    Array.prototype.insert_sort=function(){
        var i,j;
        for(i = 1;i<this.length;i++){
            for(j=0;j<i;j++){
                if(this[j]>this[i]){
                    this.splice(j,0,this[i]) // 在j对应的下标后插入i对应的数值
                    this.splice(i+1,1) // 删除i+1下标对应的数值
                }
            }
        }
        return this
    }
 ```