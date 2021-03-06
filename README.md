# Hooks Combine Reducers
Building a complex React app using the `useReducer` hook can lead to long reducers.

It's better to split reducers & states into seperate files. `hooks-combine-reducers` accepts multiple reducer files or states and combines them into a single object.

## How To Use

Create an initial state:

```
const initialState = {
  key: value
};
```

Then create multiple reducer functions:
```
const reducer1 = (state, action) => {
  switch (action.type) {
    case "ACTION":
      return
    default:
      return state;
  }
};

const reducer2 = (state, action) => {
  switch (action.type) {
    case "ACTION":
      return
    default:
      return state;
  }
};

```

And finally combine the reducers:

```
  const [state, dispatch] = React.useReducer(
    combineReducers({
      keyName1: reducer1,
      keyName2: reducer2
    }),
    initialState
  );
```

## Combining State

You may want to separate state into different objects for better organization. 

```
import { combineReducers, combineStates } from 'hooks-combine-reducers';


const state1 = {
  ...
}

const state2 = {
  ...
}

const reducer1 = (state, action) => {
  switch (action.type) {
    case "ACTION":
      return
    default:
      return state;
  }
};

const reducer2 = (state, action) => {
  switch (action.type) {
    case "ACTION":
      return
    default:
      return state;
  }
};

const [state, dispatch] = React.useReducer(
  combineReducers({
    keyName1: reducer1,
    keyName2: reducer2
  }),
  combineStates([state1, state2])
);

```