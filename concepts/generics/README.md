# Generics

```
const addId = (obj: any) => {
    const id = Math.random().toString(16);
    return {
        ...obj,
        id
    }
}

const user = {
    name: 'Jack'
}

const result = addId(user);
console.log(result);
// {
//  "name": "Jack",
//  "id": "0.53133d2a63786"
// }
```

## Generatics with Interface

```
const addId = <T>(obj: T) => {
    const id = Math.random().toString(16);
    return {
        ...obj,
        id
    }
}

interface IUser {
    name: string
}
const user: IUser = {
    name: 'Jack'
}

const result = addId<IUser>(user);
console.log(result);

const result2 = addId<string>("foo");
console.log(result2);
```

Generics with template constrain

```
const addId = <T extends object>(obj: T) => {
    const id = Math.random().toString(16);
    return {
        ...obj,
        id
    }
}

interface IUser {
    name: string
}
const user: IUser = {
    name: 'Jack'
}

const result = addId<IUser>(user);
console.log(result);

// Error: Type 'string' does not satisfy the constraint 'object'.
// const result2 = addId<string>("foo");
```

## Generics with interface

```
interface IUser<T> {
    name: string,
    data: T
}
const user1: IUser<number> = {
    name: 'Jack',
    data: 10
}
console.log(user1);

const user2: IUser<{meta: string}> = {
    name: 'John',
    data: {
        meta: 'Wick'
    }
}
console.log(user2);
```

## Generics with muliple tempaltes

```
interface IUser<T, V> {
    name: string,
    data: T,
    meta: V
}
const user1: IUser<number, string> = {
    name: 'Jack',
    data: 10,
    meta: 'Sparrow'
}
console.log(user1);

const user2: IUser<{lastname: string}, number> = {
    name: 'John',
    data: {
        lastname: 'Wick'
    },
    meta: 100
}
console.log(user2);
```
