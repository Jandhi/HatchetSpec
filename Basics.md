
##### Assignment
`x := 1`

## Types
Types may be specified:
`x : i8 = 1`
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

`struct Person := struct {name : str, age : u32}`

