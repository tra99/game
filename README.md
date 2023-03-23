# game
Predict number between 1-30 and program will display congratulation if you input right number. You have 5 chances to input number and the program will display game over if you input higher than 5. 

## Game source code
import java.util.Random;
import java.util.Scanner;

public class test_g {
    public static void main(String[] args) {
        Scanner scanner=new Scanner(System.in);
        Random random=new Random();
        System.out.print("Enter your name: ");
        String name=scanner.nextLine();
        System.out.print("Shall we start now?");
        System.out.print("\n1. Yes");
        System.out.print("\n2. No");
        System.out.print("\nEnter your choice: ");
        int n=scanner.nextInt();
        while (n!=1){
            System.out.print("Shall we start now?");
            System.out.print("\n1. Yes");
            System.out.print("\n2. No");
            System.out.print("\nEnter your choice: ");
            n=scanner.nextInt();
        }
        int num=random.nextInt(50);
        System.out.print("\nGuess number between 1-50: ");
        int guess_num=scanner.nextInt();

        int time_tried=0;
        boolean finished=false;
        boolean won=false;

        while(!finished){
            time_tried++;
            if(time_tried<5){
                if(guess_num==num){
                    won=true;
                    finished=true;
                }
                else if(guess_num>num){
                    System.out.println("Please guess lower number.");
                    guess_num=scanner.nextInt();
                }
                else if(guess_num<num){
                    System.out.println("Please guess higher number.");
                    guess_num=scanner.nextInt();
                }
            }
            else{
                finished=true;
            }
        }
        if(won){
            System.out.println("Congradulatin!!! You have guessed "+time_tried+" times.");
        }
        else{
            System.out.println("Game over!!!");
        }
    }
}

