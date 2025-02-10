# Discrete Math

## Examples:

### Ex 1:

We will set this up by starting with one person and having them shake hands with everyone they have not already done so with. The first person will have $n-1$ people to shake hands with as they will not shake hands with themselves. The next person will then add $n-2$ more unique handshakes as they will not shake hands with themselves or the first person (because they had already shaken hands). This pattern will continue with each person having to introduce one less new hand shake as they will have already shaken hands with one more person. This gives us a series $a$ which counts down from $n-1$ to one, and a sum $s$ where,\
$s = sum(a) = \displaystyle\sum_{k=n-1}^{1} (k) = \begin{bmatrix}n-1+n-2+n-3+\ldots&+3+2+1\end{bmatrix}$.

This is a common type of sum with a formula that has been proven to be equal $\frac{k(k+1)}{2}$ with k being the length of the sequence as well as the highest valued term in the sequence. Plugging in $n-1$ t this formula gives: $s = \frac{n(n-1)}{2}$. However, I would like to show why this formula is correct so I will keep going with the explanation. In order to make this easier to work with we will first multiply both sides by two:\
$2s = \begin{bmatrix}n-1+n-2+n-3+\ldots&+3+2+1\end{bmatrix} + \begin{bmatrix}n-1+n-2+n-3+\ldots&+3+2+1\end{bmatrix}$,\
and reverse the order of the second copy of the series:\
$2s = \begin{bmatrix}n-1+n-2+n-3+\ldots&+3+2+1\end{bmatrix} + \begin{bmatrix}1+2+3+\ldots&+n-3+n-2+n-1\end{bmatrix}$.

We can then distribute these two series so the $k$ th term of the decreasing series is added to the $k$ th term of the increasing series:\
$2s = \begin{bmatrix}([n-1]+[1])+([n-2]+[2])+([n-3]+[3])+\ldots&+([3]+[n-3])+([2]+[n-2])+([1]+[n-1])\end{bmatrix}$,\
and combine like terms to simplify into:\
$2s = \begin{bmatrix}(n)+(n)+(n)+\ldots&+(n)+(n)+(n)\end{bmatrix}$.

This is a much cleaner sum as we have a sequence that is $n-1$ terms long where each term is equal to $n$. This is just simple multiplication giving us that $2s = (n-1)(n)$. Dividing both sides by $2$ gives us the final answer of $s = \frac{n(n-1)}{2}$, where s is the total number of handshakes that occur at the party with each party goer shaking hands with everyone (except themselves) exactly once.

### Ex 2:
This pattern can be easily represented by a sequence $a$, where $a_{n} = 2n-1$, and $n = 1$ represents the first contestant and each subsequent $n+1$ represents the next contestant to eat. $a_{26}$ (assuming the index starts at $1$ and not $0$) is then equal to $2(26)-1 = 52-1 = 51$.

We will denote the sum of this series as $s$ or $s_{n}$ when referring to the cumulative sum of the total number of hotdogs eaten up to and including a specific contestants contribution. This gives us $s_{26} = \begin{bmatrix}(1+3+5+7+9+11+\ldots&+51)\end{bmatrix}$. We can use the same trick as the first example to rearrange this as $2s_{26} = \begin{bmatrix}(54+54+54+54+54+54+\ldots&+54)\end{bmatrix} = 54 * 26$. This gives us our final answer of $s_{26} = 702$ hotdogs eaten in total.

### Ex 3:
We will represent this problem with a truth table of all possible combinations of each chest lying or telling the truth with $0$ representing lying and $1$ representing telling the truth. This gives us $t = \begin{bmatrix}1&1\cr0&1\cr1&0\cr0&0\end{bmatrix}$. We can then evaluate each of these scenarios for either having a contradiction, which would tell us that the scenario is impossible, or having a set list of possible outcomes. 

The first scenario, $\left<true, true\right>$, is impossible as the first (left) chest guarantees exactly one chest has treasure while the other chest guarantees that both chests have treasure because they are both true. This is a contradiction disproving this scenario.

The second scenario, $\left<false, true\right>$, guarantees the the second (right) chest has treasure because it is telling the truth and the second chest is true so truthful chests have treasure. Additionally, the first chest also has treasure because the first chest being false guarantees they either both chests have treasure or neither chest has treasure and we know that it is not neither. 

The third scenario, $\left<true, false\right>$, guarantees that the second chest alone has treasure. We know this because we know exactly one chest has treasure, but chests that are true do not have treasure (else it would be true and true). This means that the first chest cannot have treasure, but the total number of treasure chests most equal one so the second chest must have treasure.

What makes this difficult is the last scenario where both are lying, $\left<false, false\right>$, as we cannot prove the outcome of this scenario. We know because the first chest is false that either both chests have treasure or neither chest has treasure, but we cannot prove one or the other is the outcome of the scenario. This is the only way where the second chest does not have treasure, however. This means that <B><font color="Yellow">if you can prove that at least one chest is truthful through other means, then you can safely open the second chest.</B></font> We could simply assume this is true, or we could likely confirm the first chest is truthful by comparing the chests using scales or more advanced methods.

### Ex 4:
The goal is to place five points on a flat, euclidean plane with exactly one line connecting each pair of points and with no intersections in our lines. I will assume in my explanation that the points are placed so that any set of three points are not collinear and any line connecting to points is straight unless it cannot be. However, it is fairly easy to show that violating these assumptions do not make the problem easier as placing three points along the same line simply reduces your options for connecting the first and last points, and using bent lines just means that your shape takes up a larger footprint.

We will start off with three points placed and will attempt to add more till we get to five or cannot continue to add connections. We lose if we place a point (that is not the last point) within a closed shape. This is because adding in the new point will subdivide the shape into multiple regions where there will be one (in the case of a subdivided triangle) or more points along the edge of the original shape that cannot be connected into any given subregion so none of the subregions could host another point. Additionally, the next point could not be placed out side of the shape because then it could not be connect to the internal point.

To explain this better, say that you start off by placing a point in the middle of a triangle. This will create three smaller sub-triangles each connected to this new center point. The next point (the fifth point) could then only be placed within one of these three subregions or outside of the shape. If placed outside it would fail to connect to the internal center point that was just placed. If placed in any given subregion, it would be able to easily connect to the center point and the two points along the nearest edge of the original triangle. However, the last vertex of the original triangle (the one opposite to the edge that the fifth point is closest to) is now unable to reach our fifth point as it is completely surrounded by closed shapes. This problem holds for any other arrangement of four or more points forming a closed shape.

The real problem is that this holds for all arrangements of four points.

To see this we will start with three points on a plane and keep our lose condition in mind. These will always form a closed shape (a triangle if they are not colinear). The fourth point then cannot be placed inside this shape for the above logic. Additionally, if the fourth point is placed outside of the shape, then it creates a new closed shape with the two furthest points*. This means that we now have a larger closed shape with the new point and the two furthest from it, and the point that was closest to our new point is now inside of said closed shape. *(Alternatively, if the fourth point is placed equidistant from two points a connection to the third point will have to bend around one of the two points causing it to be locked inside of a closed shape). Because of this, we cannot possible win and will lose with any combination of four points. Therefore, we cannot place five interconnected points on a plane without intersection.

## Comprehension:

### What is Discrete Math?

Discrete math is a mathematical field that deals exclusively with non-continuous sets of possible input or outputs values. They involve logic or math problems where any given parameter to the problem has a countable number of possible states, such as ($true$ or $false$), or ($1$, $2$, $3$, or $4$) (even if the number of states is infinite, if it is discrete there is a system that if run infinitely long will eventually cover every number). For example, there is not a program that could count every number between $0$ and $1$ in order as there will always be ones skipped over; however, a program could easily count all of the natural numbers if run forever. 

### What are the Main Subcategories of Discrete Math?

The four main subcategories that we will focus on in this class are combinatorics (the study of the number of different pairs, orderings, subsets, or combinations of a set of things), sequences (ordered lists of numbers that can be expressed by a common rule), symbolic logic (combinations of logical statements and rules which can be used to solve complex problems), and graph theory (black magic from the before ages that expresses problems as sets of nodes and lines on a graph).

### Questions

I would like to know if there is a solution to example three that does not use any other information, such as assuming at least one is truthful, as that is the only problem I could not solve.

# Discrete Structures

## Example

For the first value that is placed on the top, $0$, there are $n+1$ ($0$ through $n$ inclusive) possible numbers to pair it with on the bottom of the domino. For each next number placed on the top, the number of possible pairs decreases by one because they will have already been paired with each number less then them. This gives us a series of numbers that counts down from $n+1$ to $1$. This then tells us that the number of combinations is the sum of the series that counts down from $n+1$ to $1$, which in turn means we can use the formula we proved in example number one. Substituting in $n+1$ as our upper limit gives us that $s_{n} = \frac{(n+1)(n+2)}{2}$ where n is the highest number on the domino. We can then use this formula to find that a six sided domino, $s_{6}$, has $\frac{(6+1)(6+2)}{2} = \frac{(7)(8)}{2} = 7*4$ = 28 possible combinations, and a nine sided domino $s_{9} = \frac{(10)(11)}{2} = 5 * 11 = 55$ possible combinations. 

## Discrete Structure Examples
#### Sets:
An unordered collection of numbers that does not contain duplicate elements. (This would make it a multi-set).
#### Functions:
A formula that takes in a tuple of inputs and outputs a value or set. These can be explicit formulas, such as $2x^2 + 1$, or recursive formulas, such as $f(n) = f(n-1) + f(n-2)$, which require an initial position $+C$ to find the specific solution for the general formula.
#### Sequences:
Ordered lists of numbers that can contain duplicates, which are usually used as the discrete representation of continuos functions and integrals (sums of a sequence from $a$ to $n$).
#### Relations:
Rules that define relative properties between two or more items, such as $a<b<c$.
#### Graphs:
A set of points and connections on a plane that visually represent symmetric (if point $a$ is connected to point $b$, then point $b$ is connected to point $a$), non-reflexive (any given point $a$ is not connected to itself) relations. These can also be used in a more topographical way such as the previous example which looks for intersections of these connections.

## Comprehension

### Reflection 
The original problem at the top of the section was to find the count of a set of multi-sets. The collection of each domino was a set as dominos did not repeat or have order. Each domino, however, was a multi-set as they were unordered but contained duplicates.

### Questions
Why do we distinguish between functions and sequences in this class? I thought that a discrete function was just a sequence and vice versa.