# signal-utils

Utils for the [Signal's Proposal](https://github.com/proposal-signals/proposal-signals).

## APIs 

### `@signal`

A utility decorator for easily creating signals 

```ts
import { signal } from 'signal-utils';

class State {
    @signal accessor #value = 3;

    get doubled() {
        return this.#value * 2;
    }

    increment = () => this.#value++;
}

let state = new State();

state.doubled // 6
state.increment()
state.doubled // 8
```

### `Array`

wip

A reactive Array

### `Object`

A reactive Object

```js
import { ReactiveObject } from 'signal-utils/object';

let obj = new ReactiveObject({
    isLoading: true,
    error: null,
    result: null,
});

obj.isLoading // true
obj.isLoading = false
obj.isLoading // false
```

In this example, we could use a reactive object for quickly and dynamically creating an object of signals -- useful for when we don't know all the keys boforehand, or if we want a shorthand to creating many named signals.

### `Map`

wip

A reactive Map

### `WeakMap`

wip

A reactive WeakMap

### `Set`

wip

A reactive Set

### `WeakSet`

wip

A reactive WeakSet

### `async`

wip

A reactive async function with pending/error state handling

### `localCopy` + `@localCopy`

wip

utilities for the [localCopy](https://github.com/tracked-tools/tracked-toolbox?tab=readme-ov-file#localcopy) pattern

### `dedupe` + `@dedupe`

wip

utilities for the [dedupe](https://github.com/tracked-tools/tracked-toolbox?tab=readme-ov-file#dedupetracked) pattern.


## Contributing

**Starting dev**

```bash
pnpm install
pnpm start
```

This will start a [concurrently](https://www.npmjs.com/package/concurrently) command that runs the vite build and vitest tests in parallel.

Vitest isn't being used _within_ the package, because we want to exercise the public API, generated types, etc (through package.json#exports and all that).
