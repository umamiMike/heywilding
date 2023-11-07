---
title: "How to Use UseContext and UseReducer"
date: 2022-07-10T16:00:59-07:00
draft: true
tags:
  - react
  - hooks
category:
- articles
---

```
discover how to work with context and reducer in react
    1 create reducer function
        can be exported from its own file or in the App.js
    2 in App.js
        2.1 add useReducer to app
            state
                the returned state to use
            dispatch
                is a function you use to send data to the reducer function
        2.2 import createContext
        2.3 add
        export const StateContext = React.createContext()
        2.4 wrap the app in AppContext.Provider
            value={{ stateValue: state, stateDispatch: dispatch  }}
    3 In the child component
        3.1 import the exported StateContext from the App.js
        3.2 in the component add a useContext(StateContext)
        3.3 add a button onClick() or some other triggering event
            {() => dispatch('action in case statement of reducer')}
        3.4 to be able to pass a value the dispatch function
            {() => dispatch({type: 'action name', payload:  somevalue })}

```

:
discover how to work with context and reducer in react

create reducer function

## can be exported from its own file or in the App.js

in App.js

add useReducer to app

### state

#### the returned state to use

### dispatch

#### is a function you use to send data to the reducer function

import createContext

add
export const StateContext = React.createContext()

wrap the app in AppContext.Provider

### value={{ stateValue: state, stateDispatch: dispatch  }}

1. In the child component
1. import the exported StateContext from the App.js
1. in the component add a useContext(StateContext)
1. Simple dispatch without any payload
1.
1. add a button onClick() or some other triggering event

```javascript
{
  () => dispatch("action in case statement of reducer");
}
```

pass a value the dispatch function

```javascript
{
  () => dispatch({ type: "action name", payload: somevalue });
}
```
