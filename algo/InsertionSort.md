public class InsertionSort{
 public static void sort (int a[]){
  //确定边界，这个方法直接引用了insertion，让low指针一开始指向索引1的位置
  insertion(a,1); 
  
 }
private static void insertion(int []a,int low){
//这里的参数low为指针，作为未排序的右边界，它的左边就是未排序区域
if(low==a.length)return;//这里low增长到跟数组长度一样的地方说明全部排序完毕直接结束方法

int t=a[low];//代表low指针指向数组索引的数字，存储在t这个变量里
int i=low-1;//i存储的是low前面一个数字的索引位置
while(i>=0&&a[i]>t){//这里的逻辑左条件是当想要插入到最左边的位置设置的边界，i作为索引到最左边的时候就该推出循环了，不然没有意义，i自己的值最多搞到-1这个数字，这样下一步就可以再将索引空出插入位置
a[i+1]=a[i];
i--;
}
a[i+1]=t;//找到插入位置把low指针的值给到这个插入位置
insertion(a,low+1);//递归，每次low会向右边移动
}
}
