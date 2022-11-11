# Working with DOM

```
const element = document.querySelector('foo');
console.log('someElement', (element as any).value); // Incorrect fix

const element2 = document.querySelector('foo') as HTMLInputElement; // Correct fix 
console.log('element2', element2.value); 

// Add listener
const element3 = document.querySelector('foo') as any;
element3.addEventListener('blue', (event: any) => {
    const target = event.target as HTMLInputElement;
    console.log('event', target.value)
})
```