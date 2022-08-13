```
package com.company;

import java.util.Arrays;
import java.util.Random;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        Random rand = new Random();
        int number = rand.nextInt(100);

        Scanner scanner = new Scanner(System.in);


        int right = 0;
        int select;
        int[] wrong = new int[5];
        boolean isWin = false;
        boolean isWrong = false;


        while (right < 5) {
            System.out.println("Lutfen tahmininizi girin : ");
            select = scanner.nextInt();
            if (select < 0 || select > 99) {
                System.out.print("lutfen 0 ile 100 arasinda bir sayi giriniz. ");
                if (isWrong) {
                    right++;
                    System.out.println(" Cok fazla hatali giris yaptiniz. Kalan hakkiniz : " + (5 - right));
                } else {
                    isWrong = true;
                    System.out.println(" Bir sonraki hatali girisinizde hakkinizdan dusülecektir. ");

                }
                continue;
            }
            if (select == number) {
                System.out.print("Tebrikler gizli sayiyi bildiniz.!!!");
                isWin = true;
                break;
            } else {
                System.out.println(" Hatali bir giris yaptiniz !!!");
            }
            if (select > number) {
                System.out.println(select + " sayisi gizli sayidan buyuktur");
            } else {
                System.out.println(select + " sayisi gizli sayidan kucuktur");
            }
            wrong[right++] = select;
            System.out.println("Kalan hakkiniz : " + (5 - right));
        }
        if (!isWin) {
            System.out.println(" Kaybettiniz !!! ");
            if (!isWrong) {
                for (int i = 0; i < wrong.length; i++) {
                    System.out.println("Tahminleriniz = " +wrong);
                }
            }
        }
    }
}


```