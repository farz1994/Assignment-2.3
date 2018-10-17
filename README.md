df1 = data.frame(CustId = c(1:6), Product = c(rep("TV", 3), rep("Radio", 3)))
df2 = data.frame(CustId = c(2, 4, 6), State = c(rep("Texas", 2), rep("NYC", 1)))
df1 #left table
df2 #right table
For the above given data frames and tables perform the following operations:
1. Return only the rows in which the left table have match

df1 = data.frame(CustId = c(1:6), Product = c(rep("TV", 3), rep("Radio", 3)))
df2 = data.frame(CustId = c(2, 4, 6), State = c(rep("Texas", 2), rep("NYC", 1)))
> Left <- merge(df1, df2, by.x = "CustId")
  CustId Product State
1      2      TV Texas
2      4   Radio Texas
3      6   Radio   NYC

2. Return all rows from both tables, join records from the left which have matching keys in the right table.
Right <- merge(df1, df2, by = "CustId", all = TRUE)
> Right
  CustId Product State
1      1      TV  <NA>
2      2      TV Texas
3      3      TV  <NA>
4      4   Radio Texas
5      5   Radio  <NA>
6      6   Radio   NYC
