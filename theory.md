# Programming Assignment 5

## Question 1:

**Static Scoping:** means a variable is resolved by looking at the structure of the source code. If a variable isn't found in the local block, the intepreter checks the enclosing block where the function was written and then checks layer by layer until it gets to the global scope

**Dynamic Scoping:** Ignores where the function was written. It instead looks at the call stack at runtime. It checks the function that is currently running, then the function that called it, and so on backward through the execution history

### Which one is Python and Bash?

| Python is static and bash is dynamic. In a scenario where we have a massive codebase with a lot of files. A colleague writes a function 'calculate_total()' that uses a free variable tax_rate. We need to know exactly which tax_rate is being applied. We can figure that out by looking at the text on our screen. Wheras with dynamic scoping we have to trace where everything was originally referenced

## Question 2:

```
global x = 10

proc A():
    local x = 1
    call B()

proc B():
    print(x)
```

### Static Scoping:

Since B is written at the global level and we have a global x value, calling the function B() on its own will instead call the global x value instead of the local x value in function A()

### Dynamic Scoping:

This one should print out 1 for x since A is the function that called B()

## Question 3

```
global y = 50

proc print_y(y){
    // the 'global y' (50) is in a scope hole here

    // It's impossible to access because the parameter 'y' shadows it
    print(y)
}
```

## Question 4

If we have a concurrent or multi-threaded program where multiple threads are executing code at the same time they would overlap. This would create a race condition and this shared piece of state at risk is the call stack itself. If we have on thread going through the code and then another one. B would pop a frame off that exact same stack because a function finished executing. Thread A's lookup will pull corrupted date or crash the intepreter entirely