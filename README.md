# OS-Lab-5.1
package kz.project;

public class Main {

    public static void main(String[] args) {
        TestThread testThread1 = new TestThread();
        TestThread testThread2 = new TestThread();
        Thread thread1 = new Thread(testThread1);
        Thread thread2 = new Thread(testThread2);
        thread1.start();
        thread2.start();
    }
}
class TestThread implements Runnable{
    @Override
    public void run() {
        for (int i = 0; i <=100 ; i++) {
            System.out.println(Thread.currentThread().getName() + "; i == " + i);
            try {
                Thread.sleep(100);
            }catch (Exception e){
                e.printStackTrace();
            }
        }
    }
}
