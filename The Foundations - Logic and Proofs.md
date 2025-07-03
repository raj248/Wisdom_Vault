## Propositional Logic
The rules of logic give precise meaning to mathematical statements.
used to distinguish between valid and invalid arguments. 
### Propositions

[[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=25&selection=9,0,14,28&color=note|A proposition is a declarative sentence (that is, a sentence that declares a fact) that is either true or false, but not both.]]
Declarative sentences are propositions i.e. 1+1=2, India's Capital is Delhi, etc.
Not propositions? what time is it?, x+1=2, etc.

use letters to denote propositional variables (or sentential variables) are p, q, r, s, . . .
Truth value of proposition, T (if true), F (if false)

Propositions that cannot be expressed in terms of simpler propositions are called atomic propositions. 
The area of logic that deals with propositions is called the propositional calculus or propositional logic.

New propositions, called compound propositions, are formed from existing propositions using logical operators.

![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=26&rect=122,493,625,597&color=red]]

![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=27&rect=108,565,591,627&color=red]]
[[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=27&selection=240,0,242,12|The Truth Table for the Conjunction of Two Propositions]]
Note that in logic the word “but” sometimes is used instead of “and” in a conjunction. For example, the statement “The sun is shining, but it is raining” is another way of saying “The sun is shining and it is raining.”

![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=27&rect=105,248,589,317&color=red]]
[[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=27&selection=276,1,279,13|The Truth Table for the Disjunction of Two Propositions.]]
The use of the connective or in a disjunction corresponds to one of the two ways the word or is used in English, namely, as an inclusive or. A disjunction is true when at least one of the two propositions is true. That is, p ∨ q is true when both p and q are true or when exactly one of p and q is true.

Besides its use in disjunctions, the connective or is also used to express an exclusive or. Unlike the disjunction of two propositions p and q, the exclusive or of these two propositions is true when exactly one of p and q is true; it is false when both p and q are true (and when both are false)

![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=28&rect=131,274,610,330&color=red]]
[[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=29&selection=243,0,245,12&color=red|The Truth Table for the Exclusive Or of Two Propositions]]

---
### Conditional Statements

![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=29&rect=107,314,588,406&color=red]]
[[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=29&selection=280,0,288,1&color=red|The Truth Table for the Conditional Statement p → q.]]
The statement p → q is called a conditional statement because p → q asserts that q is true on the condition that p holds. A conditional statement is also called an implication.

Ways to express this conditional statement: “if p, then q” “p implies q” “if p, q” “p only if q” “p is sufficient for q” “a sufficient condition for q is p” “q if p” “q whenever p” “q when p” “q is necessary for p” “a necessary condition for p is q” “q follows from p” “q unless ¬p” “q provided that p”

note that “p only if q” says that p cannot be true when q is not true. That is, the statement is false if p is true, but q is false. When p is false, q may be either true or false, because the statement says nothing about the truth value of q.

To remember that “q unless ¬p” expresses the same conditional statement as “if p, then q,” note that “q unless ¬p” means that if ¬p is false, then q must be true. That is, the state- ment “q unless ¬p” is false when p is true but q is false, but it is true otherwise. Consequently, “q unless ¬p” and p → q always have the same truth value.

In mathematical reasoning, conditional statements are defined independently of cause-and-effect relationships and are specified by their truth values, not English usage. Propositional language, an artificial language, parallels English for ease of use but differs from programming languages' if-then statements, where p is a proposition and S is executable instructions. In programming, S is executed if p is true and skipped if p is false.

[[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=32&selection=105,0,105,37&color=red|CONVERSE, CONTRAPOSITIVE, AND INVERSE]]

From the conditional statement p→q, we can derive three related statements: 
the converse q→p, 
the contrapositive ¬q→¬p, and 
the inverse ¬p→¬q. 
Only the contrapositive always has the same truth value as the original statement. The converse and inverse do not always share the same truth value with the original statement, but they are equivalent to each other. A common logical error is assuming the converse or inverse is equivalent to the original conditional statement.

Converse + Inverse = Contrapositive

BICONDITIONALS

![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=33&rect=107,498,595,566&color=red]] [[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=33&selection=6,0,13,0&color=red|The Truth Table for the Biconditional p ↔ q]]

There are some other common ways to express p ↔ q: “p is necessary and sufficient for q” “if p then q, and conversely” “p iff q.” “p exactly when q.” The last way of expressing the biconditional statement p ↔ q uses the abbreviation “iff” for “if and only if.” Note that p ↔ q has exactly the same truth value as (p → q) ∧ (q → p).

[[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=33&selection=259,0,287,1&color=red|IMPLICIT USE OF BICONDITIONALS : You should be aware that biconditionals are not always explicit in natural language. In particular, the “if and only if” construction used in biconditionals is rarely used in common language. Instead, biconditionals are often expressed using an “if, then” or an “only if” construction. The other part of the “if and only if” is implicit. That is, the converse is implied, but not stated. For example, consider the statement in English “If you finish your meal, then you can have dessert.” What is really meant is “You can have dessert if and only if you finish your meal.” This last statement is logically equivalent to the two statements “If you finish your meal, then you can have dessert” and “You can have dessert only if you finish your meal.” Because of this imprecision in natural language, we need to make an assumption whether a conditional statement in natural language implicitly includes its converse. Because precision is essential in mathematics and in logic, we will always distinguish between the conditional statement p → q and the biconditional statement p ↔ q.]]

### Truth Tables of Compound Propositions
[[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=34&selection=20,0,37,1&color=red|Construct the truth table of the compound proposition (p ∨ ¬q) → (p ∧ q).]]

### Precedence of Logical Operators
 [[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=34&selection=351,0,352,17&color=red|Table]]
Operator Precedence 
¬ 1 
∧ 2 
∨ 3 
→ 4 
↔ 5

### Logic and Bit Operations
![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=35&rect=101,327,590,406&color=red]]

---
## Applications of Propositional Logic

How can this English sentence be translated into a logical expression? 
“You can access the Internet from campus only if you are a computer science major or you are not a freshman.”?

let a, c, and f represent “You can access the Internet from campus,” “You are a computer science major,” and “You are a freshman,” respectively. Noting that “only if” is one way a conditional statement can be expressed, this sentence can be represented as
a → (c ∨ ¬f )

“You cannot ride the roller coaster if you are under 4 feet tall unless you are older than 16 years old.”

Let q, r, and s represent “You can ride the roller coaster,” “You are under 4 feet tall,” and “You are older than 16 years old,” respectively. Then the sentence can be translated to (r ∧ ¬s) → ¬q.

### System Specifications
![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=41&rect=104,75,536,151&color=red]]

Solution: 
Let p denote “The diagnostic message is stored in the buffer” and let q denote “The diagnostic message is retransmitted.” The specifications can then be written as p ∨ q, ¬p, and p → q. An assignment of truth values that makes all three specifications true must have p false to make ¬p true. Because we want p ∨ q to be true but p must be false, q must be true. Because p → q is true when p is false and q is true, we conclude that these specifications are consistent, because they are all true when p is false and q is true.

## Propositional Equivalences

![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=49&rect=108,173,592,258&color=red]]
[[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=50&selection=6,0,7,20&color=red|Examples of a Tautology and a Contradiction.]]

### Logical Equivalences
Compound propositions that have the same truth values in all possible cases are called logically equivalent. i.e.
![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=50&rect=126,511,609,574&color=red]]
Remark: The symbol ≡ is not a logical connective, and p ≡ q is not a compound proposition but rather is the statement that p ↔ q is a tautology. The symbol ⇔ is sometimes used instead of ≡ to denote logical equivalence.

De Morgan’s Laws. 
1. ¬(p ∧ q) ≡ ¬p ∨ ¬q 
2. ¬(p ∨ q) ≡ ¬p ∧ ¬q

![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=51&rect=108,507,591,713&color=red]]

![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=52&rect=50,375,640,747&color=red]]
![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=52&rect=71,72,648,287&color=red]]
A truth table with $2^n$ rows is needed to prove the equivalence of two compound propositions in n variables.
Because $2^n$ grows extremely rapidly as n increases, the use of truth tables to establish equivalences becomes impractical as the number of variables grows. It is quicker to employ logical equivalences that we already know.
![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=53&rect=178,481,595,662&color=red]]

### Using De Morgan’s Laws
### Constructing New Logical Equivalences
if p and q are logically equivalent and q and r are logically equivalent, then p and r are logically equivalent
A proposition in a compound proposition can be replaced by a compound proposition that is logically equivalent to it without changing the truth value of the original compound proposition 
![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=54&rect=127,454,616,623&color=red]]
![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=54&rect=129,330,613,426&color=red]]
![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=55&rect=101,428,585,749&color=red]]

### Satisfiability
A compound proposition is satisfiable if there is an assignment of truth values to its variables that makes it true (that is, when it is a tautology or a contingency).

When no such assignments exists, that is, when the compound proposition is false for all assignments of truth values to its variables, the compound proposition is unsatisfiable

When we find a particular assignment of truth values that makes a compound proposition true, such an assignment is called a solution.

Application of Satisfiability
- n-Queens Problem
- Sudoku

## Predicate and Quantifiers
(predicate logic)

### Predicate
The statement “x is greater than 3” has two parts. The first part, the variable x, is the subject of the statement. The second part—the **predicate**, “is greater than 3”—refers to a property that the subject of the statement can have.

denote the statement “x is greater than 3” by P (x), where P denotes the predicate “is greater than 3” and x is the variable.

The statement P (x) is also said to be the value of the propositional function P at x.  
**Once a value has been assigned to the variable x, the statement P (x) becomes a proposition and has a truth value.**

![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=65&rect=108,483,591,647&color=red]]

Preconditions and Post-conditions : The statements that describe valid input are known as preconditions and the conditions that the output should satisfy when the program has run are known as post-conditions.

### Quantifiers
When the variables in a propositional function are assigned values, the resulting statement becomes a proposition with a certain truth value. i.e quantification, to create a proposition form a propositional function.

Quantification expresses the extent to which a predicate is true over a range of elements.

In English, the words all, some, many, none, and few are used in quantification.

The area of logic that deals with predicates and quantifiers is called the predicate calculus.

Universal Quantifier

![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=67&rect=108,506,594,631&color=red]]
The meaning of the universal quantification of P (x) changes when we change the domain. The domain must always be specified when a universal quantifier is used; without it, the universal quantification of a statement is not defined.

**Remark**: Generally, an implicit assumption is made that all domains of discourse for quantifiers are nonempty. Note that if the domain is empty, then ∀xP (x) is true for any propositional function P (x) because there are no elements x in the domain for which P (x) is false.

A statement ∀xP (x) is false, where P (x) is a propositional function, if and only if P (x) is not always true when x is in the domain. One way to show that P (x) is not always true when x is in the domain is to find a counterexample to the statement ∀xP (x). Note that a single counterexample is all we need to establish that ∀xP (x) is false.
![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=67&rect=127,72,622,183&color=red]]
[[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=68&selection=0,0,1,0&color=red|1.4 Predicates and Quantifiers Examples]]

Golden Example ![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=68&rect=120,260,611,385&color=red]]
Existential Quantifier

![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=68&rect=127,70,616,245&color=red]]

A domain must always be specified when a statement ∃xP (x) is used. Furthermore, the meaning of ∃xP (x) changes when the domain changes. Without specifying the domain, the statement ∃xP (x) has no meaning.

Besides the phrase “there exists,” we can also express existential quantification in many other ways, such as by using the words “for some,” “for at least one,” or “there is.” The existential quantification ∃xP (x) is read as “There is an x such that P (x),” “There is at least one x such that P (x),” or “For some xP (x).”

Remark: Generally, an implicit assumption is made that all domains of discourse for quantifiers are nonempty. If the domain is empty, then ∃xQ (x) is false whenever Q (x) is a propositional function because when the domain is empty, there can be no element x in the domain for which Q (x) is true.

### THE UNIQUENESS QUANTIFIER 

### QUANTIFIERS OVER FINITE DOMAINS

![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=70&rect=202,598,610,741&color=red]]
![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=70&rect=200,357,612,453&color=red]]

### Quantifiers with Restricted Domains
![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=71&rect=101,500,592,657&color=red]]

### Precedence of Quantifiers 
The quantifiers ∀ and ∃ have higher precedence than all logical operators from propositional calculus. For example, ∀xP (x) ∨ Q (x) is the disjunction of ∀xP (x) and Q (x). In other words, it means (∀xP (x)) ∨ Q (x) rather than ∀x (P (x) ∨ Q (x)).

### Binding Variables
- When a quantifier is used on the variable x, we say that this occurrence of the variable is bound. 
- An occurrence of a variable that is not bound by a quantifier or set equal to a particular value is said to be free. 
- All the variables that occur in a propositional function must be bound or set equal to a particular value to turn it into a proposition. 
- This can be done using a combination of universal quantifiers, existential quantifiers, and value assignments.
- The part of a logical expression to which a quantifier is applied is called the scope of this quantifier
-  a variable is free if it is outside the scope of all quantifiers in the formula that specify this variable.

![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=71&rect=103,172,596,215&color=red]]
[[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=71&color=red|The reader should be aware that in common usage, the same letter is often used to represent variables bound by different quantifiers with scopes that do not overlap.]]

### Logical Equivalence with Quantifiers
![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=72&rect=128,537,617,627&color=red]]
[[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=72&selection=46,0,47,0&color=red|EXAMPLE 19]]

### Negating Quantified Expressions
[[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=73&selection=50,0,62,25&color=red|To show that ¬∀xP(x) and ∃x¬P(x) are logically equivalent]]

![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=73&rect=162,74,610,167&color=red]] ![[Discrete mathematics and its applications Rosen, Kenneth H - (2019).pdf#page=74&rect=170,586,610,750&color=red]]

## Nested Quantifiers
