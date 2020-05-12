This repository correspond to the TDD Calculator assignment.

## Setup

### Environment

- Node v12: https://nodejs.org/en/
  (alernative if Mac/Linux https://github.com/nvm-sh/nvm )
- Yarn v1: https://classic.yarnpkg.com/lang/en/

### Setup

Once you download it, add all libraries by executing:

```zsh
$ yarn
```

### Run

```zsh
$ yarn test
```

The initial test result is the following:

```
 FAIL  src/calculator.spec.js
  ✕ 1 | "" (1ms)

  ● 1 | ""

    TypeError: _calculator.Calculator is not a constructor

       7 |   ${1}  | ${""}
       8 | `('$order | "$sequence"', ({ sequence }) => {
    >  9 |   expect(new Calculator()).toSatisfy(sequence)
         |          ^
      10 | })
      11 |
      12 | /*

      at src/calculator.spec.js:9:10

Test Suites: 1 failed, 1 total
Tests:       1 failed, 1 total
Snapshots:   0 total
Time:        0.375s, estimated 1s
Ran all test suites related to changed files.

Watch Usage: Press w to show more.
```

## Instructions

### Operators

You can use javascript native operators for addition and multiplication.

### Transformations

See https://www.youtube.com/watch?v=VW4hHaid3PE

When refactoring or fixing a test in production code,
pick always the first transformation of the following
list:

1. Null
2. Null to Constant
3. Constant to Variable
4. Add Computation
5. Split Flow
6. Variable to Array
7. Array to Container
8. If to While
9. Recurse
10. Iterate
11. Assign
12. Add Case

### Tests

Tests are already written.
You have to write no tests.

There is only one test function call,
which executes a table of tests.

Initially there is only one table test line.
The rest of lines that you have to execute
are below in a comment.

### Order

There are test table lines inside a comment below
the test function call.

This comment contains all test table lines
that you have to implement.
Each line has an order number that you have to respect.

In order to complete the assignment
move one by one
to the test function call
and solve each before passing to the next one.
Ex:

```javascript
test.each`
  order | sequence
  ${1}  | ${""}
`('$order | "$sequence"', ({ sequence }) => {
  expect(new Calculator()).toSatisfy(sequence)
})

/*
  order | sequence
  ${2}  | ${"[0]"}
  ${3}  | ${"0[0]"}
  ${4}  | ${"1[1]"}
  ${5}  | ${"56[56]"}
  ${6}  | ${"0![1]"}
  ...
```

Once the first is solved, copy the next test, and make it pass:

```javascript
test.each`
  order | sequence
  ${1}  | ${""}
  ${2}  | ${"[0]"}
`('$order | "$sequence"', ({ sequence }) => {
  expect(new Calculator()).toSatisfy(sequence)
})

/*
  order | sequence
  ${3}  | ${"0[0]"}
  ${4}  | ${"1[1]"}
  ${5}  | ${"56[56]"}
  ${6}  | ${"0![1]"}
  ...
```

And so on:

```javascript
test.each`
  order | sequence
  ${1}  | ${""}
  ${2}  | ${"[0]"}
  ${3}  | ${"0[0]"}
`('$order | "$sequence"', ({ sequence }) => {
  expect(new Calculator()).toSatisfy(sequence)
})

/*
  order | sequence
  ${4}  | ${"1[1]"}
  ${5}  | ${"56[56]"}
  ${6}  | ${"0![1]"}
  ...
```

Continue in order until implementing all test table lines inside the comment.

**Important**:
Follow the exact order and fix
the minimal amount of your production code
in order to pass the test.

It is possible that time to time you pass more than one
test table line.
Only few tests are redundants, it is to make
sure that the implementation is correct.
It happens, but not often.
If you find that one production code fixes many lines,
review your code to be sure that you
have not implemented more than necessary.

### Commits

You have to do a commit for each test that you pass.
Name the commit as: "Test table line X"
where X is the test table line order number.

If you forgot to commit,
undo the changes,
reset to a previous commit,
and redo again from the last correct commit.

Be careful, your grade depends on this.

### Grades

This practice evaluates how good are you following TDD.

For this reason,
the teacher will subsitute the testing file by its own,
and will test commit by commit
to know how you have been progressing in the implementation.

Your **note can be reduced by** the following parameters:

- you do not pass secret teacher tests (extra checks that logic is correct),
- you pass too many commits at once,
- you skip the order and solve test table lines out of order,
- you do not keep a clean production code at all times,
- you cheat (copy from other colleages or copy a solution from internet)
- you change the expected API for the Calculator class (it emerges from tests)

The **maximum grade** that you can aspire is computed by the maximum
test table line order that you reach passing all previous tests.

The corresponding maximum grades are:

- 1: `${5} | ${"56[56]"}`
- 2: `${11} | ${"9![362880]"}`
- 3: `${16} | ${"12+34=[46]"}`
- 4: `${20} | ${"1+2+4=[7]"}`
- 5: `${24} | ${"12*34=[408]"}`
- 6: `${28} | ${"2*3*4=[24]"}`
- 7: `${30} | ${"2+3*[3]"}`
- 8: `${32} | ${"4*3+[12]"}`
- 9: `${35} | ${"2+3*4+5=[19]"}`
- 10: `${40} | ${"5!+3!*4!=[264]"}`
