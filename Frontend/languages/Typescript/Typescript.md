[[Typescript|TypeScript]] is a statically typed superset of JavaScript that compiles to plain JavaScript. It was created by Microsoft to address the shortcomings of JavaScript, particularly its lack of strong typing and support for object-oriented programming.

TypeScript adds features like classes, interfaces, and type annotations to JavaScript, making it easier to build and maintain large-scale applications. Because TypeScript is a superset of JavaScript, any valid JavaScript code is also valid TypeScript code, so existing codebases can be gradually migrated to TypeScript.


## Type Inference

![[TS - Type Inference#^1a326c]]


## Type annotation

![[TS - Type annotation#^6fe0e9]]


## Primitive Types in TypeScript

![[TS - Primitive Types in TypeScript#^db339c]]

## Union Types

![[TS - Union Types#^7be988]]

## Literal Types

Fixed values can also be assigned to a parameter or a variable. This is done with the help of so-called literal types. In the example below, the binding number2 may point either to any number or a string with the value "Hello". All other string values would not be allowed for this binding.

```TS
let number2: number | "Hallo" = 12;

number2 = "Hallo"
```

## Arrays

![[TS - Arrays]]

## Enums 

![[TS - Enums#^717422]]

## Type Aliases

![[TS - Type Aliases#^8c3125]]

## Intersection Types

![[TS - Intersection Types#^713950]]

## Interfaces

![[TS - Interfaces#^5c2079]]

## Type Narrowing

![[TS - Type Narrowing#^929d81]]

## Typeof Operator

![[TS - Typeof Operator#^95e514]]

## Keyof Operator

![[TS - Keyof Operator#^902860]]

## Combining `typeof` and `keyof`

When used together, `typeof` and `keyof` can be used to create type-safe code.

For example, suppose you have an object with a known set of keys and values, and you want to create a function that retrieves the value for a given key:

```TS
const myObject = {
  foo: "hello",
  bar: 42,
};

function getValue(key: keyof typeof myObject) {
  return myObject[key];
}
```

Here, `keyof typeof myObject` gets the keys of `myObject` and restricts the `key` parameter to only those keys. This ensures that the `getValue` function can only be called with valid keys of `myObject`.

If you try to call `getValue` with an invalid key, TypeScript will give you a compile-time error:

```TS
getValue("baz"); // Error: Argument of type '"baz"' is not assignable to parameter of type '"foo" | "bar"'
```

Using `typeof` and `keyof` together like this can help catch errors at compile-time, rather than waiting until runtime.

## Utility Types

![[TS - Utility Types#^1a8ec0]]