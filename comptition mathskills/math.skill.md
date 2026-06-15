字符串方法
//字符数据类型后面加数字(比如int类为首的)会自动转化为string类的数据
String num="0"
for(int i=1;i<=2026;i++){
//这里就是会自动转成字符
num+=i;}
int a=Integer.parseInt(num)%26;
//这里利用余数来拼接代替数据范围计算拼接后大数防止数据溢出
num=a+"";//空字符串类也是将数字类转换成string类的方法


防止浮点误差
maxK=(long)Math.sqrt(total);//先用浮点数算出逻辑上的近似值
while((maxK+1)*(maxK+1)<=total)maxK++;//往上修正如果maxK加1的平方都不超过total那说明算小了
while(maxK*maxK>total)maxK--;//反之上面结论
//为了修正maxK确保满足maxK

浮点误差是因为Math.sqrt()是浮点运算，但total是一个很大的long整数
当total非常大接近10的18次方的时候double就无法精确了

long的大数据后面要加l


关于大数BigInteger用法
一.首先得导入java.math.BigInteger的包
二.其次有三种创建对象方式
1.BigInteger one =BigIeteger.ONE//1,还有英文的0和10
2.BigInteger num1 = BigInteger.valueOf(50);
3.BigInteger num2 = new BigInteger ("999999999999999");
三.核心运算
BigInteger a = BigInteger.valueOf(10);
同样方法搞出一个对象b数字是3
则有BigInteger add = a.add(b);用英文的这个格式来算
//10+3=13
BigInteger x =BigInteger.valueOf(20);
同样方法创建出一个对象y,值是10
则再创建一个数字是int cmp =x.compareTo(y);
if(cmp>0)sout("x更大")//这个运算感觉就是减法
自乘
res=res.multiply(BigInteger.valueOf(i));
四.转普通数字/输出
BigInteger big = big.toString();
String s=big.toString();
long I =big.longValue();


