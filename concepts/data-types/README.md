Data Types

```
const getFullName = (name: string, surname: string) => {
    return name + ' ' + surname;
}

console.log(getFullName("Vu", "Anh"));
console.log(getFullName(true, 0));
```

## Objects

Option 1:

```
interface User {
    name: string,
    age: number
}
const user1: User = {
    name: 'Monster 1',
    age: 0
}

const user2: User = {
    name: 'Monster 2'
}
```

Option 2:

```
interface User {
    name: string,
    age?: number
}
const user1: User = {
    name: 'Monster 1',
    age: 0
}

const user2: User = {
    name: 'Monster 2'
}
```

## Union & Type Alias

```
let username: string = 'Vu Anh';
let pageName: string | number = 0;
let errorMessage: string | null = null;
console.log(username);
console.log(pageName);
console.log(errorMessage);

interface IUser {
    name: string,
    surname: string
};
type ID = string
interface IPerson {
    id: ID;
}
let user: IUser | null = null;
let someProp: string | number | null | undefined | string[] | object = null;
let person = {'id': 1};
console.log(user);
console.log(person);

type PopularTag = string
type MaybePopularTag = string | null
const popularTags: PopularTag[] = ["dragon", "coffee"];
const dragonTag: MaybePopularTag = "dragon";
console.log(popularTags);
console.log(dragonTag);
```

## Any, never, void, unknown

```
const doSomething = (): void => {
    console.log('doSomething');
}
doSomething();

// In some situations, not all type information is available or its declaration would take
// an inappropriate amount of effort.
let foo: any = 'foo';
// [ERR]: foo.bar is not a function
// console.log(foo.bar());

// The never type represents the type of values that never occur. 
const doError = (): never => {
    throw "never";
}
// doError();

let vAny: any = 10;
let vUnknown: unknown = 10;
let s1: string = vAny;
// [Erorr] Type 'unknown' is not assignable to type 'string'.
// let s2: string = vUnknown;

// Type assertion
let vUnknown2: unknown = 10;
let s2: string = vUnknown2 as string;
console.log(s2);

let pageNumber: string = '1';
// let numericPageNumber: number = pageNumber as number;
let numericPageNumber: number = pageNumber as unknown as number;
```