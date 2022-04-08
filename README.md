# Tic-Tac-Toe Game Using Mini-Max Algorithm


<p align="center">
<img width="912" alt="Screenshot 2022-04-07 at 10 30 02 PM" src="https://user-images.githubusercontent.com/54971204/162359027-b7bbca33-815a-469e-ac5f-0e1ae91ad0f5.png">
</p>


## Introduction:



## What is Mini-Max Algorithm and How does it work ?
Mini-Max algorithm is a **Recursive Bactracking Algorithm**, which makes optimal decision for current state based on each of its possible successor states.
It is generally used in 2-player based games such as TicTacToe, Backgammon, Chess, and Mancala etc which are played in turn-based. In general the result or **Terminal** state of these games is either **"Win"** or **"Lose"** or **"Draw"** .One of the palyer is called as **Minimizer** and other player is called as **Maximizer**.

**Minimizer**:Minimizer or **MIN** player is a player, who always tries to minimize the opponents score.

**Maximizer**:Maximizer or **MAX** player is a player, who always tries to get maximium score possible.


## Understanding the Code
Important Functions to understand in the code:
```
public static int minmax (int[][]a,boolean ismaximizing)
{
      .
      .
      .
}
```

**minmax()** function returns the bestscore for each move
- The input of the function of is **"current state"** of the tictactoe game and **"boolean value(**True** or **False**)"** of the current player i.e is the player trying to maximize the score or minimize the score?


```
public static int minmax (int[][]a,boolean ismaximizing)
{

      if(wincheck(a)==1){
          return 100;
      }
      else if(wincheck(a)==2){
          return -100;
      }
      else if(checkdraw()){
          return 0;
      }
      . 
      . 
      .
      .
      .
}
```
- Checking the currrent state of TicTacToe game whether if any one of the palyer had already Won or Lost or a Draw.
- If it is not satisfying any one of the above 3 conditions, then we continue to calculate the bestscore for current player.
```
public static int minmax (int[][]a,boolean ismaximizing)
{
      . 
      . 
      .
      .
      .
      if(ismaximizing)
      {
          bestscore=-10000;
          for (int i = 0; i < 3; i++)
          {
           	for (int j = 0; j < 3; j++)
	           {
	             if (a[i][j] == -1)
	             {
		              a[i][j] = 1;
		              score = minmax(a,false);
                a[i][j] = -1;
		              if (score>bestscore)
		              { 
                  bestscore = score;
		              }
	             }
	           }
          }
      return bestscore;
      }
      
      else
      {
          bestscore=10000;
          for (int i = 0; i < 3; i++)
          {
	   for (int j = 0; j < 3; j++)
	   {
	     if (a[i][j] == -1)
	     {
		a[i][j] = 0;
		score = minmax(a,true);
                a[i][j] = -1;
                if (score<bestscore)
		  {
                   bestscore = score;
		  }
	     }
	   }
          }
      return bestscore;
      }

}
```
- If the current player is trying to maximize the score, then we will place **"X"** in the position that produces the highest value for **"MIN"** of current state.

- If the current player is trying to minimize the score, then we will place **"O"** in the position that produces the minimum value for **"MAX"** of the current state


## Example of Tic-Tac-Toe Game Tree
<p align = "center">
 <img width="985" alt="Screenshot 2022-04-08 at 7 47 21 PM" src="https://user-images.githubusercontent.com/54971204/162454481-0e268ba1-742f-4a3b-8b10-681d94e20e92.png">

</p>







## References
- Book: Artificial Intelligence: A Modern Approach by Peter Norvig and Stuart J. Russell


## How to Run the Code?

This repository contains two source code files

- **start.java**: This file contains the code that displays the first page, where you can select which player can start the game i.e either **Player** or **Computer**


- **TicTacToe.java**:This file contains the various functions that are a part of computing **minimax** value in each state of the game. 

Download both the files including images and run the file  **start.java**







