# create-reducer-redux

A redux reducer generator function

## Install
```bash
npm install --save @funnyfoo/create-reducer-redux
# or
yarn add @funnyfoo/create-reducer-redux
```

## Usage
```js
import createReducer from '@funnyfoo/create-reducer-redux'

const Types = {
  INCREMENT: 'INCREMENT',
  DECREMENT: 'DECREMENT',
  ADDITION: 'ADDITION'
}

const increment = function() {
  return {
    type: Types.INCREMENT,
  }
}

const decrement = function() {
  return {
    type: Types.DECREMENT,
  }
}

const addX = function(x) {
  return {
    type: Types.ADDITION,
    payload: x
  }
}

const inc = x => x + 1
const dec = x => x - 1

const initialState = 0

const reducer = createReducer([
  [ Types.INCREMENT, inc ],
  [ Types.DECREMENT, dec ],
  [ Types.ADDITION, (state, action) => state + action.payload ],
], initialState)

reducer(undefined, addX(12))  // => 12
reducer(12, decrement())  // => 11

```
