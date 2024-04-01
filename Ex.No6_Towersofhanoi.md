# Ex.No: 6   Logic Programming – Factorial of number   
### DATE:26.08.2023                                                                            
### REGISTER NUMBER :212221060066 
### AIM: 
To  write  a logic program  to solve Towers of Hanoi problem  using SWI-PROLOG. 
### Algorithm:
1. Start the program
2.  Write a rules for finding solution of Towers of Hanoi in SWI-PROLOG.
3.  a )	If only one disk  => Move disk from X to Y.
4.  b)	If Number of disk greater than 0 then
5.        i)	Move  N-1 disks from X to Z.
6.        ii)	Move  Nth disk from X to Y
7.        iii)	Move  N-1 disks from Y to X.
8. Run the program  to find answer of  query.

### Program:
```
and(0,0,0).
and(0,1,0).
and(1,1,1).
and(1,0,0).
xor(0,0,0).
xor(0,1,1).
xor(1,0,1).
xor(1,1,0).
not(0,1).
not(1,0).
halfadder(A,B,S,C):-
xor(A,B,S),
and(A,B,C).
halfsubtractor(A,B,Diff,Bo):-
xor(A,B,Diff),
not(A,X),
and(B,X,Bo).
```




### Output:
![image](https://github.com/Gopika-5/AI_Lab_2023-24/assets/147976522/d7ceed8b-48ac-4dd6-a139-a154337b1e8e)



### Result:
Thus the solution of Towers of Hanoi problem was found by logic programming.
