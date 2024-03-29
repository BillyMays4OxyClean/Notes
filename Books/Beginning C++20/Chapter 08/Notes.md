# Chapter 8 Outline
In this chapter, you will learn:
- What a function is and why you should segment your programs into functions.
- How to declare and define functions.
- How data is passed to a function and how a function can return a value.
- What the difference is between "pass-by-value" and "pass-by-reference" and how to choose between both mechanisms.
- What is the best way to pass strings to a function.
- How to specify default values for function parameters
- What the prefered way is to return a function's output in modern C++.
- How using const as a qualifier for a parameter type affects the operation of a function.
- The effect of defining a variable as static within a function.
- How to create multiple functions that have the same name but different parameters -- a mechanism you'll come to know as function overloading.
- What recursion is and how to apply it to implement elegant algorithms.  

## What a function is and why you should segment your programs into functions.

**Definitions**:  
_function_: a self-contained block of code with a specifc purpose.

Functions are defined with the **function header** shown below. The function header consists of three things:
- A return type
- A name
- A set of input parameters  


```c++
return_type function_name(parameter_list)
```

### How the return statement works
In the code below, the variable `result` is local to the function body. Since `result` goes out of scope once the function returns, `result` no longer exists after the function finishes executing. This begs the question of how the `power` function can return the `result` if it is deleted once the function is done executing? The answer to this is that **a copy of `result` is created a returned**.

```c++
double power(double x, int n)
{
   double result{1.0};
   if (n >= 0)
   {
      result *= x;
   }
   else
   {
      result /= x;
   }
   return result;
}
```