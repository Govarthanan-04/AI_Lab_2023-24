Ex.No: 12 Planning – Monkey Banana Problem
DATE:17.04.2024
REGISTER NUMBER : 212221040041
AIM:
To find the sequence of plan for Monkey Banana problem using PDDL Editor.

Algorithm:
Step 1: Start the program
Step 2 : Create a domain for Monkey Banana Problem.
Step 3: Create a domain by specifying predicates.
Step 4: Specify the actions GOTO, CLIMB, PUSH-BOX, GET-KNIFE, GRAB-BANANAS in Monkey Banana problem.

Step 5: Define a problem for Monkey Banana problem.
Step 6: Obtain the plan for given problem.
Step 7: Stop the program.

Program:
(define (domain monkey) 
(:requirements :strips) 
(:constants monkey box knife bananas glass waterfountain) 
(:predicates (location ?x) 
(on-floor) 
(at ?m ?x) 
(hasknife) 
(onbox ?x) 
(hasbananas) 
(hasglass) 
(haswater)) 
;; movement and climbing 
(:action GO-TO 
:parameters (?x ?y)
:precondition (and (location ?x) (location ?y) (on-floor) (at monkey ?y)) 
:effect (and (at monkey ?x) (not (at monkey ?y)))) 
(:action CLIMB 
:parameters (?x) 
:precondition (and (location ?x) (at box ?x) (at monkey ?x)) 
:effect (and (onbox ?x) (not (on-floor)))) 
(:action PUSH-BOX 
:parameters (?x ?y) 
:precondition (and (location ?x) (location ?y) (at box ?y) (at monkey ?y) 
(on-floor)) 
:effect (and (at monkey ?x) (not (at monkey ?y)) 
(at box ?x)(not (at box ?y)))) 
;; getting bananas 
(:action GET-KNIFE 
:parameters (?y) 
:precondition (and (location ?y) (at knife ?y) (at monkey ?y)) 
:effect (and (hasknife) (not (at knife ?y)))) 
(:action GRAB-BANANAS 
:parameters (?y) 
:precondition (and (location ?y) (hasknife) 
(at bananas ?y) (onbox ?y)) 
:effect (hasbananas)) 
;; getting water 
(:action PICKGLASS 
:parameters (?y) 
:precondition (and (location ?y) (at glass ?y) (at monkey ?y)) 
:effect (and (hasglass) (not (at glass ?y)))) 
(:action GETWATER 
:parameters (?y) 
:precondition (and (location ?y) (hasglass) 
(at waterfountain ?y)
(at monkey ?y) 
(onbox ?y)) 
:effect (haswater)))
Problem:
(define (problem pb1) 
(:domain monkey) 
(:objects p1 p2 p3 p4 bananas monkey box knife) 
(:init (location p1) 
(location p2) 
(location p3) 
(location p4) 
(at monkey p1) 
(on-floor) 
(at box p2) 
(at bananas p3) 
(at knife p4) 
) 
(:goal (and (hasbananas))) 
)
Output:
https://private-user-images.githubusercontent.com/147976522/281797907-5eb89095-c5c6-4311-b548-c252ca7895f4.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTUzNTg4NzgsIm5iZiI6MTcxNTM1ODU3OCwicGF0aCI6Ii8xNDc5NzY1MjIvMjgxNzk3OTA3LTVlYjg5MDk1LWM1YzYtNDMxMS1iNTQ4LWMyNTJjYTc4OTVmNC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwNTEwJTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDUxMFQxNjI5MzhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT05ZWYzNTliOTYxMzU5NGUwYjM3NTRhOWUxZGVhNzJmOGE4MWNkZmFlYTY3Y2ZjZmVjODZkNjYyYWM5MGFiYjA4JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.6WRVT6n2jhN_-cvCFmPnS8um8c2zkNohaig25RAlzeI

Result:
Thus the plan was found for the initial and goal state of given problem.
