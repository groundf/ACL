headerACL coding example
========================
Implement nPr := [... n r] nPr =>,[... nPr] and
		  nCr := [... n r] nCr => [... nCr]

nPr is the number of permutations of n items taken r at a time.
nCr is the number of combinations of n items taken r at a time.

The formulas are: nPr = n!/(n-r)!
				  nCr = n!/(r!(n-r)! = nPr/r!

Coding in ACL is primarily an exercise in keeping track of the
stack contents. I suggest something like the following method:

for nPr:
[n r] swap => [r n] dup => [r n n] ! => [r n n!]
rotdn => [n! r n] swap => [n! n r] - => [n! n-r]
! => [n! (n-r)!] / => [n!/(n-r)!] the desired result.

The lambda expression for the nPr function is then:
[swap dup ! rotdn swap - ! /]

For nCr:
[n r] dup => [n r r] ! => [n r r!] rotdn => [r! n r]
nPr => [r! nPr] swap => [nPr r!] / => [nPr/r!] again the
desired result.

Thus the lambda expression for nCr is:
[dup ! rotdn nPr swap /]

Test the new functions one step at a time in interactive mode
and make corrections as necessary.

Then create entries in ACLlib.txt as follows:
[swap dup ! rotdn swap - ! /] defun nPr
[dup ! rotdn nPr swap /] defun nCr

User function definitions are limited to a single line of text.
If your defintion becomes too long, factor it into two or more
shorter definitions and glue them together. After all, correct
factoring is one of the benefits of CLs.

Happy coding in ACL!