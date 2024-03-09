# Ex.No: 10  Logic Programming –  Simple queries from facts and rules
### DATE:                                                                            
### REGISTER NUMBER : 
### AIM: 
To write a prolog program to find the answer of query. 
###  Algorithm:
 Step 1: Start the program <br> 
 Step 2: Convert the sentence into First order Logic  <br> 
 Step 3:  Convert the sentence into Horn clause form  <br> 
 Step 4: Add rules and predicates in a program   <br> 
 Step 5:  Pass the query to program. <br> 
 Step 6: Prolog interpreter shows the output and return answer. <br> 
 Step 8:  Stop the program.
### Program:
### Task 1:
Construct the FOL representation for the following sentences <br> 
1.	John likes all kinds of food.  <br> 
2.	Apples are food.  <br> 
3.	Chicken is a food.  <br> 
4.	Sue eats everything Bill eats. <br> 
5.	 Bill eats peanuts  <br> 
   Convert into clause form and Prove that John like Apple by using Prolog. <br> 
### Program:
```
likes(mani,X):-easygame(X).
indoorgame(tabletennis).
easygame(X):-indoorgame(X).
hard(boxing).
likes(john,X):-food(X).
food(apple).
food(vegetable).
eats(bill,peanuts).
eats(sue,X):-eats(bill,X).
alive(bill).
```

### Output:
![WhatsApp Image 2024-03-09 at 16 15 37_2a5d4396](https://github.com/YugendarM/AI_Lab_2023-24/assets/119681539/0762d6d5-282b-4d1d-9516-bcf0beb991c6)


### Task 2:
Consider the following facts and represent them in predicate form: <br>              
1.	Steve likes easy courses. <br> 
2.	Science courses are hard. <br> 
3. All the courses in Have fun department are easy <br> 
4. BK301 is Have fun department course.<br> 
Convert the facts in predicate form to clauses and then prove by resolution: “Steve likes BK301 course”<br> 

### Program:
```
likes(steve,X):-
     easycourse(X).
hard(sciencecourse).
easycourse(X):-
          course(X,dept(havefun)).
course(bk301,dept(havefun)).

```

### Output:
![image](https://github.com/YugendarM/AI_Lab_2023-24/assets/119681539/fdc00246-48cb-458e-aa39-b86e79b5452d)


### Task 3:
Consider the statement <br> 
“This is a crime for an American to sell weapons to hostile nations. The Nano , enemy of America has some missiles and its missiles were sold it by Colonal West who is an American” <br> 
Convert to Clause form and prove west is criminal by using Prolog.<br> 
### Program:
```
criminal(X):-
	american(X),
	weapon(Y),
	hostile(Z),
	sells(X,Y,Z).
weapon(Y):-
                 missile(Y).
hostile(Z):-
                 enemy(Z,X).

sells(west,Y,nano):-
	missile(Y),
	owns(nano,Y).

missile(m).
owns(nano,m).
enemy(nano,america).
american(west).
```

### Output:
![WhatsApp Image 2024-03-09 at 16 19 30_6875467e](https://github.com/YugendarM/AI_Lab_2023-24/assets/119681539/c015d5f3-4758-4e28-b82f-6a48c645be93)



### Result:
Thus the prolog programs were executed successfully and the answer of query was found.
