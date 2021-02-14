# Using Danfojs in React

Danfojs works for both browser and NodeJs environment, and as such is available to frontend frameworks like React and Vue. 

In order to use Danfojs in a library like React, you must install the [browser side version ](https://www.npmjs.com/package/danfojs)from npm. 

```bash
npm install danfojs

or 

yarn add danfojs
```

Follow the steps here to bootstrap a React app, and in your App.js or any file where you want to use danfojs, you can import it as follow:

```bash
import "./App.css";
import * as dfd from "danfojs/danfojs/src/index";
```

Now you have access to all features under the `dfd` namespace. Below is a sample App.js file using danfojs:

```bash
import "./App.css";
import * as dfd from "danfojs/danfojs/src/index";

function App() {

  const df = new dfd.DataFrame(
    { pig: [20, 18, 489, 675, 1776], horse: [4, 25, 281, 600, 1900] },
    { index: [1990, 1997, 2003, 2009, 2014] }
  );
  df.head().print()


  return (
    <div className="App">
      <header className="App-header">
        <a
          className="App-link"
          href="https://danfo.jsdata.org/getting-started"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn Danfojs 
        </a>
      </header>
    </div>
  );
}

export default App;

```

On running the app, we get the following output in the console:

![](../.gitbook/assets/screen-shot-2021-02-14-at-7.22.16-pm.png)

Note that you can also import specific modules. For instance, in the code below we import only the DataFrame module:

```bash
import { DataFrame } from "danfojs/danfojs/src/index";
```

Following these steps, you can use danfojs in any client-side library. 

