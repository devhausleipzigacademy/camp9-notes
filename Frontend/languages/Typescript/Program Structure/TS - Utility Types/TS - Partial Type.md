
## What is Partial\<Type\>?

The [[TS - Partial Type|Partial Type]] utility type in TypeScript creates a new type that has all the properties of `Type`, but with all properties set as optional. This means that any property of the original type can be either present or undefined in the new type. ^afd816

## How to use Partial\<Type\>

To use `Partial<Type>`, we simply pass the type we want to make partially optional as the generic type parameter. Here's an example:

```TS
interface User {
  id: number;
  name: string;
  email: string;
  phone?: string;
}

type PartialUser = Partial<User>;

// PartialUser is equivalent to:
// {
//   id?: number;
//   name?: string;
//   email?: string;
//   phone?: string;
// }

```