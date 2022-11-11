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
// Error: Property 'firstName' is private and only accessible within class 'User2'.
console.log(user2.firstName);

## Readonly

```
class User {
    firstName: string;
    lastName: string;
    readonly unchangeableName: string;

    constructor(firstName: string, lastName: string){
        this.firstName = firstName;
        this.lastName = lastName;
        this.unchangeableName = firstName;
    }

    getFullname(): string {
        return this.firstName + ' ' + this.lastName;
    }

    change(): void {
        // Error: Cannot assign to 'unchangeableName' because it is a read-only property.
        this.unchangeableName = "foo";
    }
}

const user = new User('Vu', 'Anh');
console.log(user);
console.log(user.getFullname());
console.log(user.firstName);
console.log(user.lastName);
```

## Interface 

```
interface IUser {
  getFullName(): string;
}

// Class 'User' incorrectly implements interface 'IUser'.
//   Property 'getFullName' is missing in type 'User' but required in type 'IUser'.
// class User implements IUser {
  
// }

class User implements IUser {
    getFullName(): string {
        return "Hola";
    }
}

const user = new User();
```

## Static

```
class User {
    static maxAge: number = 100;
}

console.log(User.maxAge);
```

## Inherantance

```
class User {
    firstName: string;
    lastName: string;

    constructor(firstName: string, lastName: string){
        this.firstName = firstName;
        this.lastName = lastName;
    }
}

class Admin extends User {
    private editor: string;

    setEditor(editor: string): void {
        this.editor = editor;
    }

    getEditor(): string {
        return this.editor;
    }
}
const user = new User("User", "1");
console.log(user);

const admin = new Admin("Mr", "Admin");
console.log(admin);
admin.setEditor("Editor 1");
console.log(admin.getEditor());
```