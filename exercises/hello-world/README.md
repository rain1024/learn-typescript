# Instructions

The classical introductory exercise. Just say "Hello, World!".

"Hello, World!" is the traditional first program for beginning programming in a new language or environment.

The objectives are simple:

Write a function that returns the string "Hello, World!".
Run the test suite and make sure that it succeeds.
Submit your solution and check it at the website.
If everything goes well, you will be ready to fetch your first real exercise.

Setup
Go through the setup instructions for TypeScript to install the necessary dependencies:

https://exercism.org/docs/tracks/typescript/installation

Requirements
Install assignment dependencies:

$ yarn install
Making the test suite pass
Execute the tests with:

$ yarn test
In many test suites all but the first test have been skipped.

Once you get a test passing, you can unskip the next one by changing xit to it.

Tutorial
This section is a step-by-step guide to solving this exercise.

This exercise has two files:

hello-world.ts
hello-world.test.ts
The first file is where you will write your code. The second is where the tests are defined.

The tests will check whether your code is doing the right thing. You don't need to be able to write a test suite from scratch, but it helps to understand what a test looks like, and what it is doing.

Open up the test file, hello-world.test.ts. There is a single test inside:

it('says hello world', () => {
  expect(hello()).toEqual('Hello, World!')
})
Run the test now, with the following command on the command-line:

$ yarn test
The test fails, which makes sense since you've not written any code yet.

The failure looks like this:

    × says hello world (5ms)

  ● Hello World › says hello world

    expect(received).toEqual(expected) // deep equality

    Expected: "Hello, World!"
    Received: "Goodbye, Mars!"

      4 |
      5 |   it('says hello world', () => {
    > 6 |     expect(hello()).toEqual('Hello, World!')
        |                     ^
      7 |   })
      8 |
      9 | })

      at Object.it (hello-world.test.ts:6:32)
And these are those code lines with probable defects in the hello-world.test.ts file:

the 6th line:

    expect(hello()).toEqual('Hello, World!')
                    ^
Hence the problem is with the hello() function call. We can see that the test is expecting 'Hello, World!' as output, but instead is getting "Goodbye, Mars!".

So let's check now this function in the hello-worlds.ts file:

export function hello(): string {
  return 'Goodbye, Mars!'
}
Now we see that the function returns the incorrect string, which is the reason for our failure. Let's fix this by changing the returned value:

export function hello(): string {
  return 'Hello, World!'
}
Run the test again:

 PASS  ./hello-world.test.ts
  Hello World
    √ says hello world (4ms)
And it passes!