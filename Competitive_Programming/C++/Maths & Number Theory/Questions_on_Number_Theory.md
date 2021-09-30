# :heavy_check_mark: Questions On Number Theory Concepts
## :one: A. Theatre Square  <br>
#### :earth_asia: Source - https://codeforces.com/contest/1/problem/A
   Theatre Square in the capital city of Berland has a rectangular shape with the size n × m meters. On the occasion of the city's anniversary, a decision was taken to pave the Square with square granite flagstones. Each flagstone is of the size a × a.<br>
   
   What is the least number of flagstones needed to pave the Square? It's allowed to cover the surface larger than the Theatre Square, but the Square has to be covered. It's not allowed to break the flagstones. The sides of flagstones should be parallel to the sides of the Square.
   
### Input
The input contains three positive integer numbers in the first line: n,  m and a (1 ≤  n, m, a ≤ 10^9).
         
### Output
Write the needed number of flagstones.

### Examples
    input
    6 6 4
    
    output
    4

## :point_right: Approach to the above problem statement
     1. Read the problem statement carefully have a look over the constraints.
     2. Given a rectangle of size (N x M) and we need to pave it with flagstones of size (A x A).
     3. We can cover the rectangle larger than its surface as given in the problem statement.
     4. First, find the number of squares that can be paved on side 'n' i.e (n/a).
     5. Second, find the number of squares that can be paved on side 'm' i.e (m/a).
     6. Now, if (n/a) is completely divisible then it means that the square (A x A) covered the whole 
        side without taking extra space, similar in case of side 'm'.
     7. If they are not completely divisible it means that we need to cover the rectangle with 1 more
        flagstone, so add 1 to the resultant answer.
        
## :dart: Code in C++      

```cpp
#include <bits/stdc++.h>
using namespace std;

// function to calculate the number of flagstones needed
// long long is taken due to higher constraints as in the problem statement
long long flag(int n, int m, int a)
{
    long long i, j;
    // use of ternary operator
    i = (n % a == 0 ? n / a : n / a + 1); 
    j = (m % a == 0 ? m / a : m / a + 1);
    
    //returns the number of flagstones needed to cover the rectangle
    return i * j;
}

int main()
{
    long long n, m, a, res;
    cin >> n >> m >> a;
    res = flag(n, m, a);
    cout << res;

    return 0;
}

```
     



            
                                               
