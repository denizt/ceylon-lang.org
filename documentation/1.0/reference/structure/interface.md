---
layout: reference
title: Interfaces
tab: documentation
unique_id: docspage
author: Tom Bentley
milestone: Milestone 1
---

# #{page.title}

An interface is a stateless type that cannot be 
[instantiated](../../expression/class-instantiation) directly.

## Usage 

A trivial interface declaration looks like this:

    interface I {
        /* declarations of interface members */
    }

Note that because interfaces are stateless they do not have 
initializers and so there's no parameter list after 
the interface name as there is with [class declarations](../class).

## Description

### Satisfying interfaces

An interface can satisfy zero or more other interfaces using the 
`satisfies` keyword. If the class `I` is to satisfy interfaces `I1` and `I2` the 
declaration looks like this:

<!-- cat: interface I1{} interface I2{} -->
    interface I satisfies I1 & I2 {
        /* declarations of interface members */
    }

`&` is used as the separator between satisfied interfaces because `I` is 
satisfying a type, the 
[intersection type](../type#intersection_types) `I1&I2`.

An interface inherits all members (methods, attributes and member types) 
of every supertype.

### Enumerated subtypes

The subtypes of an interface can be constrained to a list of named 
interfaces, classes, or toplevel anonymous classes using the `of` clause. 

If the interface `I` is permitted only two direct 
subtypes `I1` and `C1` its declaration would look like this:

<!-- cat: interface I1 satisfies I {} class C1() satisfies I {} -->
    interface I of I1 | C1 {
        /* declarations of interface members */
    }

### Type parameters

An interface declaration lists [type parameters](../type-parameters) with angle brackets (`<` and `>`) 
after the interface name. 

    interface I<Z> {
        /* declarations of interface members 
           type parameter Z treated as a type */
    }

An interface declaration with type parameters may have a `given` clause for 
each declared type parameter to 
[constraint the permitted type argument](../type-parameters#constraints).

### Shared interfaces

TODO

### Formal interfaces

TODO

### Default interfaces

TODO

### Members

The permitted members of interaces are [classes](../class), 
[interfaces](../interface), 
[methods](../method), 
and [attributes](../attribute).

Note that an interface cannot have an [`object`](../object) member.

### Aliases

An *interface alias* is a kind of [type alias](../type-alias) that 
declares an interface in terms of a type expression:

<!-- cat: interface I2{} -->
    interface I => I2;

## See also

