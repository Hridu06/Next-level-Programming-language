# Type Alias vs Interface in TypeScript

## Introduction

When working with TypeScript, both `type` and `interface` help us
describe the structure of data. At first, they may look almost the same,
but there are some important differences. Understanding these
differences makes it easier to choose the right one while developing a
project.

## Understanding the Difference

An interface is mainly used to describe the shape of an object. For
example:

``` typescript
interface User {
  name: string;
  age: number;
}
```

We can create a user object that follows this structure. One useful
feature of interfaces is that they can be extended using `extends`.

``` typescript
interface Employee extends User {
  salary: number;
}
```

A type alias can describe objects too:

``` typescript
type Product = {
  name: string;
  price: number;
};
```

However, type aliases are more flexible. They can represent unions,
primitives, tuples, and other types.

``` typescript
type Status = "pending" | "completed" | "failed";
```

Another difference is that interfaces can be declared multiple times
with the same name, and TypeScript combines their properties. This is
called declaration merging. Type aliases do not support this behavior.

## Conclusion

In my opinion, interfaces are a good choice when defining object
structures, especially in OOP-based projects. Type aliases are useful
when working with unions, complex types, or when creating reusable type
definitions. Both are valuable, and choosing between them depends on the
situation.
