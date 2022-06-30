# number-guess


   import java.util.*;
public class NumberGuessingGame
{
     
       
	public static void main(String[] args) {
	    Scanner input=new Scanner(System.in);
	    //ArrayList<Integer> scoreboard=new ArrayList<Integer>();
	   System.out.print("\n"+"What would you like the range of the game to be? ");
	  
        int numberRange = input.nextInt();
         
         
        int randomNumber = randomNumber(numberRange);
               guessNumber(randomNumber,numberRange);    
                    
	    
	}
	public static int scoreboard(int numberRange,int count)
	
	{
	    
	     int score=numberRange-count;
	    System.out.println("Congratulations!!Your score is"+score);
	    return score;
	}
         public static int randomNumber(int numberRange) {
        Random random = new Random();
        int randomNumber = random.nextInt(numberRange) + 1;
        //10System.out.println("random number is" + randomNumber);
        return randomNumber;
    }
    public static void guessNumber(int randomNumber,int numberRange) {
        Scanner input = new Scanner(System.in);
         System.out.print("\n"+"how many attempts do you need to clear the game? ");
         int max=input.nextInt();
        
       int count=0;
        int userGuess;
        
               do {
            System.out.print("Enter your guess: ");
            userGuess = input.nextInt();
            count++;

            if (userGuess < randomNumber) {
                System.out.println("Lower");
            } else // (userGuess < randomNumber)
            {
                System.out.println("Higher");
            }

        } while (randomNumber != userGuess&&count<=max);
         System.out.println(" ");
        if(randomNumber != userGuess)
        {
            System.out.println("Attempts exceeded");
            System.out.println("score is Zero");
        }

       else{

        if (count == 1) {
            System.out.println("You answered right in " + count + " try!");
             scoreboard(numberRange,count);
        } else {
            System.out.println("You answered right in " + count + " tries!");
            scoreboard(numberRange,count);
        }
        
       }
    }
}
