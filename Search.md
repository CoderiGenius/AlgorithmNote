# 二分查找
> 给定一个数组，和一个值，返回值所在的坐标
输入[1,2,3,4,5,6,7,8]  7
输出6

- 二分查找必须使用有序的结构
- 取中间的数比较是大还是小，分布对应在左边或者右边
- 保留头和尾，缩小范围的时候，只需要修改left 或 right就行 这样可以直接找出来所要查找的元素的位置

```

/**
 * 二分查找
 */
public class BinarySearch {

    public static void main(String[] args) {
        int[] num = new int[]{1};
        System.out.println(getResult(num,1,0,num.length-1));
    }

    public static int getResult(int[] nums, int search,int left,int right) {
        //先判断是否到头了
        if (left == right && nums[left]!=search ) {
            return -1;
        }
        if (left == right && nums[left]==search ) {
            return left;
        }

        //没到头
        if (nums[(left + right) / 2] == search) {
            return (left + right) / 2;
        }
        if (nums[(left + right) / 2] < search) {
            return getResult(nums,search,(left + right) / 2,right);
        }
        if (nums[(left + right) / 2] > search) {
            return getResult(nums,search,left,(left + right) / 2);
        }

        return -1;
    }


}
```
