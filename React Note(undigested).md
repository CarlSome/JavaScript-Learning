# Note

- super方法：
  在JS中，每次定义子类的构造函数时，都需要调用super方法。因此，在所有含有构造函数的React组件中，构造函数必须以super(props)开头
  
```
class Square extends React.Component {
constructor(props) {
  super(props);
  this.state = {
    value: null,
  };
}
```

- 数组复制：
```
// 错误方法：只会让array2指向array1的指针，没有完成“复制”
const array1(9).fill(1);
const array2 = array1;

// 正确方法：使用slice()或其他拷贝函数
const array2 =  array1.slice();
```

- setState()
  - 形式1：
  ```
  // updater为函数
  setstate(updater[, callback])
  
  // 下为带参数的updater函数
  (state, props) => stateChange
  
  // 使用示例
  this.setState((state, props) => {
    return {counter: state.counter + props.step};
  })
  ```
  - 形式2：
  ```
  // stateChange为传入的对象
  setState(stateChange[, callback])
  
  // 使用实例
  this.setState({quantity: 2})
  ```
形式1、2中的[]并不是表示数组的意识，而是可选的意思——可以选用callback函数，如:
```
setState(updater, callback);
```
使用callback是为了立即完成setState的数据更新。一般而言，如果没有callback的话，setState后的数据一般不会立刻更新，而是在下一轮渲染时更新。这样的话，如果setState后马上读取state的值的话容易读到错误的值。
