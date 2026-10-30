# Exp 4 – React Lab Exercise: Event Handling in React

## NAME : Lokesh P
## REG NO : 23050010315

## Aim
To create React applications that demonstrate event handling using `onClick`, `onChange`, and `onSubmit` events to handle user interactions, update data, and perform form submissions.

## Objectives
- To understand event handling in React.
- To implement button click events using `onClick`.
- To create interactive applications using `useState()`.
- To show and hide messages using conditional rendering.
- To handle input field changes using `onChange`.
- To handle form submissions using `onSubmit`.
- To retrieve user input using `event.target.value`.
- To prevent page refresh using `event.preventDefault()`.

## Program

### Exercise 1 – Counter

**App.jsx**

```jsx
import { useState } from "react";

function App() {
  const [count, setCount] = useState(0);

  function increase() {
    setCount(count + 1);
  }

  function decrease() {
    setCount(count - 1);
  }

  return (
    <div>
      <h1>Counter</h1>

      <button onClick={increase}>+</button>

      <h2>Count: {count}</h2>

      <button onClick={decrease}>-</button>
    </div>
  );
}

export default App;
```

### Exercise 2 – Show / Hide Message

**App.jsx**

```jsx
import { useState } from "react";

function App() {
  const [show, setShow] = useState(false);

  function handleClick() {
    setShow(!show);
  }

  return (
    <div>
      <h1>Show / Hide Message</h1>

      <button onClick={handleClick}>
        {show ? "Hide Message" : "Show Message"}
      </button>

      {show && (
        <h2>Welcome to React!</h2>
      )}
    </div>
  );
}

export default App;
```

### Exercise 3 – Student Registration Form

**App.jsx**

```jsx
import { useState } from "react";

function App() {
  const [name, setName] = useState("");
  const [regNo, setRegNo] = useState("");
  const [department, setDepartment] = useState("");
  const [submitted, setSubmitted] = useState(false);

  function handleSubmit(event) {
    event.preventDefault();
    setSubmitted(true);
  }

  return (
    <div>
      <h1>Student Registration</h1>

      <form onSubmit={handleSubmit}>
        <input
          type="text"
          placeholder="Student Name"
          value={name}
          onChange={(event) => setName(event.target.value)}
          required
        />

        <br /><br />

        <input
          type="text"
          placeholder="Register Number"
          value={regNo}
          onChange={(event) => setRegNo(event.target.value)}
          required
        />

        <br /><br />

        <input
          type="text"
          placeholder="Department"
          value={department}
          onChange={(event) => setDepartment(event.target.value)}
          required
        />

        <br /><br />

        <button type="submit">Register</button>
      </form>

      {submitted && (
        <div>
          <h2>Student Details</h2>
          <p>Name: {name}</p>
          <p>Register No: {regNo}</p>
          <p>Department: {department}</p>
        </div>
      )}
    </div>
  );
}

export default App;
```

## Output

### Exercise 1 – Counter

<img width="200" height="200" alt="Counter Output" src="https://github.com/user-attachments/assets/11b3ed0b-9a8d-4d0f-88bc-b3a8b191b149" />

### Exercise 2 – Show / Hide Message

**Show Message:**

<img width="400" height="200" alt="Show Message Output" src="https://github.com/user-attachments/assets/e99f5b79-e856-44e7-9650-2bb6df47fe4a" />

**Hide Message:**

<img width="400" height="200" alt="Hide Message Output" src="https://github.com/user-attachments/assets/a8d2233d-aa4c-434c-927d-b72ad5314f6d" />

### Exercise 3 – Student Registration Form

<img width="400" height="400" alt="WhatsApp Image 2026-10-30 at 1 52 24 PM" src="https://github.com/user-attachments/assets/17f794b2-fef3-4596-a37f-d2296bfcbc0d" />

## Result

Thus, React event handling was successfully implemented through three exercises: Counter using `onClick`, Show / Hide Message using `onClick` and conditional rendering, and Student Registration Form using `onChange` and `onSubmit` events. The applications demonstrated handling user interactions and dynamically updating the user interface.
