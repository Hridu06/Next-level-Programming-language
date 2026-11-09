# How Generics Work in TypeScript and Their Role in Promises

## Introduction

Generics are one of the useful features of TypeScript because they allow
us to write reusable code without losing type safety. Instead of writing
separate functions for different data types, we can create one function
that works with multiple types.

## Understanding Generics

A generic type is represented by a type parameter, commonly written as
`<T>`. TypeScript determines what `T` represents when the function is
called.

``` typescript
function getValue<T>(value: T): T {
  return value;
}

getValue<number>(10);
getValue<string>("Hello");
```

The same function can handle numbers and strings while keeping the
correct return type. This makes code easier to maintain and reduces
unnecessary duplication.

Generics are also useful when working with asynchronous operations. A
Promise represents a value that may become available later. We can use
`Promise<T>` to describe the type of value it will eventually return.

``` typescript
async function getUserName(): Promise<string> {
  return "Rakib";
}
```

Here, `Promise<string>` means that the function returns a Promise that
resolves to a string. We can also create reusable functions that return
different Promise types.

``` typescript
function createResponse<T>(data: T): Promise<T> {
  return Promise.resolve(data);
}
```

This function can return a Promise containing a string, number, or
object while preserving its original type.

## Conclusion

Generics make TypeScript code more flexible and reusable without
sacrificing type safety. When combined with Promises, they help
developers clearly define asynchronous results and build reliable APIs
and services.
