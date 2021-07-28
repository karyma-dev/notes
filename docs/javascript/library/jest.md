# Jest

## Table Of Content

-   [Matchers](#matchers)
-   [Setup and Teardown](#setup-and-teardown)

## Matchers

**toBe** is used to test exact equalities

```js
test('two plus two is four', () => {
    expect(2 + 2).toBe(4)
})
```

**not.toBe**

```js
test('adding positive numbers is not zero', () => {
    for (let a = 1; a < 10; a++) {
        for (let b = 1; b < 10; b++) {
            expect(a + b).not.toBe(0)
        }
    }
})
```

**Equalto** is used to check value of an object

```js
test('object assignment', () => {
    const data = { one: 1 }
    data['two'] = 2
    expect(data).toEqual({ one: 1, two: 2 })
})
```

**Truthiness**

```js
test('null', () => {
    const n = null
    expect(n).toBeNull() // toBeNull matches only null
    expect(n).toBeDefined() // toBeUndefined matches only undefined
    expect(n).not.toBeUndefined() // toBeDefined is the opposite of toBeUndefined
    expect(n).not.toBeTruthy() // toBeTruthy matches anything that an if statement treats as true
    expect(n).toBeFalsy() // toBeFalsy matches anything that an if statement treats as false
})
```

**Numbers**

```js
test('two plus two', () => {
    const value = 2 + 2
    expect(value).toBeGreaterThan(3)
    expect(value).toBeGreaterThanOrEqual(3.5)
    expect(value).toBeLessThan(5)
    expect(value).toBeLessThanOrEqual(4.5)
    expect(value).toBeCloseTo(4.0) // toBeCloseTo is used for floating numbers

    // toBe and toEqual are equivalent for numbers
    expect(value).toBe(4)
    expect(value).toEqual(4)
})
```

**String**

```js
// Regular expression can be used to check strings
test('there is no I in team', () => {
    expect('team').not.toMatch(/I/)
})

test('but there is a "stop" in Christoph', () => {
    expect('Christoph').toMatch(/stop/)
})
```

**Array**

```js
const shoppingList = ['diapers', 'kleenex', 'trash bags', 'paper towels', 'beer']

test('the shopping list has beer on it', () => {
    expect(shoppingList).toContain('beer')
    expect(new Set(shoppingList)).toContain('beer')
})
```

**Exceptions**

```js
function compileAndroidCode() {
    throw new Error('you are using the wrong JDK')
}

test('compiling android goes as expected', () => {
    expect(compileAndroidCode).toThrow()
    expect(compileAndroidCode).toThrow(Error)

    // You can also use the exact error message or a regexp
    expect(compileAndroidCode).toThrow('you are using the wrong JDK')
    expect(compileAndroidCode).toThrow(/JDK/)
})
```

**Asynchronous**

```js
test('the data is peanut butter', (done) => {
    function callback(data) {
        try {
            expect(data).toBe('peanut butter')
            done()
        } catch (error) {
            done(error)
        }
    }

    fetchData(callback)
})
```

**Promises**

```js
test('the data is peanut butter', async () => {
    const data = await fetchData()
    expect(data).toBe('peanut butter')
})

test('the fetch fails with an error', async () => {
    expect.assertions(1)
    try {
        await fetchData()
    } catch (e) {
        expect(e).toMatch('error')
    }
})

test('the data is peanut butter', async () => {
    await expect(fetchData()).resolves.toBe('peanut butter')
})

test('the fetch fails with an error', async () => {
    await expect(fetchData()).rejects.toThrow('error')
})
```

## Setup and Teardown

```js
beforeAll(() => console.log('1 - beforeAll'))
afterAll(() => console.log('1 - afterAll'))
beforeEach(() => console.log('1 - beforeEach'))
afterEach(() => console.log('1 - afterEach'))
test('', () => console.log('1 - test'))
describe('Scoped / Nested block', () => {
    beforeAll(() => console.log('2 - beforeAll'))
    afterAll(() => console.log('2 - afterAll'))
    beforeEach(() => console.log('2 - beforeEach'))
    afterEach(() => console.log('2 - afterEach'))
    test('', () => console.log('2 - test'))
})

// 1 - beforeAll
// 1 - beforeEach
// 1 - test
// 1 - afterEach
// 2 - beforeAll
// 1 - beforeEach
// 2 - beforeEach
// 2 - test
// 2 - afterEach
// 1 - afterEach
// 2 - afterAll
// 1 - afterAll
```

## Snapshot

```js
test('', () => {
    expect(value).toMatchSnapshot() // Creates a snapshot
})
```
