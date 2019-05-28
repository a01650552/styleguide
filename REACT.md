# React

Follow this guide in React in addition to the JavaScript and TypeScript style guides.

- **Never bind event listeners in the constructor. Use arrow method syntax instead.**
> Why? Unnecessary boilerplate is bad.
```javascript
openModal = () => {
  this.setState({ /* ... */ });
}
```

- **Name event listeners after what they do, not how they are triggered.**
> Why? This makes it easier to identify their purpose when quickly skimming through #render, and especially when the listener is passed as a prop to child components.
```javascript
// Bad
handleClick = () => {

// Good
openModal = () => {
```

- **Write long JSX tags as follows, with one value per line.** This is used for both standalone and inline tags.
> Why? This makes it easier to read while not requiring you to move the closing `>` or `/>` part around if you add new properties at the end. Basically the same reasoning with trailing commas in object literals.
```javascript
<Page
  name="Thread"
  loading={!this.state.thread}
  banner={this.state.thread && this.getBanner()}
  breadcrumbs={this.state.thread && this.getBreadcrumbs()}
  htmlTitle={this.getHtmlTitle()}
>
  {/* ... */}
</Page>
```
