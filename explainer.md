__Proposal:__

`<-` operator that would allow us to have an observable binding like below:

```js
let a = 40;
let b <- a + 1;
a = 42 // a indirectly updates the value of b
b === 43 // true
```

```js
let a = 40;
let b <- (a > 40 ? a + 1 : a + 2); // it can also accept an expression
a = 42 // a indirectly updates the value of b
b === 43 // true
```

```js
let a = 40;
let b <- () => {a > 40 ? a + 1 : a + 2} // it can also accept a function.
a = 42 // a indirectly updates the value of b
b === 43 // true
```

__Motivations:__

* Have Topological ordering in the language.
* Include true reactivity in the language.
* Abstracting always-in-sync dependent value.

__Other languages that have them:__

`C`

```c
int a = 10;
#define b (a+1)
a = 11;
assert(21 == b);
```

`VHDL`

```
signal a : integer := 40;
signal b : integer;

b <= a + 1;
```

