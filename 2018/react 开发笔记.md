# react 开发笔记
## `forwardRef`

### 例子

```jsx
const FancyButton = React.forwardRef((props, ref) => (
  <button ref={ref} className="FancyButton">
    {props.children}
  </button>
));

// You can now get a ref directly to the DOM button:
const ref = React.createRef();
<FancyButton ref={ref}>Click me!</FancyButton>;
```

Here is a step-by-step explanation of what happens in the above example:

1. We create a React ref by calling `React.createRef` and assign it to a ref variable.
2. We pass our ref down to `<FancyButton ref={ref}>` by specifying it as a JSX attribute.
3. React passes the ref to the `(props, ref) => ...` function inside forwardRef as a second argument.
4. We forward this ref argument down to `<button ref={ref}>` by specifying it as a JSX attribute.
5. When the ref is attached, `ref.current` will point to the `<button>` DOM node.

#### 参考

- 官方文档 [Forwarding Refs – React](https://reactjs.org/docs/forwarding-refs.html)
- [React Refs with TypeScript – Martin Hochel – Medium](https://medium.com/@martin_hotell/react-refs-with-typescript-a32d56c4d315)


#编程/前端