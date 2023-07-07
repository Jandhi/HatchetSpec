
##### Assignment
`x := 1`

## Functions
Functions are defined using javascript-esque lambdas
`add := (a : i32, b : i32) -> i32 {a + b}`

You can also take no arguments or have no return
`hello := () -> { print 'hello' }`

Or remove brackets for one liners
`hello := () -> print 'hello'`

Implicit returns
```
add_twice := (x : i32) -> {
	x += 1
	x += 1
	x
}
```

## Types
Types may be specified:
`x : i32 = 1`
or interpreted
`x := 1`

### Type Definitions
Types may be defined as unions of types:
`number := u32 | i32`

Or as composite types, using structs:

```
Person := struct {
	name : str
	age : u32
}
```

This should also be doable in one liners:

`Person := struct {name : str, age : u32}`

### Interface Types
Some types describe the behavior of an object rather than structure of an object. For this we use "trait".

```
Person := struct {
	name : str
	age : u32
	get_name : () -> str { self.name }
}

HasName := trait {
	name : str
}

HasGetName := trait {
	get_name : () -> str
}

x = Person{'name', 5}

y : HasName = x 
z : HasGetName = x 
e : HasName = 3 // error!
e : HasGetName = 3 // error!
```

