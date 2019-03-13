import java.util.Scanner;

/**
 * A basic Number Guesser game.
 *
 * @author David Herring
 * @version 3/11/19
 */
public class NumberGuesser
{
    private static Scanner kb = new Scanner(System.in);
    
    public static void main(String [] args)
    {        
        boolean isPlaying = true;
        while (isPlaying)
        {
            numGuesser();
            System.out.println("Enter 1 to play again or 2 to quit");
            int playAgain = kb.nextInt();
            if (playAgain == 2)
                isPlaying = false;
        }
    }
    
    public static void numGuesser()
    {
        int guess = 0;
        int num = (int)(Math.random() * 100 + 1);
        while (guess != num) 
        {
            System.out.println("Guess a number between 1 and 100:");
            guess = kb.nextInt();
            if (guess < num)
                System.out.println("That's too low. Try again.");
            else if (guess > num)
                System.out.println("That's too high. Try again.");
        }
        System.out.println("You guessed it!");
    }
}

