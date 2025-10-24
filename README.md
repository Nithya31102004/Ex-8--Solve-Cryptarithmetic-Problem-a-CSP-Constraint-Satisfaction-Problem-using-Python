<h1>ExpNo 8 : Solve Cryptarithmetic Problem,a CSP(Constraint Satisfaction Problem) using Python</h1> 
<h3>Name: NITHYA T       </h3>
<h3>Register Number: 2305001023   </h3>
<H3>AIM:</H3>
<p>
    To solve Cryptarithmetic Problem,a CSP(Constraint Satisfaction Problem) using Python
</p>
<h3>PROCEDURE:</h3>
Input and Output
<br>Input:
This algorithm will take three words.
<br> B A S E<br>
    B A L L<br>
           ----------<br>
           G A M E S<br>

Output:
It will show which letter holds which number from 0 – 9.
For this case it is like this.

              B A S E                         2 4 6 1
              B A L L                         2 4 5 5
             ---------                       ---------
            G A M E S                       0 4 9 1 6
Algorithm
For this problem, we will define a node, which contains a letter and its corresponding values.<br>

isValid(nodeList, count, word1, word2, word3)<br>

Input − A list of nodes, the number of elements in the node list and three words.<br>

Output − True if the sum of the value for word1 and word2 is same as word3 value.<br>

Begin<br>
   m := 1<br>
   for each letter i from right to left of word1, do<br>
      ch := word1[i]<br>
      for all elements j in the nodeList, do<br>
         if nodeList[j].letter = ch, then<br>
            break<br>
      done<br>
      val1 := val1 + (m * nodeList[j].value)<br>
      m := m * 10<br>
   done<br>

   m := 1<br>
   for each letter i from right to left of word2, do<br>
      ch := word2[i]<br>
      for all elements j in the nodeList, do<br>
         if nodeList[j].letter = ch, then<br>
            break<br>
      done<br>

      val2 := val2 + (m * nodeList[j].value)
      m := m * 10
   done<br>

   m := 1<br>
   for each letter i from right to left of word3, do<br>
      ch := word3[i]<br>
      for all elements j in the nodeList, do<br>
         if nodeList[j].letter = ch, then<br>
            break<br>
      done<br>

      val3 := val3 + (m * nodeList[j].value)
      m := m * 10
   done<br>

   if val3 = (val1 + val2), then<br>
      return true<br>
   return false<br>
End<br>

<hr>
<h2>Sample Input and Output:</h2>
SEND = 9567<br>
MORE = 1085<br>
<hr>
MONEY = 10652<br>

## PROGRAM
```Python
from itertools import permutations

def solve_cryptarithmetic():
    letters = ('T', 'H', 'I', 'S', 'A', 'R', 'D')
    for perm in permutations(range(10), len(letters)):
        T, H, I, S, A, R, D = perm

        # Leading letters cannot be zero
        if T == 0 or H == 0:
            continue

        THIS = 1000 * T + 100 * H + 10 * I + S
        IS = 10 * I + S
        HARD = 1000 * H + 100 * A + 10 * R + D

        if THIS + IS == HARD:
            return THIS, IS, HARD, {'T':T, 'H':H, 'I':I, 'S':S, 'A':A, 'R':R, 'D':D}

    return None

solution = solve_cryptarithmetic()

if solution:
    THIS, IS, HARD, mapping = solution
    print("Mapping:", mapping)
    print(f"THIS = {THIS}")
    print(f"IS   = {IS}")
    print(f"HARD = {HARD}")
else:
    print("No solution found.")


```

## OUTPUT

<img width="641" height="103" alt="image" src="https://github.com/user-attachments/assets/e84c72e4-67c7-494a-a591-c568ae7780cc" />


<hr>
<h2>Result:</h2>
<p> Thus a Cryptarithmetic Problem was solved using Python successfully.</p>
