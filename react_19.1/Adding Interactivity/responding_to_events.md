### Adding event handlers

```javascript
export default function Button() {
  function handleClick() {
    alert("You clicked me!");
  }

  return <button onClick={handleClick}>Click me</button>;
}
```

#### Functions passed to event handlers must be passed, not called. For example:

- _passing a function (correct)_
  ```javascript
  <button onClick={handleClick}>
  ```
- _calling a function (incorrect)_
  ```javascript
  <button onClick={handleClick()}>
  ```

#### When you write code inline, the same pitfall presents itself in a different way:

- _passing a function (correct)_
  ```javascript
  <button onClick={() => alert('...')}>
  ```
- _calling a function (incorrect)_
  ```javascript
  <button onClick={alert('...')}>
  ```

### Reading props in event handlers

```javascript
function AlertButton({ message, children }) {
  return <button onClick={() => alert(message)}>{children}</button>;
}
```

### Passing event handlers as props

```javascript
function Button({ onClick }) {
  return <button onClick={onClick}></button>;
}

function PlayButton({ movieName }) {
  function handlePlayClick() {
    alert(`Playing ${movieName}!`);
  }

  return <Button onClick={handlePlayClick}></Button>;
}
```

### Event propagation (_Stopping propagation_)

_Event handlers receive an event object as their only argument. By convention, it’s usually called e, which stands for “event”. You can use this object to read information about the event._

```javascript
function Button({ onClick }) {
  return (
    <button
      onClick={(e) => {
        e.stopPropagation();
        onClick();
      }}
    ></button>
  );
}

export default function Toolbar() {
  return (
    <div
      onClick={() => {
        alert("You clicked on the toolbar!");
      }}
    >
      <Button onClick={() => alert("Playing!")}>Play Movie</Button>
      <Button onClick={() => alert("Uploading!")}>Upload Image</Button>
    </div>
  );
}
```

### Preventing default behavior

_Some browser events have default behavior associated with them. For example, a <form> submit event, which happens when a button inside of it is clicked, will reload the whole page by default_

```javascript
<form
  onSubmit={(e) => {
    e.preventDefault();
    alert("Submitting!");
  }}
></form>
```
