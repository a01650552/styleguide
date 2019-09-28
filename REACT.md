# React

Follow this guide in React in addition to the JavaScript and TypeScript style guides.

- **Use React Hooks whenever possible as an alternative to React.Component.**
> Why? Hooks are easier to understand, easier to reuse, and shorter. [Take the time to read the guide](https://reactjs.org/docs/hooks-intro.html), and once you have I recommend using them for all new components. You aren't required to port existing components to hooks. If you're making a massive controller-style component (like ThreadPage, IndexPage), stick with classes, but otherwise go for hooks.

- **When using React.Component, never bind event listeners in the constructor. Use arrow method syntax instead.**
> Why? Unnecessary boilerplate is bad.
```javascript
openModal = () => {
  this.setState({ /* ... */ });
}
```

- **When using React.Component, name event listeners after what they do, not how they are triggered.**
> Why? This makes it easier to identify their purpose when quickly skimming through #render, and especially when the listener is passed as a prop to child components.
```javascript
// Bad
handleClick = () => {

// Good
openModal = () => {
```

- **Write long JSX tags as follows, with one value per line.** This is used for both standalone and inline tags.
> Why? This makes it easier to read while not requiring you to move the closing `>` or `/>` part around if you add new properties at the end. Basically the same reasoning with trailing commas in object literals.
```jsx
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
