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