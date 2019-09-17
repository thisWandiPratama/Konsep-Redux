# Konsep-Redux
Belajar Memahami Konsep Cara Kerja Redux dengan React Native

# 4 Tahap Memahami Redux
- Store
Merupakan Wadah Untuk Menampung State

- Reducers
Meruapakan Kumpulan Function Memiliki Perintah Untuk Melakukan Perubahan State yang ada di Store

- Despatchin Action
Merupakan Proses Pemanggilan Reducers tujuannya reducers dijalankan. Despathcing Action memiliki properti yang wajib ada yitutype dan valuenya sesuai keinginan namun huruf KAPITAL

```
import React from 'react'
import { Text, View } from 'react-native'
import {createStore} from 'redux'


// Define the initial state of our store
const initialState = {
  value: 0,
  age: 21
}

// Define a reducer
const rootreducer = (state = initialState, action) => {
  // if (action.type === 'INCREMENT') {
  //   return {
  //     ...state,
  //     value: state.value + action.addvalue
  //   }
  // }
  // if (action.type === 'MIN-AGE') {
  //   return {
  //     ...state,
  //     age: state.age - action.changeage
  //   }
  // }
  
  switch(action.type){
    case 'INCREMENT':
       return {
      ...state,
      value: state.value + action.addvalue
    }
       case 'MIN-AGE':
      return {
        ...state,
        age:state.age - action.changeage
      }
    default:
      return state
  }

}



// Create a store, passing our reducer function and our initial state
const store = createStore(rootreducer)
// Now we can dispatch actions, which are understood by our store/reducer



store.dispatch({type: 'INCREMENT', addvalue: 7 })
store.dispatch({type: 'MIN-AGE', changeage: 5})


/// We're done! Redux is all set up. Here's how we can use it:




// Calling `store.getState()` returns our state object
export default function App() {
  return (
    <View>
    <Text style={{fontSize: 50}}>
     value  {store.getState().value}
    </Text >
    <Text style={{fontSize: 50}}> age {store.getState().age}
</Text>
    </View>
  )
}
```

# Screenshoot
![ss](https://github.com/thisWandiPratama/Konsep-Redux/blob/master/ss.jpeg)
