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