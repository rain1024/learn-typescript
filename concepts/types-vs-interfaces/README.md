# Types vs Interfaces

**ℹ️ What are key differences between types and interfaces?**

> On the typescript documentation page, it does sugest to use interface. Because ideal property of software as being open to extension, and as such you should always use an interface over a type alias if possible. That is especially true if you're writing a library that you're exporting functions and type information, it's better to export interfaces than types because interfaces can be extended and changed to fit the needs of the application.

> Types are static. They're just an alias to a shape. You can make new types by doing unions and intersections but you can't change the type itself.

**ℹ️ What should I be using: interfaces or types?**

Short Answer: If you're working with object or classes, then using interface. If you're not using objects or classes, you want to type a function, I want to make a type alias, then using type.

Be consistent with yourself and your team.

## Intefaces 

```ts
interface Person {
    name: String;
    hungry: boolean;
}

const me: Person = {
    name: 'Harry',
    hungry: false
}

// implement a class from an interface
class WorkPerson implements Person {
    constructor(public name: string, public hungry: boolean){};
}

// interface with function 
interface Greeting {
    (name: string): string
}
const myGreeting: Greeing = (name: string) => 'Hello!';
console.log(myGreeting('Hi'));

// extends new interface from an interact
interface Youtuber extends Person {
    youtube: boolean
}
const HarryWolff: Youtuber = {
    name: 'Harry',
    hungry: false,
    youtube: true
}
console.log(HarryWolff);
```

## Types 

```ts
type Hungry = boolean;
type Greeting = (name: string) => string;

type Person = {
    name: string,
    hungry: boolean
};

const harry: Person = {
    name: 'Harry',
    hungry: true
}
console.log(harry);

// Type Intersections
type WorkPerson = Person & {
    youtube: boolean
}

const harry2: WorkPerson = {
    name: 'Harry',
    hungry: true,
    youtube: true
}

// Type Union 
type Youtuber = { youtuber: boolean }
type WorkerYoutuber = Person | Youtuber;
const harry3: WorkerYoutuber = {
    youtuber: true
} 
```

## Futher Readings 

* ▶️ 2020, [TypeScript Interfaces vs Types](https://www.youtube.com/watch?v=crjIq7LEAYw&ab_channel=HarryWolff), Harry Wolff