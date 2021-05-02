# task2
task2
import java.util.Scanner;
public class main {

    public static void main(String[] args) {
        System.out.print("Введите чётное число n= ");
        Scanner sc1 = new Scanner(System.in);
        int n = sc1.nextInt();
        if (n % 2 == 1) {
            System.out.print("Вы ввели нечётное число");
            System.exit(-1);
        }
        System.out.print("Введите первый целый " + n + "-значный множитель x= ");
        Scanner sc2 = new Scanner(System.in);
        long x = sc2.nextLong();
        System.out.print("Введите второй целый " + n + "-значный множитель y= ");
        Scanner sc3 = new Scanner(System.in);
        long y = sc3.nextLong();
        System.out.print(methode(x,y,n));
    }
    public static long methode(long x, long y, int n) {
        if (n == 2) {
            return x * y;
        }
        long a = (int) (x / Math.pow(10, n / 2));
        long b = (int) (x % Math.pow(10, n / 2));
        long c = (int) (y / Math.pow(10, n / 2));
        long d = (int) (y % Math.pow(10, n / 2));
        long ac = methode(a, c, n / (n / 2));
        long ad = methode(a, d, n / (n / 2));
        long bc = methode(b, c, n / (n / 2));
        long bd = methode(b, d, n / (n / 2));
        return (long) ((long) Math.pow(10, n) * ac + Math.pow(10, n / 2) * (ad + bc) + bd);
    }
}
