# Question 5

## Part A

1NF - YES: Assume atomic attributes, no duplicate attribute names, primary key { Book_title, Author_name }.

2NF - NO: Type, Author_affil and Publisher depend on proper subset of primary key and aren't prime.

3NF - NO: Since not in 2NF and also contains transitive dependency (Book_title -> Book_type -> List_price).

Not higher than 1NF since 2NF and above requires 2NF therefore 1NF.

## Part B


This preserves referential intergrity

R<sub>1</sub>(**Book_title**, **Author_name**)

Then these two relations put it in 2NF

R<sub>2</sub>(**Book_title**, Publisher, Book_type, Listprice)


R<sub>3</sub>(**Author_name**, Author_affil)

Then to put it in 3NF, you need to remove the transitive dependency from R<sub>2</sub> and create a new table.


R<sub>2</sub>(**Book_title**, Publisher, Book_type)

R<sub>4</sub>(**Book_type**, Listprice)