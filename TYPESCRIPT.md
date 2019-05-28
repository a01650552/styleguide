# TypeScript

Follow this guide in TypeScript in addition to the JavaScript style guide.

- **Name props and state interfaces in React components as `IProps` and `IState`.** 
> Why? Giving them unique names in each file isn't worth it as they are generally only ever used internally. If you need to use them in multiple places, you can extract a named type into another file.

- **Prefer keyword (destructuring) arguments** when you have arguments that are booleans and/or don't have an obvious order. This can be annoying to do in TypeScript, but you can type the arguments using an interface defined in the same file as the function.
> Why? Keyword arguments make it easier to understand a function call without looking up the original function.
```typescript
// bad - will just be a string of true/falses when called, hard to understand
export function parseBBCode(code: string, parseEmoji: boolean, parseLinks: boolean, allowHTML: boolean) 

// good - using keyword arguments
interface BBCodeParserOptions {
  parseEmoji: boolean;
  parseLinks: boolean;
  allowHTML: boolean;
}

export function parseBBCode(code: string, { parseEmoji, parseLinks, allowHTML }: BBCodeParserOptions)
```
