# 排序
## 冒泡排序
> 给定一个无序数组，进行冒泡排序
输入[1,5,2,6,4,3,2]
输出[1,2,2,3,4,5,6]
```
/**
 *  冒泡排序
 *  相邻的两个元素，如果前者大于后者，则交换位置
 *  一轮循环之后，如果没有发生位置交互，则可以退出循环
 */
 public T[] sort(T[] nums) {
        boolean isSorted = false;
        for (int n = nums.length - 1; n > 0 ; n--) {

            for (int a = 0; a < n ; a++) {

                if (less(nums[n], nums[a])) {
                    System.out.println("n:"+n+" a:"+a);
                    isSorted = true;
                    swap(nums, n, a);
                }
            }
            if(!isSorted){
                break;
            }
        }
        //Arrays.stream(nums).forEach(x -> System.out.println(x));
        return nums;
    }
```
