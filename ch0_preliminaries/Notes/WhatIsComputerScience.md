## Notes:

CS is not a scientific field that makes observations, fits theories to them, proves them, and applies them. Instead, we make models of how interactions should work and fit the world to them. 

Originally, we ran analytical experiments with run time and memory usage to evaluate the efficiency of programs and fit curves to our data to make predictions about the run time or memory usage of programs with a given input size. This, however, was quickly phased out as hardware and OSs diversified and these models became obsolete as their use-cases shrunk. 
Instead we introduced O(n) evaluation of algorithms which is so useful that people willingly ignored that it cannot tell anything about how long it will actually take to run a program in actual units of time. This led to most of CS moving away from exact, quantitative, and empirical evidence and data and towards the realm of logic chains and math. 

This means that, instead of the scientific approach of forming hypotheses out of observations and testing them, we shifted to using the mathematical approach of state assumptions and deriving conclusions from them using logic. However, we do not have a rigorous way to test these assumptions, creating a great risk for anyone who accepts this conclusions. 

Because of this uncertainty, CS does not function like a mathematical field, and people tend to have their own personal "philosophies" about best practices in CS. For this reason, he concludes that CS is actually a branch of philosophy and not a science.

## TLDR:

CS is not a science because it does not make testable theories out of observations but instead makes conclusions out of assumptions and mathematical or logical steps. However, it is not a math either because it cannot prove its assumptions and is subjective and inexact.

## Reflection:

### Why Read This:

We are reading this because it helps us understand the connection between computer science and mathematical proofs, which this article mentions is important to computer science. Additionally, it serves as a general introduction for why this csc class is just about math. Otherwise, no one cares about what the technically correct term for the field is, we will use whatever is the most convenient. 

### Who are these people:

John Hopcroft and Robert Tarjan are computer scientists who invented Big O notation for evaluating the time and memory complexity of an algorithm by focusing on the general trend of the worst case scenario of the algorithm as the input size increases without bound. This is then used to classify the algorithm by the lowest category it falls below. The general types that can be used are: 

O(1) (constant time/memory), O($ln(n)$) (log time/memory), O(n) (linear time/memory), O($n^2$)... O($n^k$) (polynomial time/memory), O($e^n$) (exponential time/memory), or O($n!$) (factorial time/memory).

There are other ways these can be combined, such as merge sort's O($n * log(n)$) time complexity, but these are the main foundations of Big O notation.