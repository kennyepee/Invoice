# Invoice
package com.company;
import java.util.ArrayList;
import java.util.Scanner;
public class Main {

    public static void main(String[] args) {
        ArrayList<String> products = new ArrayList<String>();
        ArrayList<Double> prices = new ArrayList<Double>();
        products.add("Bison Sweater");
        prices.add(55.99);
        products.add("Bison Tee");
        prices.add(14.99);
        products.add("Bison Hoodie");
        prices.add(23.99);
        products.add("Bison Bumpersticker");
        prices.add(4.99);

        String answer = "";
        ArrayList<String> purchases = new ArrayList<String>();

        Scanner input = new Scanner(System.in);
        do {
            System.out.println("What do you want to do?");
            System.out.println("1) add purchase 2) change purchase 3) show purchases 4) finish transaction");
            answer = input.nextLine();

            if (answer.equals("1"))
            {
                System.out.println("What do you wish to buy?");
                answer = input.nextLine();
                purchases.add(answer);
            }

            else if (answer.equals("2")) {
                System.out.println("What would you wish to change?");
                System.out.println(purchases);
                System.out.println("What item do you want to remove from purchase?");
                String prod = input.nextLine();

                int index = -1;
                for (int i = 0; i < products.size(); i++) {
                    if (products.get(i).equals(prod)) {
                        index = i;
                    }
                }
               {
                    purchases.remove(index);
                }

            }else if (answer.equals("3")) {
                System.out.println("Here are your purchases");
                System.out.println(purchases);

            }

        } while (! answer.equals("4"));
        double totalcost = 0.0;
        int j = 0;
        for (int i = 0; i < purchases.size() ; i++)
        {
            j=0;
            do {
                // condition is check if the value in purchases at position i is equal to the value in products at position j
                if  (purchases.get(i).equals(products.get(j)))
                {
                    totalcost += prices.get(j);
                }
                j++;
            } while (j < products.size());
        }
        System.out.println("Your order total is: $" + totalcost);
        System.out.println("Thank you for ordering!");

    }
}
