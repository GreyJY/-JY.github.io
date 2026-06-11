import java.io.*;
import java.util.*;

class FastReader{
BufferedReader br;
StringTokenizer st;
public FastReader(){
br=new BufferedReader(new InputStreamReader(System.in));
}
String next(){
while(st==null||!st.hasMoreTokens()){
try{
st=new StringTokenizer(br.readLine());
}catch(IOException e){
e.printStackTrace();
}
}
return st.nextToken();
}

String nextLine(){
try{
return br.readLine();
}catch(IOException e){
e.printStackTrace();
return null;
}
}
int nextInt(){
return Integer.parseInt(next());
}
省略后两钟
}
}
