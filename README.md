# SLR(1)_Short_Note
**SLR(1)**

In the bottom-up parsers there are two main catgories like below,

1) Operator Precedence parsers
2) LR parsers - LR(0) , SLR(1) , LALR(1), CLR(1)

![LR parser](https://github.com/user-attachments/assets/02210858-1aa5-4561-8696-ba5bf90941f8)

![LR parser_2](https://github.com/user-attachments/assets/93ce6c08-c7ef-4fa7-b55c-9c556356c51f)

**Canonical Collection** 

To construct LR(0) and SLR(1) we use canonical collection of LR(0) items.
To construct LALR(1) and CLR(1) tables we use canonical collection of LR(1) items.

![LR parser_3](https://github.com/user-attachments/assets/3d785efc-7109-4661-869c-ccd72e57e11b)

SLR(1) parsing 

In SLR(1) parsing, the key distinction from LR(0) lies in how reductions are handled.

LR(0): Reductions are performed without considering lookaheads. If a state contains a reduce item,
(e.g. A→α∙), it will reduce for all possible input symbols, leading to potential conflicts.

SLR(1): Reductions are allowed only if the next token (lookahead) is in the FOLLOW set of the non-terminal being reduced. 
This restricts reductions to valid contexts, resolving many conflicts that arise in LR(0).

Example:

For a rule A→ε, LR(0) would reduce ε in any state containing this item.

SLR(1) reduces ε only if the lookahead is in  FOLLOW(A), avoiding invalid reductions.

SLR(1) uses FOLLOW sets to "filter" reductions, making it more powerful than LR(0) while retaining simplicity.

Lets, consider small exmaples to understand the SLR(1) more spesifically,

**Example 01 - **

R1 : A  → A c
R2 :    | A a d 
R3 :    | b d 
R4 :    |  ε

where A is non-terminal while all others are terminal and ε means null.


sample answer  -
1) DFA and SLR(1) parsing table

![SLR](https://github.com/user-attachments/assets/8c708a71-1bd9-456e-9f39-0463ad5c714b) 

2) parsing steps for the (Input - Action ) of the input string " bdc " 


![image](https://github.com/user-attachments/assets/18baf0ad-9d55-46df-a130-4a10581db102)

![image](https://github.com/user-attachments/assets/00e1b5a5-15a6-441f-aa4b-1e787f3b80ca)


**Example 2**

Consider the following grammar with the starting terms S. 
S → P 
S → a y 
p → x P y
P → Q 
Q → a 

in the above S,P,Q are non-terminal and others are terminals.

a) illustrating  the set of  SLR(1) items with the corresponding DFA for the given grammar 
b)  Briefly explaining whether this grammar is SLR(1) or not.
c)  The FOLLOW sets for each non-terminal

Sample Answer  -


![SLR_2](https://github.com/user-attachments/assets/959345c5-761b-425f-822e-0bd6f5069d7c)

Thank You . 
