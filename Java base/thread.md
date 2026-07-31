public class  ThreadDemo {

   public static void main(String[] args) {

 Thread thread = new Thread(  () -> {
          System.out.println("子线程：" + Thread.currentThread().getName()  );  Lambda表达式后面对象的括号里放填充内容，可以是对象，也可以是方法
   });

   thread.start();很重要的start方法，它会通知 JVM 创建一个新的执行线程，然后由新线程执行 run() 里的代码，单独的run方法只是调用的普通方法，并没有开启新线程

 System.out.println("主线程：" + Thread.currentThread().getName());
    }
}

线程池
ExecutorService executor =
        Executors.newFixedThreadPool(4);

executor.submit(() -> {
    System.out.println("线程池执行任务");
});

executor.shutdown();
一般开发情况不会new 新线程，而是交给线程池
