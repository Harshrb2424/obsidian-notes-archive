## SET 1: 
## a) Write simple fact for following: A. Ram likes mango. B. Seema is a girl. C. Bill likes Cindy. D. Diamond is Valuable. E. John owns gold.

### Source Code: 

```pl
likes(ram,mang0).
girl(seema).
red(rose).
likes(bill,candy).
owns(john,gold).
```

### Output:

```bash
ᬀ% c:/users/harsh/onedrive/documents/prolog/ex1 compiled 0.00 sec, -3 clauses
?- likes(ram, What).
What = mango.

?- likes(Who, candy).
Who = bill.

?- red(What).
What = rose.

?- owns(Who, What).
Who = john,
What = gold.
```
# b) Write a prolog program for binary search trees.
### Source Code: 
```pl
% Check if an element is in a binary tree
in(X, t(_, X, _)).
in(X, t(L, _, _)) :- 
    in(X, L). 
in(X, t(_, _, R)) :- 
    in(X, R).

% Check if an element is in a binary search tree
in(X, t(_, X, _)).
in(X, t(Left, Root, Right)) :-
    gt(Root, X), 
    in(X, Left). 
in(X, t(Left, Root, Right)) :-
    gt(X, Root), 
    in(X, Right).

% Add an element to a binary search tree
add(Tree, X, NewTree) :-
    addroot(Tree, X, NewTree). 
add(t(L, Y, R), X, t(L1, Y, R)) :-
    gt(Y, X),
    add(L, X, L1). 
add(t(L, Y, R), X, t(L, Y, R1)) :-
    gt(X, Y), 
    add(R, X, R1). 

% Add an element to an empty tree
addroot(nil, X, t(nil, X, nil)). 
addroot(t(L, Y, R), X, t(L1, X, t(L2, Y, R))) :-
    gt(Y, X), 
    addroot(L, X, t(L1, X, L2)). 
addroot(t(L, Y, R), X, t(t(L, Y, R1), X, R2)) :-
    gt(X, Y), 
    addroot(R, X, t(R1, X, R2)).

% Display a binary tree
show(Tree) :-
    show2(Tree, 0).
show2(nil, _).
show2(t(Left, X, Right), Indent) :-
    Ind2 is Indent + 2, 
    show2(Right, Ind2), 
    tab(Indent), write(X), nl, 
    show2(Left, Ind2).

```
### Output
```bash
?- in(3, t(t(nil, 1, nil), 2, t(nil, 3, nil))).
true .

?- add(t(t(nil, 1, nil), 2, t(nil, 3, nil)), 4, NewTree).
NewTree = t(t(nil, 1, nil), 2, t(nil, 3, t(nil, 4, nil))).

?- show(t(t(nil, 1, nil), 2, t(nil, 3, nil))).
  3
2
  1
true.

?- add(nil, 5, D1),
|    add(D1, 3, D2).
D1 = t(nil, 5, nil),
D2 = t(t(nil, 3, nil), 5, nil) .

?- add(D2, 8, D3),
add(D3, 6, D4),
|    show(D3).|    
8
  6
D2 = nil,
D3 = t(nil, 8, nil),
D4 = t(t(nil, 6, nil), 8, nil) .
```
---
## SET 2: 
## a) Write simple Prolog functions to remove the Nth item from the list.
### Source Code: 
```pl
delte(1,[_|T],T).
delte(P,[X|Y],[X|R]):-
    P1 is P-1,
    delte(P1,Y,R).
```
### Output
```bash
% c:/users/harsh/onedrive/documents/prolog/exp8 compiled 0.00 sec, -7 clauses
?- delte(4,[1,2,3,4,5,6],R).
R = [1, 2, 3, 5, 6] .

?- delte(2,[a,b,c,d,e],R).
R = [a, c, d, e] .

?- delte(5,[1,2,3,4,5,6],R).
R = [1, 2, 3, 4, 6] .

?- delete(2, [a, b, c, d],R).
R = [a, c, d] .

```


## b) Write a program to solve the 4-Queen problem.
### Source Code: 
```pl
queens(N, Queens) :-
    length(Queens, N),
    board(Queens, Board, 0, N, _, _),
    queens(Board, 0, Queens).

board([], [], N, N, _, _).

board([_|Queens], [Col-Vars|Board], Col0, N, [_|VR], VC):-
    Col is Col0+1,
    functor(Vars, f, N),
    constraints(N, Vars, VR, VC),
    board(Queens, Board, Col, N, VR, [_|VC]).

constraints(0, _, _, _):- !.

constraints(N, Row, [R|Rs], [C|Cs]):-
    arg(N, Row, R-C),
    M is N-1,
    constraints(M, Row, Rs, Cs).

queens([], _, []).

queens([C|Cs], Row0, [Col|Solution]) :-
    Row is Row0+1,
    select(Col-Vars, [C|Cs], Board),
    arg(Row, Vars, Row-Row),
    queens(Board, Row, Solution).
```
### Output
```bash
ጀ% c:/users/harsh/onedrive/documents/prolog/exp5 compiled 0.00 sec, -2 clauses
?- queens(4,Queens).
Queens = [2, 4, 1, 3] .

?- queens(5,Queens).
Queens = [1, 3, 5, 2, 4] .

?- queens(7,Queens).
Queens = [1, 3, 5, 7, 2, 4, 6] .
```

---
## SET 3: 
## a) Write a Prolog predicate, countLists(Alist, Ne, NI), using accumulators, that is true when Ni is the number of items that are listed at the top level of Alist and Ne is the number of empty lists. Suggestion: First try to count the lists, or empty lists, then modify by adding the other counter.
### Source Code:
```pl
% Base case: an empty list has 0 empty sublists
empties([], 0).

% Recursive case: if the head of the list is an empty list, increment the count
empties([[]|L], R) :-
    empties(L, K),
    R is K + 1.

% Recursive case: if the head is not an empty list, just proceed with the tail
empties([X|L], K) :-
    X \= [],
    empties(L, K).

% Alternative implementation using findall and length to count empty sublists
empties(L, N) :-
    findall(X, (member(X, L), X = []), L1),
    length(L1, N).

```
### Output
```bash
ʹ% c:/users/harsh/onedrive/documents/prolog/exp10 compiled 0.00 sec, -8 clauses
empties([], 0).
true .

?- empties([[], [], [1,2], [], [3], []], Count).
Count = 4 .

?- empties([[], X, [], Y, Z, [[]]], Count).
X = Y, Y = Z, Z = [],
Count = 5 .

?- empties([[], [a], [], [b, c], [], [], [d], [], [e, f]], Count).
Count = 5 .

?- empties([[a, b], [], [c], [], [d, e], [], [], [f], [g], [], [], [h], [], [i, j, k]], Count).
Count = 7 .
```

## b) Write a program to solve the Monkey Banana problem.
### Source Code: 

```pl
in_room(bananas).
in_room(chair).
in_room(monkey).

clever(monkey).
can_move(monkey,chair,bananas).
can_climb(monkey,chair).
can_reach(X,Z):-clever(X),is_close(X,Z).
is_close(X,Z):- can_climb(X,Y),under(Y,Z).
under(Y,Z):-in_room(X),in_room(Y), in_room(Z), can_move(X,Y,Z).
```

### Output:

```bash
% c:/users/harsh/onedrive/documents/prolog/exp3 compiled 0.00 sec, -3 clauses
?- can_reach(Who, What).
Who = monkey,
What = bananas .

?- can_reach(monkey, bananas).
true.

?- can_reach(monkey, apple).
false.

?- clever(Who).
Who = monkey.

?- can_climb(X,Y).
X = monkey,
Y = chair.
```

---
## SET 4: 
## a) Define a predicate memCount(AList, Blist, Count) that is true if Alist occurs Count times within Blist. Define without using an accumulator.
### Source Code:
```pl
not(Goal) :-
    \+ call(Goal).

prefix([], _).
prefix([H|T1], [H|T2]) :-
    prefix(T1, T2).

memCount(_, [], 0).

memCount(AList, BList, Count) :-
    prefix(AList, BList),  % AList is a prefix of BList
    append(AList, Rest, BList),  % Remove the prefix AList from BList to get Rest
    memCount(AList, Rest, CountRest),
    Count is CountRest + 1.

memCount(AList, [_|Tail], Count) :-
    not(prefix(AList, [_|Tail])),  % Ensure AList is not a prefix of the current list
    memCount(AList, Tail, Count).
```
### Output
```bash
ᜀ% c:/users/harsh/onedrive/documents/prolog/diff compiled 0.00 sec, -1 clauses
?- memCount([1,2],[1,2,3,1,2,1,2,4],Count).
Count = 3 .

?- memCount([1, 2], [1, 3, 4, 1, 2, 1, 2], Count).
Count = 2 .

?- memCount([1], [1, 1, 1, 1], Count).
Count = 4 .

?- memCount([2], [1, 3, 4, 5], Count).
false.
```
## b) Write predicates one converts Fahrenheit temperatures to centigrade, the other checks if a temperature is below freezing.

### Source Code:

```pl
c_to_f(C,F):-
   F is C*9/5+32.
frezzing(F):-
   F=<32.
```

### Output:

```bash
Ȁ% c:/users/harsh/onedrive/documents/prolog/exp2 compiled 0.00 sec, -1 clauses
?- c_to_f(100,X).
X = 212.

?- frezzing(15).
true.

?- c_to_f(32,X).
X = 89.6.
```

---
## SET 5: 
## a) Write a program to solve traveling salesman problems.
### Source Code: 
```pl
road("tampa", "houston", 200).
road("gordon", "tampa", 300).
road("houston", "gordon", 100).
road("houston", "kansas_city", 120).
road("gordon", "kansas_city", 130).

route(Town1, Town2, Distance) :-
    road(Town1, Town2, Distance).

route(Town1, Town2, Distance) :-
    road(Town1, X, Dist1),
    route(X, Town2, Dist2),
    Distance is Dist1 + Dist2, !.
```
### Output
```bash
?- route("tampa", "houston", Distance).
Distance = 200.

?- route("gordon", "kansas_city", Distance).
Distance = 130 ;
Distance = 420.

?- route("tampa", "kansas_city", Distance).
Distance = 320 ;
Distance = 530.

?- route("houston", "kansas_city", Distance).
Distance = 120 ;
Distance = 230 ;
false.

?- route("houston", "gordon", Distance).
Distance = 100.

```

## b) WAP in turbo prolog for medical diagnosis and show the advantages and disadvantages of green and red cuts.
### ALGORITHM
1. Start
2. First the knowledge is encoded in knowledge base
3. A set of new questions are raised to the users
4. Matching the answers convert personality is returned
5. No match occur error message displayed
6. Stop.

### Source Code:

```pl
run :-
    write('Do you have HEADACHE?'),
    read(HA),
    write('Do you have TEMPERATURE?'),
    read(TP),
    write('Do you have a SORE THROAT?'),
    read(ST),
    write('Are you feeling TIRED?'),
    read(TR),
    disease(HA, TP, ST, TR).


disease(y,y,y,y):-write('You are suffering from VIRAL FEVER').
disease(y,y,y,n):-write('You are suffering from COMMON FEVER').
disease(y,y,n,y):-write('You are suffering from VIRAL FEVER').
disease(y,y,n,n):-write('You maybe OVERHOOKED').
disease(y,n,y,y):-write('You are suffering from COLD').
disease(y,n,y,n):-write('You might develop THROAT INFECTION').
disease(y,n,n,y):-write('You might have SEDENTARY for a long spell').
disease(y,n,n,n):-write('You are suffering from HEADACHE').
disease(n,y,y,y):-write('You are suffering from FEVER').
disease(n,y,y,n):-write('You are experiencing initial stages of COMMON COLD').
disease(n,y,n,y):-write('You are suffering from DEHYDRATION').
disease(n,y,n,n):-write('You are suffering from DENGU FEVER').
disease(n,n,y,y):-write('You are suffering from CHICKENGUNYA').
disease(n,n,y,n):-write('You are suffering from SORE THROAT').
disease(n,n,n,y):-write('You can relax, U are ENERVATED').
disease(n,n,n,n):-write('You are ALRIGHT').

```

### Output:

```bash
% c:/users/harsh/onedrive/documents/prolog/exp4 compiled 0.00 sec, 0 clauses
?- run.
Do you have HEADACHE?y.
Do you have TEMPERATURE?|: n.
Do you have a SORE THROAT?|: y.
Are you feeling TIRED?|: y.
You are suffering from COLD
true .
```

---
## SET 6: 
## a) Write a program to solve water jug problems using Prolog..
### Source Code: 
```pl
member(X, [X|_]).
member(X, [Y|Z]):-member(X,Z).

move(X,Y,_):-X=:=2,Y=:=0,write('done'),!.

move(X,Y,Z):-X<4,\+member((4,Y),Z),
    write("fill 4 gallon jug"),nl,move(4,Y,[(4,Y)|Z]).

move(X,Y,Z):-Y<3, \+member((X,3),Z),
    write("fill 3 gallon jug"),nl,move(X,3,[(X,3)|z]).

move(X,Y,Z):-X>0,\+member((0,Y),Z),
    write("pour 4 galloon jug"),nl, move(0,Y,[(0,Y)|Z]).

move(X,Y,Z):-Y>0,\+member((X,0),Z),
    write("pour 3 galloon jug"),nl, move(X,0,[(X,0)|Z]).

move(X,Y,Z):-P is X+Y, P>=4, Y>0,K is 4-X,M is Y-K,\+member((4,M),Z),
    write("pour from 3 gallon jug to 4 gallon jug"),nl, move(4, M, [(4,M)|Z]).

move(X,Y,Z):-P is X+Y, P>=3, X>0,K is 3-Y,M is X-K,\+member((M,3),Z),
    write("pour from 4 gallon jug to 3 gallon jug"),nl, move(M,3,[(M,3)|Z]).

move(X,Y,Z):-K is X+Y, K<4, Y>0, \+member((K,0),Z),
    write("pour from 3 gallon jug to 4 gallon jug"), nl, move(K,0,[(K,0)|Z]). move(X,Y,Z):-K is X+Y, K<3,X>0,\+member((0,K),Z),
    write("pour from 4 gallon jug to 3 gallon jug"),nl, move(0,K, [(0,K)|Z]).

```
### Output
```bash
% c:/users/harsh/onedrive/documents/prolog/exp7 compiled 0.00 sec, -2 clauses

?- move(0,2,[]).
fill 4 gallon jug
fill 3 gallon jug
pour 4 gallon jug
pour 3 gallon jug
fill 4 gallon jug
pour from 4 gallon jug to 3 gallon jug
pour 3 gallon jug
pour from 4 gallon jug to 3 gallon jug
fill 4 gallon jug
pour from 4 gallon jug to 3 gallon jug
pour 3 gallon jug
done
true .
```

## b) Write a program to solve the 4-Queen problem.
### Source Code: 
```pl
queens(N, Queens) :-
    length(Queens, N),
    board(Queens, Board, 0, N, _, _),
    queens(Board, 0, Queens).

board([], [], N, N, _, _).

board([_|Queens], [Col-Vars|Board], Col0, N, [_|VR], VC):-
    Col is Col0+1,
    functor(Vars, f, N),
    constraints(N, Vars, VR, VC),
    board(Queens, Board, Col, N, VR, [_|VC]).

constraints(0, _, _, _):- !.

constraints(N, Row, [R|Rs], [C|Cs]):-
    arg(N, Row, R-C),
    M is N-1,
    constraints(M, Row, Rs, Cs).

queens([], _, []).

queens([C|Cs], Row0, [Col|Solution]) :-
    Row is Row0+1,
    select(Col-Vars, [C|Cs], Board),
    arg(Row, Vars, Row-Row),
    queens(Board, Row, Solution).
```
### Output
```bash
ጀ% c:/users/harsh/onedrive/documents/prolog/exp5 compiled 0.00 sec, -2 clauses
?- queens(4,Queens).
Queens = [2, 4, 1, 3] .

?- queens(5,Queens).
Queens = [1, 3, 5, 2, 4] .

?- queens(7,Queens).
Queens = [1, 3, 5, 7, 2, 4, 6] .
```


---
## SET 7: 
## a) Write a prolog program for binary search trees.
### Source Code:
```pl
% Check if an element is in a binary tree
in(X, t(_, X, _)).
in(X, t(L, _, _)) :- 
    in(X, L). 
in(X, t(_, _, R)) :- 
    in(X, R).

% Check if an element is in a binary search tree
in(X, t(_, X, _)).
in(X, t(Left, Root, Right)) :-
    gt(Root, X), 
    in(X, Left). 
in(X, t(Left, Root, Right)) :-
    gt(X, Root), 
    in(X, Right).

% Add an element to a binary search tree
add(Tree, X, NewTree) :-
    addroot(Tree, X, NewTree). 
add(t(L, Y, R), X, t(L1, Y, R)) :-
    gt(Y, X),
    add(L, X, L1). 
add(t(L, Y, R), X, t(L, Y, R1)) :-
    gt(X, Y), 
    add(R, X, R1). 

% Add an element to an empty tree
addroot(nil, X, t(nil, X, nil)). 
addroot(t(L, Y, R), X, t(L1, X, t(L2, Y, R))) :-
    gt(Y, X), 
    addroot(L, X, t(L1, X, L2)). 
addroot(t(L, Y, R), X, t(t(L, Y, R1), X, R2)) :-
    gt(X, Y), 
    addroot(R, X, t(R1, X, R2)).

% Display a binary tree
show(Tree) :-
    show2(Tree, 0).
show2(nil, _).
show2(t(Left, X, Right), Indent) :-
    Ind2 is Indent + 2, 
    show2(Right, Ind2), 
    tab(Indent), write(X), nl, 
    show2(Left, Ind2).

```
### Output
```bash
?- in(3, t(t(nil, 1, nil), 2, t(nil, 3, nil))).
true .

?- add(t(t(nil, 1, nil), 2, t(nil, 3, nil)), 4, NewTree).
NewTree = t(t(nil, 1, nil), 2, t(nil, 3, t(nil, 4, nil))).

?- show(t(t(nil, 1, nil), 2, t(nil, 3, nil))).
  3
2
  1
true.

?- add(nil, 5, D1),
|    add(D1, 3, D2).
D1 = t(nil, 5, nil),
D2 = t(t(nil, 3, nil), 5, nil) .

?- add(D2, 8, D3),
add(D3, 6, D4),
|    show(D3).|    
8
  6
D2 = nil,
D3 = t(nil, 8, nil),
D4 = t(t(nil, 6, nil), 8, nil) .
```

## b) Write predicates one converts centigrade temperatures to Fahrenheit, the other checks if a temperature is below freezing.

### Source Code:

```pl
c_to_f(C,F):-
   F is C*9/5+32.
frezzing(F):-
   F=<32.
```

### Output:

```bash
Ȁ% c:/users/harsh/onedrive/documents/prolog/exp2 compiled 0.00 sec, -1 clauses
?- c_to_f(100,X).
X = 212.

?- frezzing(15).
true.

?- c_to_f(32,X).
X = 89.6.
```

---