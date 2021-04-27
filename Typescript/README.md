# Typescript

## Type Inferences

Once we initalize a variable with a certain type it may not be reassigned a value of a different data type.

Primitive Data Types

- boolean
- number
- null
- string
- undefined

## Type Annotation / Declaration

`let x : string`

## Default Parameters

`function x(y = 'default')`

## Optional Parameters

`function x(y?: string){}`

## Explicit Return Types

`function x():string {}`

## Any Type

If variable is declared without a value it is considered an any type

## Documentation Comments

```ts
  /**
   * Returns the sum of two numbers.
   *
   * @param x - The first input number
   * @param y - The second input number
   * @returns The sum of `x` and `y`
   *
   */
  function getSum(x: number, y: number): number {
    return x + y;
  }
}
```

## Array Type Annotation

`let x: string[]` or `let x: Array<string>`

## Multi Dimensional Arrays

`let x: string[][] = [['x','y'],['z']]`

## Tuple Type Annotation

`let x: [number, number, string]`

## Spread

`function(...x: string[]){}`

## Enum

Enums allow a developer to define a set of named constants. Using enums can make it easier to document intent, or create a set of distinct cases. TypeScript provides both numeric and string-based enums.

```ts
let petOnSale = 'chinchilla';
let ordersArray = [
  ['rat', 2],
  ['chinchilla', 1],
  ['hamster', 2],
  ['chinchilla', 50],
];

// Write your code below:

enum Pet {
  Hamster,
  Rat,
  Chinchilla,
  Tarantula,
}

let petOnSaleTS: Pet = Pet.Chinchilla;

let ordersArrayTS: [Pet, number][] = [
  [Pet.Rat, 2],
  [Pet.Chinchilla, 1],
  [Pet.Hamster, 2],
  [Pet.Chinchilla, 50],
];
```
