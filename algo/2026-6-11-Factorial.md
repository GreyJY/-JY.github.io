public class Factorial{
public static int f(int n){
if(n==1)return 1;
//递归条件到最后的时候就没了因为f(1)正好符合上述的条件,return 1直接把1给返回了,就没有继续递归的式子了
return n*f(n-1);

}}
public class Test{
@Test
int f=f(5);
System.out.print(f);
}



//反写字符串
public class ReversePrintString{
public static void f(int n,String str){
if(n==str.length()){
return;
}
f(n+1,str);//递归入口首先遍历到最后一个字母的位置,这个return就会帮你变回上一次层的递归,然后继续执行上一层的递归方法,也就能执行打印这个操作了 
System.out.print(str.charAt(n));
}
public static void main(Sting []args){
f(0,"abcd");


}
}
