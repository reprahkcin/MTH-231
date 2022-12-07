# Chapter 1
## Section 1 - Propositional Logic
- **Proposition** - A declarative sentence that is either true of false, but not both.
- **Tautology** - A compound proposition that always evaluates to true
- **Contradiction** - A compound proposition that always evaluates to false

### How to build a truth table
1. Create columns for every variable ($2^n$ rows to allow for all combinations)
2. Create columns for every single expression
3. Create columns for compound expressions
4. Create column for complete expression

### Precedence of Logical Operators
1. $\neg$
2. $\land$
3. $\lor$
4. $\implies$
5. $\iff$

### Implication/Conditional 
$P\implies Q$

| $P$ | $Q$ | $P\implies Q$ |
|:---:|:---:|:-------------:|
|  T  |  T  |       T       |
|  T  |  F  |       F       |
|  F  |  T  |       T       |
|  F  |  F  |       T       |

#### Converse 
$Q\implies P$
#### Inverse 
$\neg P\implies\neg Q$
#### Contrapositive 
$\neg Q\implies\neg P$

### Bi-Conditional 
$P\iff Q$

| $P$ | $Q$ | $P\iff Q$ |
|:---:|:---:|:-------------:|
|  T  |  T  |       T       |
|  T  |  F  |       F       |
|  F  |  T  |       F      |
|  F  |  F  |       T       |


## Section 2 - Applications of Propositional Logic

### Example 1:
"You can access the Internet from campus only if you are a computer science major or you are not a freshman"
$a\implies (c\lor\neg f)$

### Example 2:
"You cannot ride the roller coaster if you are under 4 feet tall unless you are older than 16 years old."
$(r\land\neg s)\implies\neg q$

## Section 3 - Propositional Equivalences

### Identity Laws
$P\land T\equiv P$
$P\lor F\equiv P$
### Domination Laws
$P\lor T\equiv T$
$P\land F\equiv F$
### Idempotent Laws
$P\lor P\equiv P$
$P\land P\equiv P$
### Double Negation Law
$\neg (\neg P)\equiv P$
### Absorption Law
$P\lor (P\land Q)\equiv P$
$P\land (P\lor Q)\equiv P$
### Negation Laws
$P\lor \neg P\equiv T$
$P\land \neg P\equiv F$
### Commutative Laws - Order
$P\lor Q\equiv Q\lor P$
$P\land Q\equiv Q\land P$
### Associative Laws - Grouping
$(P\lor Q)\lor R\equiv P\lor(Q\lor R)$
$(P\land Q)\land R\equiv P\land(Q\land R)$
### Distributive Laws
$P\lor (Q\land R)\equiv (P\lor Q)\land (P\lor R)$
$P\land (Q\lor R)\equiv (P\land Q)\lor (P\land R)$
### DeMorgan's Laws
$\neg (P\land Q)\equiv \neg P\lor \neg Q$
$\neg (P\lor Q)\equiv \neg P\land \neg Q$
### More...
#### Conditional
$P\implies Q\equiv \neg P\lor Q$
$P\implies Q\equiv \neg Q\implies\neg P$
$P\lor Q\equiv\neg P\implies Q$
$P\land Q\equiv\neg (P\implies\neg Q)$
$(P\implies Q)\land (P\implies R)\equiv P\implies (Q\land R)$
$(P\implies R)\land (Q\implies R)\equiv (P\land Q)\implies R$
$(P\implies Q)\lor (P\implies R)\equiv P\implies (Q\lor R)$
$(P\implies R)\lor (Q\implies R)\equiv (P\lor Q)\implies R$
#### Bi-Conditional
$P\iff Q\equiv (P\implies Q)\land(Q\implies P)$
$P\iff Q\equiv\neg P\iff\neg Q$
$P\iff Q\equiv (P\land Q)\lor(\neg P\land\neg Q)$
$\neg (P\iff Q)\equiv P\iff \neg Q$

## Section 4 - Predicates and Quantifiers

### DeMorgan's Laws for Quantifiers

|      Negation       | Equivalent Statement |          When is Negation True?           |               When False?                |
|:-------------------:|:--------------------:|:-----------------------------------------:|:----------------------------------------:|
| $\neg\exists xP(x)$ | $\forall x\neg P(x)$ |      For every $x$, $P(x)$ is false       | There is an $x$ for which $P(x)$ is true |
| $\neg\forall xP(x)$ | $\exists x\neg P(x)$ | There is an $x$ for which $P(x)$ is false |       $P(x)$ is true for every $x$       |

## Section 5 - Nested Quantifiers

### Order of Quantifiers

###### Let $Q(x,y)$ denote $x+y=5$. Assume the domain is real numbers ($\mathbb{R}$)

Is $\forall x\exists yQ(x,y)$ true?
	For all real #'s $x$, there exists a real # $y$ such that $x+y=5$.
	**true**
	
Is $\exists y\forall xQ(x,y)$ true?
	There exists a real # $y$, such that for all real #'s $x$, $x+y=5$.
	**false**

### Translating Mathematical Statements into statements involving Nested Quantifiers

###### Translate "The sum of two positive integers is always positive" into a logical expression.

For all positive integers $x$ and $y$, $x+y>0$.

$\forall x\forall y((x>0)\land (y>0))\implies (x+y>0)$, $domain=\mathbb{Z}$

If $x>0$ and $y>0$, then adding them will also be $>0$

### Translating from Nested Quantifiers into English

###### Let $E(x,y)$ denote "$x$ sent $y$ an email" and $T(x,y)$ denote "$x$ sent $y$ a text". Translate the following into predicate logic, with a domain of "students in class."

1. Every student in the class sent an email to Joe.
	$\forall xE(x,Joe)$
	All students sent emails to Joe, Joe included.
	
	$\forall x((x\neq Joe)\implies E(x, Joe))$
	All students who are not Joe, sent an email to Joe.

1. There is a student in class who has not received a text or email from any other student in class.
	$\exists y\forall x((x\neq y)\implies\neg (E(x,y)\lor T(x,y)))$
	There exists a student who has not received an email or text.
	
	$\exists y\forall x((x\neq y)\implies (\neg E(x,y)\land\neg T(x,y)))$
	There exists a student who has not received an email and not received a text.

### Negating Nested Quantifiers

###### Negate the statement: 
$\neg\exists m\forall a\exists f(P(m,f)\land Q(f,a))$
$\color{LimeGreen}{\forall m\neg}$$\forall a\exists f(P(m,f)\land Q(f,a))$
$\forall m$$\color{LimeGreen}{\exists a\neg}$$\exists f(P(m,f)\land Q(f,a))$
$\forall m$$\exists a$$\color{LimeGreen}{\forall f\neg}$$(P(m,f)\land Q(f,a))$
$\forall m$$\exists a$$\forall f$$($$\color{LimeGreen}{\neg}$ $P(m,f)$$\color{LimeGreen}{\lor}$$\color{LimeGreen}{\neg}$$Q(f,a))$ - DeMorgan

## Section 7 - Introduction to Proofs
- **Even Integer**
	- $n=2k$, $k\in\mathbb{Z}$
- **Odd Integer**
	- $n=2k+1$, $k\in\mathbb{Z}$ 
- **Rational**
	- $\cfrac{a}{b}$, where $a,b\in\mathbb{Z}$, $b\neq 0$, and $a$ and $b$ have no common factors.

### Direct proof

$P\implies Q$
Assume P is true, prove Q is true.

###### "If $n$ is an odd integer, then $n^2$ is odd"

1. Assume $n$ is an odd integer.
2. Then 
	$n=2k+1$ for some $k\in\mathbb{Z}$
3. Substitute. 
	$(n)^2=(2k+1)^2$
4. FOIL. 
	$n^2=4k^2+4k+1$
5. Factor out 2 from RHS. 
	$n^2=2(2k^2+2k)+1$
	Alternate form: $n^2=2r+1$ where $r=2k^2+2k$ and $r\in\mathbb{Z}$ 
6. $\therefore$  $n$ is odd.

###### "The sum of two even integers is even"

1. Assume $a$ and $b$ are even integers.
2. Then,
	$a=2k$ for some $k\in\mathbb{Z}$
	$b=2m$ for some $m\in\mathbb{Z}$
3. Substitute.
	$a+b=2k+2m$
4. Factor out 2 from RHS.
	$a+b=2(k+m)$
	Alternate form: $a+b=2r$, where $r=k+m$ and $r\in\mathbb{Z}$
5. $\therefore$  The sum of two even integers is even.

### Indirect Proofs

#### Proof by Contraposition

$\neg Q\implies \neg P$
Assume Q is false

###### "If $n$ is an integer, and $3n+2$ is odd, then $n$ is odd"

1. Assume $\neg Q$. 
	$n$ is **NOT** odd, $n$ is even.
2. Then,
	$n=2k$ for some $k\in\mathbb{Z}$
3. Substitute.
	$3n+2=3(2k)+2$
4. Simplify.
	$3n+2=6k+2$
5. Factor out 2 from RHS
	$3n+2=2(3k+1)$
	Alternate form: $3n+2=2r, where $r=3k+1$ and $r\in\mathbb{Z}$
6. $\therefore$  $3n+2$ is even. 
	Since $\neg Q\implies\neg P$ is true,
	then $P\implies Q$ is true by contraposition.

###### "If $n$ is an integer, and $3n+2$ is even, then $n$ is even"

1. Assume $\neg Q$.
	$n$ is **NOT** even, $n$ is odd.
2. Then,
	$n=2k+1$ for some $k\in\mathbb{Z}$
3. Substitute.
	$3n+2=3(2k+1)+2$
4. Simplify.
	$3n+2=6k+3+2$
	$3n+2=6k+5$
5. Factor out 2 from RHS
	$3n+2=2(3k+2)+1$
	Alternate form:
	$3n+2=2r+1$, where $r=3k+2$ and $r\in\mathbb{Z}$
6. $\therefore$  $3n+2$ is odd.
	Since $\neg Q\implies\neg P$ is true,
	then $P\implies Q$ is true by contraposition.

#### Proof by Contradiction

$\neg P\implies (Q\land\neg Q)$

Assume a proposition is not true, then through that premise and logic, find a contradiction that shows the premise must have been incorrect, and therefore, the proposition was true.

For **one proposition**, $P$, assume $\neg P$ is true. Then find a contradiction that shows $\neg P$ is false, so $P$ is true.

###### "$\sqrt 2$ is irrational"

1. Assume $\neg P$.
	$\sqrt 2$ is **NOT** irrational. $\sqrt 2$ is rational.
2. Then,
	there exists 2 integers $a$ and $b$, such that $\sqrt 2=\cfrac{a}{b}$, $b\neq 0$, and $a$ and $b$ have no common factors.
3.  Simplify
	$\sqrt 2=\cfrac{a}{b}$
	$(\sqrt 2)^2=(\cfrac{a}{b})^2$
	$2=\cfrac{a^2}{b^2}$
	$2b^2=a^2$
	Alternate form:
	$a=2c$ for some $c\in\mathbb{Z}$
4. $\therefore$  $a$ must be even.
5. Substitute $2c$ for $a$
	$2b^2=(2c)^2$
	$2b^2=4c^2$
	$b^2=2c^2$
	Alternate form:
	$b=2c$
6. $\therefore$  $b$ must be even.
7. If both $a$ and $b$ are even, then they share a common factor of 2.
8. $\therefore$  $\sqrt 2$ is irrational by contradiction.
	
For an **implication**, $P\implies Q$, assume $P$ and $\neg Q$ are true, then find a contradiction that shows either $P\implies Q$ or $\neg Q\implies\neg P$.

###### "If $n$ is an integer and $3n+2$ is even, then $n$ is even"

1. Assume $P$ and $\neg Q$.
	$3n+2$ is even, where $n\in\mathbb{Z}$
	$n$ is **NOT** even, $n$ is odd.
2. Then,
	If $3n+2$ is even, then $3n$ is even by subtraction of 2 even integers.
3. $3n-n$ must be odd by subtraction of an even and odd integer.
	However, $3n-n=2n$, which is even by definition, which is a contradiction.
4. $\therefore$  If $n\in\mathbb{Z}$ and $3n+2$ is even, then $n$ is even.

## Section 8 - Proof Methods and Strategy
When you are confronted with a statement to prove, you should first replace terms by their definitions and then carefully analyze what the hypothesis and the conclusion mean.

### Exhaustive Proof and Proof by Cases
Must cover all possible cases that arise cover entire domain.

###### "If $n$ is an integer, $n\leq n^2$. Domain = $\mathbb{Z}$"

**Case 1:** $n\leq -1$
	$n^2>0$
	$\therefore$ it follows $n\leq n^2$

**Case 2:** $n=0$
	$0\leq 0^2$
	$0\leq 0$
	$\therefore$ it follows $n\leq n^2$

**Case 3:** $n\geq 1$
	$n\geq 1$
	$n^2\geq n$
	$\therefore$ it follows $n\leq n^2$

$\therefore$  Since $n\leq n^2$ for all values in our domain, we can conclude if $n\in\mathbb{Z}$, then $n\leq n^2$. 

###### "If $n$ is an integer, $n^2+3n+2$ is even"

**Case 1:** $n$ is even
	$n=2k$ for some $k\in\mathbb{Z}$
	$n^2+3n+2=(2k)^2+3(2k)+2$
	$n^2+3n+2=4k^2+6k+2$
	$n^2+3n+2=2(2k^2+3k+1)$
	Alternate form:
	$n^2+3n+2=2r$ where $r=2k^2+3k+1$ and $r\in\mathbb{Z}$
	$\therefore$  $n$ is even

**Case 2:** $n$ is odd
	$n=2m+1$ for some $m\in\mathbb{Z}$
	$n^2+3n+2=(2m+1)^2+3(2m+1)+2$
	$n^2+3n+2=4m^2+4m+1+6m+3+2$
	$n^2+3n+2=4m^2+10m+6$
	$n^2+3n+2=2(2m^2+5m+3)$
	Alternate form:
	$n^2+3n+2=2l$ where $l=2m^2+5m+3$ and $l\in\mathbb{Z}$
	$\therefore$  $n$ is even

**Case 3:** $n=0$
	$n^2+3n+2=(0)^2+3(0)+2$
	$n^2+3n+2=0+0+2$
	$n^2+3n+2=2$
	$\therefore$  $n$ is even

$\therefore$  $n^2+3n+2$ is even if $n\in\mathbb{Z}$.

### Existence Proofs

#### Constructive
Find value for which $P(c)$ is true.

###### "There exists a pair of consecutive integers such that one integer is a perfect square and the other is a perfect cube"

|         |  1  |  2  |  3  |  4  |  5  |  6  |
|:------- |:---:|:---:|:---:|:---:|:---:|:---:|
| Squares |  1  |  4  |  <span style="color: red;">9</span>  | 16  | 25  | 36  |
| Cubes   |  1  |  <span style="color: red;">8</span>  | 27  | 64  | 125 | 216    |

$\therefore$  $2^3=8$ and $3^2=9$, so there exists a pair of consecutive integers such that one is a perfect square and the other is a perfect cube.

#### Non-Constructive
Assume no values make $P(c)$ true, then contradict.

###### "There is a rational number $x$ and irrational number $y$ such that $x^y$ is irrational"

Let $x=4$ (rational) and $y=\sqrt 2$ (irrational)
$4^\sqrt 2$ is irrational

### Uniqueness Proofs

###### "If $a$ and $b$ are real numbers, and $a\neq 0$, then there is a unique real number such that $ar+b=0$"

#### Existence: 
We show an element $x$ with that property ($ar+b=0$) exists.
1. Let $r=\cfrac{-b}{a}$. That's $ar+b=0$ solved for $r$.
2. Then $r$ is a solution to $ar+b=0$.
3. Plug it in:
	$a(\cfrac{-b}{a})+b=0$
	$-b+b=0$
	$0=0$
	
#### Uniqueness: 
We show $a\neq b$, then $b$ does not have that property.
1. Suppose $s$ is a real number such that $as+b=0$
2. Then $ar+b=as+b$
	$ar=as$
	$r=s$
3. $\therefore$  $r$ must equal $s$ for this to be true, proving uniqueness.

# Chapter 2

## Section 1 - Sets
- A **set** is an unordered collection of distinct objects, called elements or members of the set. A set is said to contain its elements.
- **Elements** are objects in a set.
- Two sets are **equal** if and only if they have the same elements. Therefore, if A and B are sets, then A and B are equal if and only if $\forall x(x\in A\iff x\in B)$.
	- $\set{0,1,1,3,4,4}=\set{0,1,3,4}$
- The set A is a **subset** B ($A\subseteq B$), and B is a **superset** of A ($B\supseteq A$), if and only if every element of A is also an element of B. 
- If B is a **proper subset** of A, then all elements of B are in A but A contains at least one element that is not in B.
	- If $A=\set{1,3,5}$ and $B=\set{1,5}$
	- $B\subset A$
- For every set $S$, $\emptyset\subseteq S$ and $S\subseteq S$.
- Given a set $S$, the **power set** of $S$ is the set of all subsets of the set $S$.
	- $A=\set{0,1,2}$
	- $\mathcal{P}(A)=\set{\emptyset,\set{0},\set{1},\set{2},\set{0,1},\set{0,2},\set{1,2},\set{0,1,2}}$
	- $|\mathcal{P}(A)|=8$ ($2^n$ for $n$ elements)
- The **cardinality** of a set is a measure of a set's size, meaning the number of elements in the set.
	- $|alphabet|=26$
- A **tuple** is an ordered collection that has $a$, as its first element, $a_2$ as its second, and so on until $a_n$.
	- $(a_1,a_2,...,a_n)$
	- Ordered pairs: $(a_1,a_2)$ - $(5,2)\neq(2,5)$
- Let $A$ and $B$ be sets. The **Cartesian product** of $A$ and $B$ is the set of all ordered pairs $(a,b)$.
	- Let $A=\set{1,2}$ and $B=\set{a,b,c}$
	- $A\bigtimes B=\set{(1,a),(1,b),(1,c),(2,a),(2,b),(2,c)}$
- A **truth set** of $P$ is the set of elements $x$ in $D$ such that $P(x)$ is true.
	- Notation: $\set{x\in D|P(x)}$
		$D$: $\mathbb{Z}$
		$P(x)$: $|x|=3$
		Truth set: $\set{-3,3}$

### Important Sets
$\mathbb{N}$ - Natural Numbers (Counting)
$\mathbb{W}$ - Whole Numbers ($\mathbb{N}+0$)
$\mathbb{Z}$ - Integers ($^+_-\mathbb{W}$)
$\mathbb{Q}$ - Rational ($\cfrac{a}{b}$, where $b\neq 0$, $(a,b)\in\mathbb{Z}$, and $\cfrac{a}{b}$ is in lowest terms)
$\mathbb{R}$ - Real Numbers ($\mathbb{N,W,Z,Q}$)
$\mathbb{C}$ - Complex Numbers ($a+b_i$)
$\mathbb{U}$ - Universal Set (everything under consideration)
$\emptyset$ - Empty Set

### Set Notation
#### Roster Notation
- Discrete sets
- Countable
- $S=\set{1,2,3,4,5}$

#### Set-Builder Notation
- Can be discrete or continuous sets
- $S=\set{x|x\in\mathbb{N},x\leq 5}$

#### Interval Notation
- Continuous sets
- $B=\set{x|0\leq x\leq 1}$ in interval notation is $[0,1]$
- $M=\set{x|0<x<1}$ in interval notation is $(0,1)$

## Section 2 - Set Operations

![[unionofsets.svg | 600]]

### Union of Sets
A **union** of a collection of sets is the set that contains those elements that are members of at least one set in the collection.
- Let $A$ and $B$ be sets. The **union** of the sets $A$ and $B$, denoted by $A\cup B$, is the set that contains those elements that are either in $A$ or in $B$, or in both.
- Addition - $\lor$ - 'or' - disjunction
- Let $A,B$ be sets. The **union** of the sets $A$ and $B$ is:
	- $A\cup B=\set{x|x\in A\lor x\in B}$
	- $A=\set{1,4,7}$
	- $B=\set{4,5,6}$
	- $A\cup B=\set{1,4,5,6,7}$

### Intersection of Sets
The **intersection** of a collection of sets is the set that contains those elements that are members of all the sets in the collection.
- Let $A$ and $B$ be sets. The **intersection** of the sets $A$ and $B$, denoted by $A\cap B$, is the set containing those elements in both $A$ and $B$.
- Multiplication - $\land$ - 'and' - conjunction
- Let $A,B$ be sets. The **intersection** of the sets $A$ and $B$ is:
	- $A\cap B=\set{x|x\in A\land x\in B}$
	- $A=\set{1,4,7}$
	- $B=\set{4,5,6}$
	- $A\cap B=\set{4}$

### Difference of Sets
- Let $A$ and $B$ be sets. The **difference** of the sets $A$ and $B$, denoted by $A-B$, is the set containing those elements that are in $A$ but not in $B$. The difference of $A$ and $B$ is also called the **complement** of $B$ with respect to $A$.
- Subtraction - $\neg$ - 'not' - complement
- Let $A,B$ be sets. The **difference** of the sets $A$ and $B$ is:
	- $A-B=\set{x|x\in A\land x\notin B}$
	- $A=\set{1,4,7}$
	- $B=\set{4,5,6}$
	- $A-B=\set{7,1}$

### Order of Operations
| Order |   Logic    |  Set   | Arithmetic |    English     |                |     |
|:-----:|:----------:|:------:|:----------:|:--------------:|:--------------:|:---:|
|   1   |   $\neg$   |        |     -      |      not       |    complement    |  difference   |
|   2   |  $\land$   | $\cap$ |  $\times$  |      and       |  conjunction   |  intersection   |
|   3   |   $\lor$   | $\cup$ |     +      |       or       |  disjunction   |  union   |
|   4   | $\implies$ |        |            |    if/then     |  implication   |     |
|   5   |   $\iff$   |        |            | if and only if | bi-conditional |     |

### Set Identities
| Identity                                          | Name                |
|:------------------------------------------------- |:------------------- |
| $A\cap U=A$                                       | Identity Laws       |
| $A\cup\emptyset =A$                               |                     |
| $A\cup U=U$                                       | Domination Laws     |
| $A\cap\emptyset =\emptyset$                       |                     |
| $A\cup A=A$                                       | Idempotent Laws     |
| $A\cap A=A$                                       |                     |
| $\overline{(\overline{A})}=A$                     | Complementation Law |
| $A\cup B=B\cup A$                                 | Commutative Laws    |
| $A\cap B=B\cap A$                                 |                     |
| $A\cup (B\cup C)=(A\cup B)\cup C$                 | Associative Laws    |
| $A\cap (B\cap C)=(A\cap B)\cap C$                 |                     |
| $A\cup (B\cap C)=(A\cup B)\cap (A\cup C)$         | Distributive Laws   |
| $A\cap (B\cup C)=(A\cap B)\cup (A\cap C)$         |                     |
| $\overline{A\cap B}=\overline{A}\cup\overline{B}$ | DeMorgan's Laws     |
| $\overline{A\cup B}=\overline{A}\cap\overline{B}$ |                     |
| $A\cup (A\cap B)=A$                               | Absorption Laws     |
| $A\cap(A\cup B)=A$                                |                     |
| $A\cup\overline{A}=U$                             | Complement Laws     |
| $A\cap\overline{A}=\emptyset$                     |                     |
## Section 3 - Functions
- A **function** $f$ from $A$ to $B$, denoted $f:A\to B$, assigns each element of $A$ to exactly one element of $B$. Functions may also be called **mappings** or **transformations**.
- **Explicit Statement:** $f(A)=1$ ($A$ maps to $1$)
- **Formula:** $f(x)=x^2+1$

###### Answer the following for $f:X\to Y$
![[Function.excalidraw]]
- Domain: $X$
- CoDomain: $Y$
- Range: $\set{1,2}$
- Preimage of $2$: $D$
- Image(s) of A: $\set{1}$
- $f(D)=2$

### One-to-One Functions
$\forall a\forall b((a\neq b)\implies (f(a)\neq f(b)))$
For all $a$ and for all $b$, if $a$ and $b$ are not the same element, then both $a$ and $b$ will be mapped to different elements in the range.

### Onto Functions
Every element in the codomain maps to at least one element in the domain.
$\forall y\exists x(f(x)=y)$
For all $y$'s, there exists some $x$ such that $x$ maps to $y$. 

### Bijective Functions
A function that is both **One-to-One** and **Onto** simultaneously.

# Chapter 5

## Section 1 - Mathematical Induction
To prove $P(x)$ is true for $x\in\mathbb{Z}^+$, where $P(x)$ is a propositional function, we complete two steps:
1. Basis Step - Verify $P(1)$ is true.
2. Inductive Step - Verify $P(k)\implies P(k+1)$ for $\forall k\in\mathbb{Z}^+$
	- Inductive hypothesis: $P(k)$ is true
	- Must show: $P(k)\implies P(k+1)$

Conclusion: $P(x)$ is true $\forall k\in\mathbb{Z}^+$

### Step-by-step

###### Prove: $\sum\limits^{n}_{i=1}i=\cfrac{n(n+1)}{2}$

##### 1. Define components
Let $P(n)$: $1+2+3 +...+n=\cfrac{n(n+1)}{2}$

##### 2. Basis Step 
Verify $P(lowestValue)$ is true.
$P(1)$: $1=\cfrac{1(1+1)}{2}=\cfrac{1(2)}{2}=1$

##### 3. Inductive Step
$P(k)\implies P(k+1)$

1. Inductive Hypothesis: 
	$\color{LimeGreen}{1+2+3+...+k=\cfrac{k(k+1)}{2}}$

2. Must Show:
	$1+2+3+...+k+(k+1)=\cfrac{(k+1)((k+1)+1)}{2}=\color{Pink}{\cfrac{(k+1)(k+2)}{2}}$

3. Take Inductive Hypothesis and add $(k+1)$ to both sides:
	$\color{LimeGreen}{1+2+3+...+k}$$+(k+1)$$\color{LimeGreen}{=\cfrac{k(k+1)}{2}}$$+(k+1)$

4. Use math magic to make RHS look like Must Show:
	$=\cfrac{k(k+1)}{2}+\cfrac{2(k+1)}{2}$ - Multiply $(k+1)$ by $\cfrac{2}{2}$
	$=\cfrac{k(k+1)+2(k+1)}{2}$ - Add fractions together with common denominator.
	$=\color{Pink}{\cfrac{(k+1)(k+2)}{2}}$ - Factor out $(k+1)$, and now it matches Must Show.

##### 4. Summarize
$\therefore$  $P(n)$ is true for $\forall n\in\mathbb{Z}^+$

### Proving an Inequality

###### Prove $n<2^n$ for $\forall n\in\mathbb{Z}^+$ using mathematical induction

##### 1. Define components
Let $P(n)$: $n<2^n$ $\forall n\in\mathbb{Z}^+$

##### 2. Basis Step 
Verify $P(lowestValue)$ is true.
$P(1)$: $1<2^1=$ true

##### 3. Inductive Step
$P(k)\implies P(k+1)$

1. Inductive Hypothesis: 
	$\color{LimeGreen}{k<2^k}$

2. Must Show:
	$k+1<\color{Pink}{2^{k+1}}$

3. Take Inductive Hypothesis and add $1$ to both sides:
	$\color{LimeGreen}{k}$$+1$$\color{LimeGreen}{<2^k}$$+1$

4. Use math magic to make RHS look like Must Show:
	- Because $2^k$ was proven to be $>1$ in the basis step, we can substitute $2^k$ for $1$ on the RHS of the inequality because it does not break it. $k+1<2^k+2^k$
	- Then, because $2^k$ and $2^k$ have the same base, you can just add the exponents, resulting in $\color{Pink}{2^{k+1}}$, the Must Show.
##### 4. Summarize
$\therefore$  $n<2^n$ is true for $\forall n\in\mathbb{Z}^+$
## Section 2 - Strong Induction and Well-Ordering
- **The Well-Ordering Principle** - Every non-empty set of non-negative integers has a least element.

###### Prove that every connected graph with $n$ vertices has at least $n−1$ edges.

##### 1. Basis Step
Verify $P(lowestValue)$ is true.
Every connected graph with 1 vertex has  0 edges. 

##### 2. Inductive Step
$P(k)\implies P(k+1)$

1. Inductive Hypothesis:
	Let $k\in N$. Assume every connected graph on i vertices where $1\leq i\leq k$ has at least  $i−1$ edges. 

2. Must Show:
	Let $G$ be a connected graph on $k+1$ vertices. We want to show that $G$ has at least  $k$ edges.  

3. Remove edges from $G$ until the resulting graph has two connected components, $G_1$  and $G_2$ on $k_1$ and $k_2$ vertices respectively. 

4. Then $1\leq k1\leq k$, $1\leq k2\leq k$ and  $k1 + k2 = k + 1$. By the induction hypothesis, $G_1$ has at least $k_1 − 1$ edges and $G_2$  has at least $k_2 − 1$ edges. 

5. Since at least one edge was removed, there must have been  at least $(k_1 − 1) + (k_2 − 1) + 1 = k_1 + k_2 − 1 = k$ edges in $G$. 
		That completes the  proof by induction $\square$

## Section 3 - Recursive Definitions and Structural Induction

### Recursively Defined Functions
1. **Basis Step**
	- Initial conditions
	- Specifies the value of the function for the first term(s)
2. **Recursive Step**
	- Function
	- Gives a rule for finding subsequent values using a previous value(s) beginning at those defined in the basis step.

###### If $f$ is defined recursively by $f(0)=2$ and $f(n+1)=3f(n)-1$, find $f(1)$, $f(2)$, $f(3)$, and $f(4)$.

##### 1. Initial Conditions (Basis Step)
	$f(0)=2$
##### 2. Function (Recursive Step)
	$f(n+1)=3f(n)-1$

$f(1)=3f(0)-1=3(2)-1=5$
$f(2)=3f(1)-1=3(5)-1=14$
$f(3)=3f(2)-1=3(14)-1=41$
$f(4)=3f(3)-1=3(41)-1=122$

###### Fibonacci Numbers
Recall the set of Fibonacci numbers:
$0,1,1,2,3,5,8,13,21...$

How is each number found?
Answer: Add the 2 previous terms.

##### 1. Initial Conditions (Basis Step)
	$f_0=0$
	$f_1=1$
##### 2. Function (Recursive Step)
	$f_n=f_{n-1}+f_{n-2}, n\geq 2$
	Because $f_n$ needs access to **two** previous values, $n$ starts at $2$.


# Chapter 6

## Section 1 - The Basics of Counting

### The Product Rule
Suppose that a procedure can be broken down into a sequence of two tasks. If there are $n_1$ ways to do the first task and for each of these ways of doing the first task, there are $n_2$ ways to do the second task, then there are $n_1n_2$ ways to do the procedure.

###### 4 t-shirts and 3 pairs of pants - How many combinations?

$4\cdot3=12$ combinations

### The Sum Rule
If a task can be done either in one of $n_1$ ways or in one of $n_2$ ways, where none of the set of $n_1$ ways is the same as any of the set of $n_2$ ways, then there are $n_1 + n_2$ ways to do the task.

###### A menu with 10 items, a menu with 5 items. No crossover.

$10+5=15$ possibilities

### The Subtraction Rule
If a task can be done in either $n_1$ ways or $n_2$ ways, then the number of ways to do the task is $n_1+n_2$ minus the number of ways to do the task that are common to both ways. (intersection)

###### 8-bit string
~~~
Starts with 1  - 1   2 x 2 x 2 x 2 x 2 x 2 x 2
Ends with 000  - 2 x 2 x 2 x 2 x 2   0   0   0
Both           - 1   2 X 2 X 2 X 2   0   0   0
~~~

$2^6 \cdot 2^4 - 2^3$
$|A_1 \cup A_2|= |A_1|+|A_2|-|A_1 \cap A_2|$

### The Division Rule
There are $\cfrac{n}{d}$ ways to do a task if it can be done using a procedure that can be carried out in $n$ ways, and for every way $w$, exactly $d$ of the $n$ ways correspond to way $w$. 

## Section 2 - The Pigeonhole Principle

### The Pigeonhole Principle
If $k$ is a positive integer and $k+1$ or more objects are placed into $k$ boxes, then there is at least one box containing two or more of the objects. 

**7 pigeons, 6 boxes**

### The Generalized Pigeonhole Principle
If $N$ objects are placed into $k$ boxes, then there is at least one box containing at least $\lceil \cfrac{N}{k} \rceil$ objects.

**7 pigeons, 6 boxes - $\lceil \cfrac{7}{6} \rceil = 1.1\overline{6}$** 

## Section 3 - Permutations and Combinations

### Permutations
An ordered arrangement of distinct objects. An $r$-permutation is the arrangement of $r$ elements of a set. 

###### Let $S=\{A,B,C\}$. Find all 2-permutations

 $P(n,r)$

$\cfrac{n!}{(n-r)!}=\cfrac{3!}{(3-2)!}=6$

### Combinations
An unordered arrangement of elements of a set. An $r$-combination is a subset of the set with $r$ elements. 
$n=|S|$

###### Let $S=\{A,B,C\}$. Find all 2-combinations

$C(n,r)$

$\cfrac{n!}{(n-r)!r!}=\cfrac{3!}{(3-2)!2!}=\cfrac{3\cdot2\cdot1}{1\cdot2\cdot1}=\cfrac{6}{2}=3$

### Permutation and Combination Reference

---

###### How many ways can we pick 3 students out of a group of 5 to stand in a line? (order matters)
$P(n,r)$ without repetition - $\cfrac{n!}{(n-r)!}$
$P(5,3) = \cfrac{5!}{2!} = 60$

----

###### How many possible 5-card hands are there in a deck of 52 cards? (order does not matter)
$C(n,r)$ without repetition - $\cfrac{n!}{(n-r)!r!}$ 
$C(52,5) = \cfrac{52!}{47!5!} = 2,598,960$

---

###### How many strings of length $r$ can be formed from letters in the alphabet?
$P(n,r)$ with repetition - $n^r$
$26^r$

---

###### How many ways are there to choose a dozen donuts from 21 varieties?
$C(n,r)$ with repetition - $\cfrac{(n+r-1)!}{(n-1)!r!}$
$C(12+21-1,12)=C(32,12)$

---
## Section 4 - Binomial Coefficients and Identities
- The total number of terms in the expansion of $(x=Y)^n$ are $(n+1)$
- The sum of exponents of $x$ and $y$ is always $n$
- The binomial coefficients which are equidistant from the beginning and from the ending are equal: $nC_0 = nC_n, nC_1 = nC_n-1 , nC_2 = nC_n-2$

### Pascal's Triangle

|     |     |     |     |     |     |     |     |     |     |     |     |     |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|     |     |     |     |     |     |  1  |     |     |     |     |     |     |
|     |     |     |     |     |  1  |     |  1  |     |     |     |     |     |
|     |     |     |     |  1  |     |  2  |     |  1  |     |     |     |     |
|     |     |     |  1  |     |  3  |     |  3  |     |  1  |     |     |     |
|     |     |  1  |     |  4  |     |  6  |     |  4  |     |  1  |     |     |
|     |  1  |     |  5  |     | 10  |     | 10  |     |  5  |     |  1  |     |
|  1  |     |  6  |     | 15  |     | 20  |     | 15  |     |  6  |     |  1  |

## Section 5 - Generalized Permutations and Combinations
### Permutations with Repetition
The number of $r$-permutations of a set of $n$ objects, with repetition allowed is $n^r$. 

### Combinations with Repetition
There are $C(n+r-1, r)=C(n+r-1, n-1)$ $r$-combinations from a set with $n$ elements when repetition of elements is allowed. 

### Permutations with Indistinguishable Objects
The number of different permutations of $n$ objects, where there are $n_1$ indistinguishable objects of type 1, $n_2$ indistinguishable objects of type 2, ..., and $n_k$ indistinguishable objects of type $k$, is 

 $\cfrac{n!}{n_1!n_2!...n_k!}$

# Chapter 10

## Section 1 - Graphs and Graph Models
- **Graph** 
	- $G=(V,E)$ consists of $V$, a nonempty set of **vertices** (or **nodes**) and $E$, a set of **edges**. 
	- Each edge has either one or two vertices associated with it, called its **endpoints**. 
	- An edge is said to **connect** its endpoints.
- **Directed graph** (or **digraph**) 
	- $(V,E)$ consists of a nonempty set of vertices $V$ and a set of **directed edges** (or **arcs**) $E$. 
	- Each directed edge is associated with an ordered pair of vertices. 
	- The directed edge associated with the ordered pair $(u,v)$ is said to start at $u$ and end at $v$.
- **Simple Graph**
	- Each edge connects to two different vertices.
	- No two edges connect to the same two vertices.
- **Multigraph**
	- Multiple edges connect the same two vertices.
- **Loop**
	- An edge that connects a vertex to itself.
- **Pseudograph**
	- May include loops as well as multiple edges.


| Type                  | Edges                   | Multiple Edges Allowed? | Loops Allowed? |
| --------------------- | ----------------------- | ----------------------- | -------------- |
| Simple graph          | Undirected              | No                      | No             |
| Multigraph            | Undirected              | Yes                     | No             |
| Pseudograph           | Undirected              | Yes                     | Yes            |
| Simple directed graph | Directed                | No                      | No             |
| Directed multigraph   | Directed                | Yes                     | Yes            |
| Mixed graph           | Directed and undirected | Yes                     | Yes               |

## Section 2 - Graph Terminology and Special Types of Graphs

### Undirected Graphs
- An undirected graph has an even number of vertices of odd degree.

![[Drawing 2022-12-06 13.47.55.excalidraw]]

- **Adjacent** vertices (neighbors)
	- Vertices that are connected by an edge.
- **Incident**
	- Edge $E_B$ is incident to to $V_e$ and $V_b$
- **Neighborhood**
	- $N(A)=V_{v\in A}N(v)$
	- $N(e)=\set{a,b,c}$
- **Degree**
	- Number of edges connected to vertex
	- $deg(a)=4$
	- Loops count in and out for 2
- **Isolated**
	- Vertices with degree of 0
	- $V_d$
- **Pendant**
	- Degree of 1
	- $V_f$

### Handshaking Theorem

###### Suppose there are 6 people in a room, and each must shake hands with every other person. How many handshakes take place?

![[handshake]]

1. Find the sum of the degrees of each vertex
	- In this case, each vertex has a degree of 5, for a total of 30.
1. Divide that number by 2, to eliminate duplicates: 15

$G=(V,E)$ with $m$ edges

$2m=\sum\limits_{v\in V}deg(v)$

### Directed Graph

![[Undirected]]
- **Adjacent to**
	- $a$ is adjacent to $b$
- **Adjacent from**
	- $b$ is adjacent from $a$
- **Initial Vertex** $(a,b)$
	- $a$
- **Terminal/End Vertex** $(a,b)$
	- $b$
- **In-degree** of vertex: $v=deg^-(v)=|E|$
	- $deg^-(b)=2$
- **Out-degree** of vertex: $v=deg^+(v)=|E|$
	- $deg^+(b)=1$
- $\sum\limits_{v\in V}deg^-(v)=\sum\limits_{v\in V}deg^+(v)=|E|$
	- For a directed graph, the number of in-degrees is equal to the number of out-degrees is equal to the number of edges.

### Complete Graph
A **complete graph**, denoted $K_n$, is a simple graph that contains exactly one edge between each pair of $n$ distinct vertices. Everything is connected to everything.

![[Complete graphs]]

### Cycles and Wheels
#### Cycle
A **cycle** $C_n$, $n\geq 3$ (at least 3 vertices), consists of vertices $v_1, v_2, ... , v_n$ and edges $\set{v_1,v_2},\set{v_2,v_3}...\set{v_{n-1},v_n},\set{v_n,v_1}$
![[cycles]]
#### Wheel
A **wheel** $W_n$ is obtained when we add an additional vertex to $C_n$, and connect that vertex to each existing vertex.

![[wheels]]

#### Hypercube
An $n$-dimensional **hypercube**, or $n$-cube, denoted $Q_n$, is a graph with vertices representing the $2^n$ bit strings of length $n$. Adjacent vertices differ by exactly one bit-position.
- $YZX$
![[hypercube]]
### Bipartite Graphs
A graph is said to be **bipartite** if we can divide the set of vertices in two disjoint sets such that there is no edge between vertices belonging to same set.
- In a bipartite graph, the sum of degrees of vertices of each set is equal to the number of edges. 
- $\sum\limits_{v\in A} deg(v)=\sum\limits_{v\in B} deg(v)=|E|$
![[bipartite]]
### Graph Coloring 
A technique for determining whether or not a graph is bipartite. Graph coloring is the assignment of colors to each vertex in a graph such that no two adjacent vertices get the same color.

1. Start by coloring a vertex a specific color. List that in Set 1.
2. Next, color vertices that **ARE** adjacent to the first vertex, but **ARE NOT** adjacent to each other. The goal is to have no connections between members of the same set. List these newly colored vertices in Set 2.
3. Color the unlisted vertices adjacent to Set 2 with the Set 1 color. (Make sure they are not adjacent to the vertices in Set1).
4. Continue until all vertices are colored and listed. If the graph is bipartite, you will have connections between all members of both sets, but no connections between members of the same set.

### Complete Bipartite Graph
A complete bipartite graph $K_{m,n}$ is a bipartite graph with subsets of $m$ and $n$ vertices, respectively with an edge between each pair of vertices from opposite subsets.

![[complete bipartite]]

### Matching
###### Suppose Adam, Ben, Chris, David and Eric are training for tasks at work. Adam and Chris are training for task 1, Ben, Chris and Eric are training for task 2, David is training for task 3, Chris and Eric are training for task 4 and Eric is training for task 5. Create a graph to model this, then determine if a matching is possible.

![[Matching]]

### Hall's Theorem
The bipartite graph $G=(V,E)$ with bipartition $(V_1,V_2)$ has a complete matching from $V_1$ to $V_2$ if and only if $|N(A)|\geq|A|$ for all subsets $A$ of $V_1$.
- Hall's condition - $N(x)\geq |x|$
Gentlemen (domain) ask ladies (codomain) to marry, there's got to be enough ladies to gentlemen. 

## Section 3 - Representing Graphs and Graph Isomorphism


## Section 4 - Connectivity

## Section 5 - Euler and Hamilton Paths

### Euler Path 
A path which visits each edge of the graph exactly once.

### Euler Circuit 
A path which visits each edge of the graph exactly once, and finishes on the vertex it started on.

### Hamilton Path
A path in an undirected or directed graph that visits each vertex exactly once.
- The number of different Hamiltonian cycles in a complete undirected graph on $n$ vertices is $\cfrac{(n-1)!}{2}$ and in a complete directed graph on n vertices is $(n-1)!$. These counts assume that cycles that are the same apart from their starting point are not counted separately.

#### Hamilton Circuit
A cycle that visits each vertex exactly once.
- Least weight

## Section 6 - Shortest Path Problems

# Chapter 11

## Section 1 - Introduction to Trees

### Tree Terminology and Properties
- A **tree** is a connected undirected graph with no simple circuits.
- Theorem 1: An undirected graph is a tree if and only if there is a unique simple path between any two of its vertices.
- A tree with $n$ vertices has $n-1$ edges
- A full $m$-ary tree with $i$ internal vertices contains $n=mi+1$ vertices.
- A full $m$-ary tree with
	- $n$ vertices has $i=\cfrac{(n-1)}{m}$ internal vertices and $l=\cfrac{[(m-1)n+1]}{m}$ leaves
	- $i$ internal vertices has $n=mi+1$ vertices and $l=(m-1)i+1$ leaves
	- $l$ leaves has $n=\cfrac{(ml-1)}{(m-1)}$ vertices and $i=\cfrac{(l-1)}{(m-1)}$ internal vertices

### Balanced m-ary trees
- It is often desirable to use rooted trees that are "balanced" so that the subtrees at each vertex contain paths of approximately the same length. Some definitions will make this concept clear. 
- The level of a vertex $v$ in a rooted tree is the length of the unique path from the root to this vertex. 
- The level of the root is defined to be zero. 
- The height of a rooted tree is the maximum of the levels of vertices. In other words, the height of a rooted tree is the length of the longest path from the root to any vertex. 
- A rooted $m$-ary tree of height $h$ is balanced if all leaves are at levels $h$ or $h-1$.

### Rooted Tree Terminology
- A **rooted tree** is a tree in which one vertex has been designated as the root and every edge is directed away from the root.
- A rooted tree is called an **$m$-ary tree** if every internal vertex has no more than $m$ children. The tree is called a full $m$-ary tree if every internal vertex has exactly $m$ children. An $m$-ary tree with $m=2$ is called a binary tree.
- **m-ary tree** - most children on any one vertex - full has $m$-children on every vertex with children
- **binary tree** - two children max - full has two on every vertex with children
- **parent** - vertex with children
- **child** - vertex with parent
- **sibling** - vertices that share a parent
- **ancestor** - parent or above in line
- **descendants** - children and below
- **leaf** - end vertex
- **internal vertices** - vertex with at least one child
- **pendant** - edge with leaf 
- **subtree** - selected vertex as root and all descendants

### Edges vs. Vertices
$|Verts|=|Edges|+1$
$|Edges|-1=|Verts|$

### Tree Math
Let $T_1=<V_1,E_1>$ and $T_2=<V_2,E_2>$ be two trees with $|E_1|=11$ and $|V_2|=2|V_1|$.

$|V_1|=12$
$|V_2|=24$
$|E_2|=23$

## Section 2 - Applications of Trees

### Binary Search Trees

### Adjacency Matrix
- Two nodes are adjacent if an edge connects them
- Rows and columns are vertices, and there is a 1 for adjacent connection, 0 for none. 
	- Row-to-column $A\to B$
	- Undirected graphs are symmetrical
		- $\sum$ of row or column is degree of vertex 

$\begin{bmatrix}0 & 1 & 1 \\1 & 0 & 1 \\1 & 1 & 0 \\\end{bmatrix}$

### Incidence Matrix
- Rows are vertices, columns are edges
- $\sum$ of row is degree of vertex, $\sum$ of column is two
	- Loop counts as 2

### Neighborhood
The neighborhood of a vertex $v$ in a graph $G$ is the subgraph of $G$ induced by all vertices adjacent to $v$, i.e., the graph composed of the vertices adjacent to $v$ and all edges connecting vertices adjacent to $v$.

### Paths
- **Circuits**
	A circuit is path that begins and ends at the same vertex.
- **Simple**
	A simple path is a path in a graph which does not have repeating vertices.
- **Length**
	The path length corresponds to the number of edges in the path

### Degree Sequence
The degree sequence of a graph is the sequence of the degrees of the vertices of the graph in non-increasing order. Largest to smallest.
- Theorem: The sum of degree of all vertices of a graph is twice the size of the graph. $\sum deg(v_1)=2|E|$
## Section 3 - Tree Traversal

### Infix, Prefix, and Postfix Notation

### Spanning Trees - Depth-first Search
A spanning tree of a graph $G$ is a subgraph of $G$ that is a tree (no cycles)
containing every vertex of  $G$.

*Hint: Remove circuits to modify graph into spanning tree.*

Instead of removing simple circuits (which can be tiresome and time-consuming for larger graphs) we can create a spanning tree by successively adding edges in an algorithmic fashion.

Depth-first implies we search vertically before horizontally

1. Choose a "root" vertex for a rooted graph
2. Create an edge by connecting the current vertex to an incident vertex.
3. From the new vertex, repeat step 2 until you can no longer connect any vertices.
4. If all vertices have been visited, you have a spanning tree. If not, go to the next-to-last visited vertex to form a new path from the vertex.
5. Continue visiting the next-to-last vertex of the current vertex until all vertices have been visited. 

### Kruskal's Algorithm
Minimum spanning tree
1. Pick the smallest edge
2. Keep picking smallest edges that don't form a circuit until all vertices are connected to same tree.
![](https://i.imgur.com/aL8hc7t.png)

|  edge  | weight |
|:------:|:------:|
| v6-v7  |   1    |
| v3-v4  |   1    |
| v6-v3  |   2    |
| v8-v9  |   2    |
| v9-v10 |   2    |
| v7-v5  |   2    |
| v5-v9  |   3    |
| v4-v9  |   3    |
| v2-v6  |   3    |
| v3-v0  |   3    |
| v0-v1  |   4    |
| v9-v11 | 4       |


### Prim's Algorithm
1. Create "Visited List" to keep track of vertices touched. 
2. Pick vertex to start.
3. Pick the smallest edge that connects to an unvisited (avoid circuits) vertex
4. Add vertex to list.
5. Pick next smallest edge connected to any vertex in list.
6. Repeat until all vertices are visited.






