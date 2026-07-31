public class  ThreadDemo {

   public static void main(String[] args) {

 Thread thread = new Thread(  () -> {
          System.out.println("子线程：" + Thread.currentThread().getName()  );  Lambda表达式后面对象的括号里放填充内容，可以是对象，也可以是方法
   });

   thread.start();

 System.out.println("主线程：" + Thread.currentThread().getName());
    }
}
