# Ivan the Fool and the Probability Theory
link: https://codeforces.com/contest/1239/problem/A
1. Note that if we have determined the first row, the second row has only two possibilities, entirely different or entirely same as the first one. However, if there is any *strips*, i.e. two consecutive blocks with same color, on the first row, the second row can only be entirely different as the first one. (can be verified by drawing all possibilities!)

2. We considered the case in which the top left block is black. Thus, the only situatoin without strips in the first row is chess coloring, i.e. black, white, black, white......etc. Then we considered if the next row is the same as the current one, and build the following table.

| row | 1 | 2 | 3 | 4 | 5 | ... | n |
|---------------|---|---|---|---|---|---|---|
| same as last line | 0 | 1 | 1 | 2 | 3 | ... | F(n-2) |
| different as last line | 1 | 1 | 2 | 3 | 5 | ... | F(n-1) |
| total | 1 | 2 | 3 | 5 | 8 | ... | F(n) |

As it shows, the number of possible boards grows as Fibonacci sequence, so if the first line is chess coloring, the total possibilities would be F(n).

3. Now, consider if the first line contains strips. We find that the rule on the colors of a row is the same as the above table, so we know the number of possibilities of the first row is F(m). However, we have to substract the one with chess coloring(already discussed), so the number of possibilities is F(m)-1. From the discussion in 1. , if the row contains strip, the next line is determined, so we have F(m)-1 boards in this section.

4. Finally, the top left block can be white, too. So the answer is 2(F(n)+F(m)-1).
