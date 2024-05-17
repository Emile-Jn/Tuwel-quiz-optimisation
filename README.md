# TUWEL quiz optimisation
This R markdown file aims to evaluate the way guessing answers affects the total score in a TUWEL quiz.
### Assumptions:
 - each statement (not counting the "none of the above" box as a statement) has a 50% chance of being true
and a 50% chance of being false, independently of any other statement. This assumption might be only approximative
if the total number of true and false statements in a quiz is intentionally made to be roughly equal.
 - the score for a batch can't be negative, so negative scores are changed to 0.
 - the order of statements in a batch is random.
 - with NOTA box format: each batch of questions has four statements, and five boxes, where four boxes correspond to the statements
   and the last box is "none of the above".
 - without NOTA box format: each batch of questions has four statements, and four boxes, where each box corresponds to a statement.

### Results:
#### With a None Of The Above box:
- if you know that one statement is true, and you don't know about the 3 others, you will
get the highest score expectancy by guessing 1 or 2 remaining statements to be true.  
- if you know that at least 2 statements are true, you will get the highest score
expectancy by guessing all remaining statements to be false.  
- in all other cases, you will get the highest score expectancy by guessing all remaining
statements to be true. 

#### Without a None Of The Above box:
- in general, try to balance out the true and false answers among the four statements. 
See table below for detailed strategy. 

### Cheat sheet:
#### With a None Of The Above box:
| What you already answered | Best guess |
| --- | --- |
| 0T,0F | TTTT |
| 0T,1F | TTT |
| 0T,2F | TT |
| 0T,3F | T or F |
| 1T,0F | TTF or TFF |
| 1T,1F | TT |
| 1T,2F | T |
| 2T,0F | FF |
| 2T,1F | T or F |
| 3T,0F | F |

#### Without a None Of The Above box:
| What you already answered | Best guess |
| --- |-------|
| 0T,0F | TTTF  |
| 0T,1F | TTT   |
| 0T,2F | TT    |
| 0T,3F | T     |
| 1T,0F | FFF   |
| 1T,1F | any   |
| 1T,2F | T     |
| 2T,0F | FF    |
| 2T,1F | F     |
| 3T,0F | F     |