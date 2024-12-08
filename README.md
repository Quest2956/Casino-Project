# **Interactive Casino**  
The **Interactive Casino** is a C programming project that simulates the thrill of a virtual casino environment. It features four classic casino games—Roulette, Blackjack, Slots, and Coin Flip, allowing users to place bets, test their luck, and manage their virtual balance. This project showcases modular programming, dynamic memory management, and random number generation in C.  

## **Project Features**  
- **Roulette**: Bet on a number between 0 and 18. Win 18x the bet for correct guesses.  
- **Blackjack**: Compete against the dealer to achieve a higher card value without exceeding 21.  
- **Slots**: Spin three reels and win based on matching patterns, including a jackpot for all three matching.  
- **Coin Flip**: Bet on heads or tails, and double your bet on a correct guess.  

## **Contribution**  
### **Slots Game**  
As a contributor to the Interactive Casino project, I was responsible for implementing the Slots game function. My tasks included:

- Designing the mechanics for the Slots game, including rules for betting, spinning, and winning.
- Using `rand()` seeded with `srand(time(NULL))` to generate random slot results for three reels, ensuring fairness and unpredictability.
- Implementing game rules:
- Jackpot Rule: Winning 10x the bet for three matching reels.
- Partial Match Rule: Winning half the bet for two matching reels.
- No Match Rule: Losing the bet for no matches.
- Managing and updating the player's balance dynamically using pointer arithmetic.
- Creating user-friendly prompts and detailed feedback messages to enhance the player's experience.
- Ensuring input validation to prevent invalid bets or entries.
- This module demonstrates key programming concepts such as randomization, input validation, and dynamic memory management in C.

### **Code Snippet**
```
void slots(int *balance)
{
    int bet, s1, s2, s3;

    printf("<---SLOTS--->\n\n");
    printf("Rules for Slots.\n");
    printf("1. Betting Rule: The player must place a bet before spinning the slots. The bet cannot exceed their current balance or be less than or equal to zero.\n");
    printf("2. Slot Spin: Three random values are generated for the three slots (ranging from 0 to 10), and the results are displayed to the player.\n");
    printf("3. Jackpot Rule: If all three slots match (e.g., 3 | 3 | 3), the player wins the jackpot and receives 10 times the amount they bet.\n");
    printf("4. Partial Match Rule: If any two slots match (e.g., 3 | 3 | 1), the player wins half their bet.\n");
    printf("5. No Match Rule: If none of the slots match (e.g., 3 | 1 | 2), the player loses their bet, and their balance is reduced accordingly.\n\n");

    printf("Enter your bet: ");
    scanf("%d", &bet);

    if (bet > *balance || bet <= 0) 
    {
        printf("Invalid bet amount. Please try again.\n\n");
        return;
    }

    s1 = rand() % 11;
    s2 = rand() % 11;
    s3 = rand() % 11;

    printf("Slot Results: %d | %d | %d\n", s1,s2,s3);

    if (s1 == s2 && s2 == s3)
    {
        printf("Congratulations! You won a JACKPOT!!!\n");
        *balance = *balance + bet * 10;
    }
    else if (s1 == s2 || s2 == s3 || s1 == s3)
    {
        printf("Congrats! You win half your bet!\n");
        *balance = *balance + bet / 2;
    }
    else
    {
        printf("You lose. Better luck next time!\n");
        *balance = *balance - bet;
    }

    show_bal(*balance);
}
```

## **How to Run the Program**  
1. Clone the repository:  
   ```bash  
   git clone https://github.com/xstolas/interactive-casino.git  
   ```  
2. Navigate to the project directory:  
   ```bash  
   cd interactive-casino
   ```  
3. Compile the program using GCC or another C compiler:  
   ```bash  
   gcc casino.c -o casino  
   ```  
4. Run the program:  
   ```bash  
   ./casino  
   ```  

## **Technologies Used**  
- **Programming Language**: C  
- **Libraries**:  
  - `<stdio.h>`: Input and output functions  
  - `<stdlib.h>`: Random number generation and memory management  
  - `<time.h>`: Seeding the random number generator with system time  

## **Acknowledgments**  
Special thanks to my team members for their collaboration and to our advisor Mr. Sahabzada Betab Badar for his guidance throughout the project. 
