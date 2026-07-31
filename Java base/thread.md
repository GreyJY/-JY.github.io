public class  ThreadDemo {

   public static void main(String[] args) {

    Thread thread = new Thread(() -> {
          System.out.println("子线程：" + Thread.currentThread().getName());
        });

     thread.start();

      System.out.println("主线程：" + Thread.currentThread().getName());
    }
}
