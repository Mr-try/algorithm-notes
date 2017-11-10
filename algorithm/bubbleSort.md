> Chrome 的 Array.prototype.sort使用了快速排序

> 冒泡排序需要嵌套两个循环，其中外层循环移动游标，内层循环遍历游标之后或之前的元素，通过两两交换的方式，每次只确保该循环结束位置排序正确，然后内层循环周期结束, 交由外层循环往后(或前)移动游标, 随即开始下一轮内层循环, 以此类推, 直至循环结束.
由于冒泡排序只在相邻元素大小不符合要求时才调换他们的位置, 它并不改变相同元素之间的相对顺序, 因此它是稳定的排序算法.
```
//先将交换元素部分抽象出来
function swap(i,j,array){
  var temp = array[j];
  array[j] = array[i];
  array[i] = temp;
}
```
```
function bubbleSort(array){
    var length = array.length,isSwap;
    for(var i=0;i<length;i++){
        isSwap=false;
        for(var j=0;j<length-1-i;j++){
            array[j]>array[j+i]&&(isSwap=true)&& swap(j,j+1,array)
        }
        if(!isSwap)
            breack
    }
    return array
}
```
- 平均时间复杂度O(n^2) 
- 最好情况O(n) 
- 最坏情况(n^2) 
- 空间复杂度O(1)

> 双向冒泡排序又称鸡尾酒排序，冒泡排序是从低到高(或者从高到低)单向排序, 双向冒泡排序顾名思义就是从两个方向分别排序(通常, 先从低到高, 然后从高到低). 因此它比冒泡排序性能稍好一些.
```
Array.prototype.cocktail_sort = function() {
	var i, left = 0, right = this.length - 1;
	var temp;
	while (left < right) {
		for (i = left; i < right; i++)
			if (this[i] > this[i + 1]) {
				temp = this[i];
				this[i] = this[i + 1];
				this[i + 1] = temp;
			}
		right--;
		for (i = right; i > left; i--)
			if (this[i - 1] > this[i]) {
				temp = this[i];
				this[i] = this[i - 1];
				this[i - 1] = temp;
			}
		left++;
	}
};
```