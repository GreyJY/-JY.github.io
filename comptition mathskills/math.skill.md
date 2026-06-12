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

