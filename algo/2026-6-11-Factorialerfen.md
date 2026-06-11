public class BinarySearchBasic{
//相当于运行的方法
public static int search(int []a,int target){
return f(a,target,0,a.length-1);
}
//private这个关键字现定于同一个类
private static int f(int[]a,int target,int i,int j){
if(i>j)return -1;
//想当于除以2>>>
int m=(i+j)>>>1;
递归方法来查找相当于while循环来找
if(target<a[m]){
return f(a,target,i,m-1);
}else if(a[m]<target){
return f(a,target,m+1,j);
}else{
//这种相当于直接发现跟中间数字一样了
return m;
}
}
}

Test{
@Test
public void test1(){
int []a={7,13,21,30,38,44,56,53};
//相当于查找存在的元素找到就返回0
assertEquals(0,search(a,7);
}
}
