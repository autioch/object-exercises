# Object exercises
Simple examples for manipulating objects.

## Create new object

<details>
  <summary>Solution</summary>

```javascript
const obj1 = {};
const obj2 = Object.create({});

function Obj3(){}
const obj3 = new Obj3();

class Obj4 {}
const obj4 = new Obj4();
```
</details>

## Add new properties to object

Input
```javascript
{
  a: 1
}
```

Output
```javascript
{
  a: 1,
  b: 2
}
```

<details>
  <summary>Solution</summary>

```javascript
INPUT.b = 2;
INPUT['b'] = 2;
Object.defineProperty(INPUT, 'b', { value: 2 })

```
</details>


## Get value of a property

Input
```javascript
{
  a: 1,
  b: {
    c: 3
  }
}
```

Output
```javascript
const valueOfC = 3;
```

<details>
  <summary>Solution</summary>

```javascript
const valueOfC = INPUT.b.c;
const valueOfC = INPUT['b']['c'];
const { b: { c: valueOfC } } = INPUT;
```
</details>


## Get object property keys, values and both

Input
```javascript
{
  a: 1,
  b: 2
}
```

Output
```javascript
const keys = ['a', 'b'];
const values = [1, 2];
const both = [['a', 1], ['b', 2]];
```

<details>
  <summary>Solution 1</summary>

```javascript
const keys = Object.keys(INPUT);
const values = Object.keys(INPUT);
const both = Object.keys(INPUT);
```
</details>


<details>
  <summary>Solution 2</summary>

```javascript
const keys = [];
const values = [];
const both = [];

for (const prop in INPUT) {
  keys.push(prop);
  values.push(INPUT[prop]);
  both.push([prop, INPUT[prop]]);
}
```
</details>


## Clone object shallow, deep

Changing value of `c` will change it across all shallow copies.

Input
```javascript
{
  a: 1,
  b: {
    c: 3
  }
}
```

<details>
  <summary>Solution</summary>

```javascript
const shallow = { ...INPUT };
const deep = JSON.parse(JSON.stringify(INPUT));
```
</details>

## Merge objects
Create new object from provided ones.

Input
```javascript
const obj1 = { a: 1 };
const obj2 = { a: 2, b: { c: 3 } };
```

Output
```javascript
{
  a: 2,
  b: {
    c: 3
  }
}
```

<details>
  <summary>Solution 1</summary>

```javascript
{
  ...obj1,
  ...obj2
}
```
</details>

<details>
  <summary>Solution 2</summary>

```javascript
Object.assign({}, obj1, obj2)
```
</details>


## Create function for creating object with dynamic property

Input
```javascript
const key = Math.random();
const value = Math.random();
```



<details>
  <summary>Solution 1</summary>

```javascript
function makeObject(key, value){
  return {
    [key]: value
  };
}
```
</details>
