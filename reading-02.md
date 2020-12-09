# Reading 02 

## Test WE Trust (TDD)
- Unit tests are some pieces of code to exercise the input, the output and the behaviour of your code. You can write them anytime you want.
- The greatest advantage about TDD is to craft the software design first
- Your code will be more reliable after a change you can run your tests and be in peace
- Beginning may be hard — and that’s fine. You just need to practice
- The cycle
  - Write a unit test and make it fail
  - Write the feature and make it pass
  - Refactor code

## Recursion
- The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called as recursive function.
```
 approach(1) – Simply adding one by one

f(n) = 1 + 2 + 3 +……..+ n
approach(2) – Recursive adding 

f(n) = 1                  n=1

f(n) = n + f(n-1)    n>1
```
- Base case 
```
  int fact(int n)
{
    if (n < = 1) // base case
        return 1;
    else    
        return n*fact(n-1);    
}
  
```
- Direct recursion
```

  // An example of direct recursion
void directRecFun()
{
    // Some code....

    directRecFun();

    // Some code...
}
``` 
- Indirect recursion
```
// An example of indirect recursion
void indirectRecFun1()
{
    // Some code...

    indirectRecFun2();

    // Some code...
}
void indirectRecFun2()
{
    // Some code...

    indirectRecFun1();

    // Some code...
}
```