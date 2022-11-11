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

