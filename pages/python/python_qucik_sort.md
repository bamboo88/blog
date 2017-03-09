---
title: Quick Sort
keywords: sample
summary: "Quick Sort"
sidebar: python_sidebar
permalink: python_quick_sort.html
folder: python
---

### 快速排序算法
快速排序使用分治法（Divide and conquer）策略来把一个串行（list）分为两个字串行（sub-lists）
#### 算法步骤：
1. 从数列中挑出一个元素，称为‘基准（pivot）’。
2. 重新排序数列，所有元素比基准值小的摆放在基准前面，所有元素比基准大的摆放在基准的后面（相同的可放在任一边）。在这个分区完成后，该基准就处于数列的中间位置，这个称为分区操作（partition）。
3. 递归的（recursive）把小于基准元素的子数列和大于基准元素的子列排序。

#### 代码实现
<pre><code>
#-*-coding:utf-8-*-
def QuickSort(arr,firstIndex,lastIndex):
    print arr
    if firstIndex < lastIndex:
        divIndex=Partition(arr,firstIndex,lastIndex)
        QuickSort(arr,firstIndex,divIndex)
        QuickSort(arr,divIndex+1,lastIndex)
    else:
        return

def Partition(arr,firstIndex,lastIndex):
    i=firstIndex-1
    for j in range(firstIndex,lastIndex):
        if arr[j]<=arr[lastIndex]:
            i=i+1
            arr[i],arr[j]=arr[j],arr[i]
    arr[i+1],arr[lastIndex]=arr[lastIndex],arr[i+1]
    return i

arr=[1,4,2,3]
QuickSort(arr,0,len(arr)-1)
</code></pre>

{% include links.html %}
