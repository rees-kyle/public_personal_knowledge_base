---
id: upj2jtnqvywuudsitlwv2ff
title: 2 - Redux
desc: ''
updated: 1729252341052
created: 1729248845662
---

Redux **is a popular** `state management library` for JavaScript applications, commonly used with React. It **helps** `manage and centralize` `the state of` `an application in` `a predictable way`. Here's a quick **breakdown** of how Redux works:

### Core Concepts
1. **Store**: The `single` `source of truth` `that holds the entire` `state of the application`.
2. **Actions**: **Plain** `JavaScript objects` **that represent** `an intention` `to change the state`. They `must have` **a** `'type' property` `and optionally` **include** `a payload` `with additional data`.
3. **Reducers**: `Functions` `that specify` `how the state changes` `in response to actions`. **They take the** `current state` `and` **an** `action` `as arguments` `and return` **a** `new state`.
4. **Dispatch**: A `method` **used** `to send` **an** `action to` **the** `Redux store`. The `store` **will then** `use` **a** `reducer to` `update` **the** `state` `based on` **the** `action`.
5. **Selectors**: `Functions` **that** `retrieve` **specific** `pieces of` `state from` **the** `store`.

### Key Concepts in Redux

- **Immutability**: The `state` **is** `never` `mutated directly`. **Instead**, **a** `new copy of` **the** `state` **is** `returned` `every time it is` `updated`.
- **Single Source of Truth**: The `entire` `state of` **the** `application` **is** `kept in` `one central place` (**the** `store`), **which** `simplifies` `debugging` **and** `tracing changes`.
- **Predictability**: `Because` `state changes` **are** `centralized` `and handled by` `reducers`, **the** `flow of data` **is** `predictable`.

### Example of Redux Flow

1. **Action**: 
    ```javascript
    // Define an increment function
    // This function returns an action object with a type of 'INCREMENT'
    const increment = () => ({ 
        type: 'INCREMENT' 
    });
    ```

2. **Reducer**:
    ```javascript
    // Define a counter reducer function
    // The state parameter defaults to 0, representing the current count
    // The action parameter is an object that determines how the state should change
    const counterReducer = (state = 0, action) => {
        
        // Switch statement to handle different action types
        switch (action.type) {
            
            // If the action type is 'INCREMENT', increase the state by 1
            case 'INCREMENT':
                return state + 1;
            
            // If the action type is 'DECREMENT', decrease the state by 1
            case 'DECREMENT':
                return state - 1;
            
            // For any other action type, return the current state
            default:
                return state;
        }
    };
    ```

3. **Store**:
    ```javascript
    // Import the createStore function from the 'redux' library
    import { createStore } from 'redux';

    // Create a store using the counterReducer
    // The store holds the application's state and allows state changes based on dispatched actions
    const store = createStore(counterReducer);
    ```

4. **Dispatch**:
    ```javascript
    // Dispatch the increment action to the store
    // This will trigger the counterReducer to update the state based on the 'INCREMENT' action
    store.dispatch(increment());
    ```

`Redux` **can be used** `to manage` `the state of` `different components`, **such as** `form inputs`, `UI states`, **or** `fetched data` **from APIs**, `all in one place`.