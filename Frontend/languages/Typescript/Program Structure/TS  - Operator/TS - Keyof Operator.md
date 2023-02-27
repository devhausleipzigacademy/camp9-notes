
One of the useful features of TypeScript is the `keyof` operator, which allows us to extract the keys of an object type. ^902860

## Syntax

The `keyof` operator is written as follows:

```TS
type KeysOfType = keyof ObjectType;
```

Here, `ObjectType` is the object type from which we want to extract keys, and `KeysOfType` is the resulting type, which is a union of all keys in `ObjectType`.

## Example

Let's consider an example to understand how `keyof` works. Suppose we have an object type `Person` as follows:

```TS
type Person = {
  name: string;
  age: number;
  address: string;
};
```

We can use the `keyof` operator to extract the keys of `Person` as follows:

```TS
type PersonKeys = keyof Person; // "name" | "age" | "address"
```

In the above example, `PersonKeys` is a union of all the keys in `Person`.