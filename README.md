This project connects with an API and displays verses in both original Arabic and English translation. I am going to use React-Redux combinations for this App.

The first step is to create the app as follows:

```
npx create-react-app react-redux-verse-display
```

Then upload to a github repository named the same `react-redux-verse-display`. 

In the local terminal:
```
git init
git add .
git commit -m 'first'
git remote add origin https://github.com/abdulbaqi/react-redux-verse-display.git
git push -u origin master
```

## basic scaffolding

Delete all files inside `src` and create a new `index.js` with the content:

```javascript
import React from 'react';
import ReactDOM from 'react-dom';
import App from './component/App';

ReactDOM.render(<App />, document.querySelector('#root'));

```

and then create the folder with content `component/App.js`

```javascript
import React from 'react';

class App extends React.Component {
    render()
    {
        return <div>React started successfully...</div>;
    }
}

export default App;
```
As an aesthetics, incorporate `Semantic UI` also in the `public/index.html` file. 
Note: I am using `prettier` within vcode to tidy up the code. Use `alt+shift+f`. 

## get redux, axios and thunk

Now, we need to get four packages that brings redux, helps in getting api data (i.e., axios) and redux-thunk (which we will discuss later).

Here is the `index.js` with integration of redux

```javascript
import React from "react";
import ReactDOM from "react-dom";
import { Provider } from "react-redux";
import { createStore } from "redux";

import App from "./component/App";
import reducers from "./reducers";

ReactDOM.render(
  <Provider store={createStore(reducers)}>
    <App />
  </Provider>,
  document.querySelector("#root")
);
```

And the `reducers/index.js` file

```javascript 
import { combineReducers } from "redux";

export default combineReducers({
  replaceMe: () => "I am dummy"
});

```

