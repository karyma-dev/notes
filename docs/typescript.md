# Typescript

Typescript is a superset of Javascript that compiles to plain javascript.

```
// Generates a typescript config file
tsc --init
```

## Table of Contents

-   [Basic Types](#basic-types)
-   [Declaration](#declaration)
-   [Interface](#interface)

### Basic Types

```ts
any
void

boolean
string
number

null
undefined

never

// Arrays
number[]
Array<nunber>

// Tuple
[string, number]

// Enum
enum Color {Red = 1, Green, Blue}
let c: Color = Color.Green;

// Union types
string | null | undefined
```

### Declaration

```ts
// Function Declarations

type C = { a: string; b?: number }
function f({ a, b }: C): void {
    // ...
}
```

### Interface

```ts
// Readonly Properties

interface Point {
    readonly x: number
    readonly y: number
}

let p1: Point = { x: 10, y: 20 }
p1.x = 5 // error!
```

```ts
// Readonly Array

let a: number[] = [1, 2, 3, 4]
let ro: ReadonlyArray<number> = a
ro[0] = 12 // error!
ro.push(5) // error!
ro.length = 100 // error!
a = ro // error!
```

```ts
// Function Types

interface SearchFunc {
    (source: string, subString: string): boolean
}

let mySearch: SearchFunc
mySearch = function (source: string, subString: string) {
    let result = source.search(subString)
    return result > -1
}
```

```ts
interface StringArray {
    [index: number]: string
}

let myArray: StringArray
myArray = ['Bob', 'Fred']

let myStr: string = myArray[0]
```

```ts
// Class Types

interface ClockInterface {
    currentTime: Date
    setTime(d: Date): void
}

class Clock implements ClockInterface {
    currentTime: Date = new Date()
    setTime(d: Date) {
        this.currentTime = d
    }
    constructor(h: number, m: number) {}
}
```
