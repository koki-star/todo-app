# Learning Practice: White Box Testing

This is a small todo app. I practiced white box testing, which means I looked at the code and wrote tests based on what I saw.

The file I tested is `src/todoUtils.ts`. It has three functions: `createTodo`, `addTodo`, and `countDone`. All of my tests are in `src/todoUtils.test.ts`.

## How to run

```bash
npm install
npm test
```

You can also run the coverage report with:

```bash
npm run coverage
```

To open the app in the browser:

```bash
npm run dev
```

## Step 1: Statement Coverage

Statement coverage checks that every line ran at least once.

`createTodo` has no if statements. I called it with Buy milk. I checked that the text is Buy milk, that `done` starts as false, and that `id` is a number. One test was enough to run every line.

## Step 2: Branch Coverage

Branch coverage checks both sides of an if.

`addTodo` trims the text. If the text is empty or only spaces, it gives back the same list. If the text is real, it adds a new todo.

I wrote one test with only spaces. The list stayed empty.
I wrote another test with Buy milk. The list got one todo.

## Step 3: Loop Coverage

Loop coverage checks a loop with zero items, one item, and several items.

`countDone` uses a for loop to count finished todos.

- Empty list: it returns 0
- One finished todo: it returns 1
- Three todos, two finished: it returns 2

The last test also runs both sides of the if inside the loop.

## Step 4: Coverage report

I ran `npm run coverage`. The report for `todoUtils.ts` should show 100 for statements, branches, functions, and lines.

## AI Transparency

AI was used to create part of this file and to clean up its writing and formatting.
