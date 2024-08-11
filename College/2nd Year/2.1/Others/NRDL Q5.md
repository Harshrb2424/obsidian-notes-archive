# AIM: 
Create a TODO application in react with necessary components and deploy 
it into github 
# DESCRIPTION: 
Let’s create a simple TODO application in React and deploy it to 
GitHub Pages.

## 1. Set Up the React App:
```bash
npx create-react-app todo-app
cd todo-app
```
## 2. Create Necessary Components:
src/components/TodoForm.js:
```js
import React, { useState } from 'react';

const TodoForm = ({ onAdd }) => {
  const [text, setText] = useState('');

  const handleSubmit = (e) => {
    e.preventDefault();
    if (text.trim() !== '') {
      onAdd(text);
      setText('');
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="text"
        value={text}
        onChange={(e) => setText(e.target.value)}
        placeholder="Add a new todo"
      />
      <button type="submit">Add</button>
    </form>
  );
};

export default TodoForm;
```

src/components/TodoList.js:
```js
import React from 'react';
const TodoList = ({ todos, deleteTodo }) => {
  return (
    <ul>
      {todos.map((todo) => (
        <li key={todo.id}>
          {todo.text}
          <button onClick={() => deleteTodo(todo.id)}>Delete</button>
        </li>
      ))}
    </ul>
  );
};
export default TodoList;
```

src/App.js:
```js
import React, { useState } from "react";
import TodoForm from "./components/TodoForm";
import TodoList from "./components/TodoList";
function App() {
  const [todos, setTodos] = useState([]);
  const addTodo = (text) => {
    setTodos([...todos, { id: Date.now(), text }]);
  };
  const deleteTodo = (id) => {
    setTodos(todos.filter((todo) => todo.id !== id));
  };
  return (
    <div className="App">
      <h1>TODO App</h1>
      <TodoForm addTodo={addTodo} />
      <TodoList todos={todos} deleteTodo={deleteTodo} />
    </div>
  );
}
export default App;
```

## 3. Create a GitHub Repository: Create a new repository on GitHub.
## 4. Initialize Git and Push to GitHub:
```
git init
git add .
git commit -m "Todo React App"
git remote add origin https://github.com/your-username/your-repo-name.git
git push -u origin master
```

## 5. Install GitHub Pages: npm install gh-pages --save-dev

## 6. Add Deploy Script to package.json:
Update your package.json with the following:
```json
"scripts": {
 "start": "react-scripts start",
 "build": "react-scripts build",
 "predeploy": "npm run build",
 "deploy": "gh-pages -d build",
 "test": "react-scripts test",
 "eject": "react-scripts eject"
}
```

## 7. Deploy to GitHub Pages: npm run deploy

## 8. Access Your Deployed App:
Visit` https://<username>.github.io/<repository-name>` in your browser to see your 
deployed TODO app.
Replace <username> with your GitHub username and <repository-name> with the 
name of your GitHub repository.
Now, you have a simple TODO application deployed on GitHub Pages. Users can 
add and delete tasks directly on the deployed app.