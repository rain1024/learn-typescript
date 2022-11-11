# Classes

```
class User {
    firstName: string
    lastName: string

    constructor(firstName: string, lastName: string){
        this.firstName = firstName;
        this.lastName = lastName;
    }

    getFullname(): string {
        return this.firstName + ' ' + this.lastName;
    }
}

const user = new User('Vu', 'Anh');
console.log(user);
console.log(user.getFullname());
console.log(user.firstName);
console.log(user.lastName);
```

`In TypeScript, each member is public by default.`

## Private

```
class User2 {
    private firstName: string
    private lastName: string

    constructor(firstName: string, lastName: string){
        this.firstName = firstName;
        this.lastName = lastName;
    }

    getFullname(): string {
        return this.firstName + ' ' + this.lastName;
    }
}
const user2 = new User2('Vu', 'Anh');
console.log(user2);
console.log(user2.getFullname());
console.log(user2.firstName);
```