I'm creating this style guide to standardize conventions in all our projects from now on. It will primarily focus on JavaScript/TypeScript code. You are free to open an issue or mention any changes in Discord.

- Dakota

# JavaScript

Follow the [AIRBNB JavaScript style guide](https://github.com/airbnb/javascript). I'll summarize the basic points below and any changes specific to PC styles.

- **Use two spaces for indentation.** Four spaces are banned. Tabs are especially banned.
> Why? This is the standard for most modern JS code and most of our team uses this already.

- **`var` is banned.** Always prefer `const`, or `let` if you may be reassigning something. If you need to assign a value in a conditional, declare the variable first.
> Why? `var` has scoping issues that makes it easy to introduce subtle bugs.
```javascript
// bad - one line shorter, but using var is a no-no
if (something) {
  var x = 'something'; 
} else {
  var x = 'somethingElse';
}

// good - couldn't use const here, so let is best
let x;
if (something) {
  x = 'something';
} else {
  x = 'somethingElse';
}
```

- **Use trailing commas on multiline arrays and objects.**
> Why? Better diffs on GitHub.

- **Use spaces around the inside of one-line object literals.**
```javascript
const user = { username: 'hackdeoxys' };
```

- **Use the shorthand syntax for matching a key with a variable name whenever possible.**
```javascript
// bad
this.setState({ text: text });

// good
this.setState({ text });
```

- **Use destructing when possible.**
```javascript
// bad
const text = this.state.text;

// good
const { text } = this.state;
```

- **Never use string concatenation.** Use template strings with `${}` syntax instead.