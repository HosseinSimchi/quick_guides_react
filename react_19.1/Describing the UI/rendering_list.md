#### _Warning_: Each child in a list should have a unique “key” prop.

```javascript
export default function List() {
  const listItems = people.map((person) => <li key={person.id}></li>);

  return <ul>{listItems}</ul>;
}
```
