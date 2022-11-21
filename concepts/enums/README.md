# Enums

```ts
const statuses = {
    notStarted: 0,
    inProgress: 1,
    done: 2
}

console.log('statuses.inProgress = ', statuses.inProgress);

enum Status {
    NotStarted,
    InProgress,
    Done
}
console.log('Status.InProgress = ', Status.InProgress);

let notStartedStatus: Status = Status.Done;
notStartedStatus = 4;
console.log(notStartedStatus);
```

## Enums in Inteface

```ts
enum StatusEnum {
    NotStarted = "NotStarted",
    InProgress = "InProgress",
    Done = "Done"
}

interface ITask {
    id: string,
    status: StatusEnum
}

const task1: ITask = {
    id: '1',
    status: StatusEnum.InProgress
};
const task2: ITask = {
    id: '2',
    status: StatusEnum.Done
}
console.log(task1);
console.log(task2);
```