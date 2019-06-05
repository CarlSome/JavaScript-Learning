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
