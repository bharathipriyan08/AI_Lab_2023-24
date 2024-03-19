Ex.No: 4 Implementation of Alpha Beta Pruning
DATE:
NAME: Bharathi priyan T
REGISTER NUMBER : 21222104028
AIM:
Write a Alpha beta pruning algorithm to find the optimal value of MAX Player from the given graph.

Steps:
Start the program
Initially assign MAX and MIN value as 1000 and -1000.
Define the minimax function using alpha beta pruning
If maximum depth is reached then return the score value of leaf node. [depth taken as 3]
In Max player turn, assign the alpha value by finding the maximum value by calling the minmax function recursively.
In Min player turn, assign beta value by finding the minimum value by calling the minmax function recursively.
Specify the score value of leaf nodes and Call the minimax function.
Print the best value of Max player.
Stop the program.
Program:
# Python program to demonstrate working of Alpha-Beta Pruning 
# Initial values of Alpha and Beta 
MAX, MIN = 1000, -1000 
 
# Returns optimal value for current player 
#(Initially called for root and maximizer) 
def minimax(depth, nodeIndex, maximizingPlayer, values, alpha, beta): 
 
 # Terminating condition. i.e 
 # leaf node is reached 
 if depth == 3: 
     return values[nodeIndex] 
 if maximizingPlayer: 
     best = MIN 
 # Recur for left and right children 
     for i in range(0, 2): 
         val = minimax(depth + 1, nodeIndex * 2 + i, False, values, alpha, beta) 
         best = max(best, val) 
         alpha = max(alpha, best)
 # Alpha Beta Pruning 
         if beta <= alpha: 
             break 
     return best 
 else: 
     best = MAX 
 # Recur for left and 
 # right children 
     for i in range(0, 2): 
         val = minimax(depth + 1, nodeIndex * 2 + i, True, values, alpha, beta) 
         best = min(best, val) 
         beta = min(beta, best) 
 # Alpha Beta Pruning 
         if beta <= alpha: 
             break 
     return best 
# Driver Code 
if __name__ == "__main__": 
 values = [3, 5, 6, 9, 1, 2, 0, -1] 
 print("The optimal value  is:",minimax(0,0,True,values,MIN,MAX))
Output:
Screenshot 2023-10-28 105743

Result:
Thus the best score of max player was found using Alpha Beta Pruning.
