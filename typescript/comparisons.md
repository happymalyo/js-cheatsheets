## Unknown vs Any
**unknown** is the parent type of all other types. it's a regular type in the type system. <br/>
**any** means "disable the type check". it's a compiler directive.
```js
// ANY
const anyValue: any = 'folish_hacker'
// OK in TypeScript (error in runtime!) 👇
anyValue.do.something.stupid() 
// UNKNOWN
const unknownValue: unknown = 'whatever, too'
// Fails TypeScript check (prevents runtime error) 👇
unknownValue.do.something.stupid()
```
