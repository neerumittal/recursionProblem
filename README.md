# recursionProblem
Choclate wrapper problem using recursion
import java.util.Scanner;

class Cal { 
       
      
    public static void main (String[] args) 
    { 
        // to take input from user
        Scanner sc = new Scanner(System.in);
        
        System.out.print("Enter Total Money You Have : ");
        int money = sc.nextInt();
        
        System.out.print("Enter Price of each Chocolate : ");
        int price = sc.nextInt();
        
        System.out.print("How many wrapper will get an Extra Chocolate : ");
        int wrapper = sc.nextInt();
        
        // getting the count , calling the method
        int totalChocolates = getChocolatesCount(money, price, wrapper);
        
        System.out.println("answer = "+totalChocolates);
    } 
    
    static int getChocolatesCount(int money, int price, int wrapper) 
    { 
        
        int chocolates = money/price; 
        
        // calling the recursive function
        return chocolates + getCountRecursively( chocolates , wrapper); 
    } 
    
    
    static int getCountRecursively(int chocolates, int wrapper) 
    { 
          
        if (chocolates < wrapper) 
            return 0; 
      
        int extraChocolates = chocolates / wrapper; 
      
        // calling function again & again until we get the chocolates count < wrapper required 
        return extraChocolates + getCountRecursively( extraChocolates + chocolates%wrapper, wrapper );                           
    } 

    
} 
