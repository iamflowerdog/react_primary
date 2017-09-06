## 海哥学习react

#### JSX

* JSX允许直接在模版插入javascript变量。
    如果这个变量是个数组，则会展开数组的所有成员

#### 组件

1. 组件标签必须大写
2. 所有的组件必须有自己的render方法，用于输出组件
3. 组件类必须只能包含一个顶层标签否则也会报错

#### React.Children

1. this.props 对象的属性和组件的属性一一对应，但是也有一个例外，
2. this.props.children 表示组件的所有子节点
3. this.props.children 有三种可能：
     * 没有子节点，undefined
     * 一个子节点，数据类型 object
     * 多个子节点，数据类型 array
4. react提供一个工具方法，React.Children 来处理this.props.children
5. 我们可以用 React.Children.map 来遍历子节点，不用担心数据类型是undefined 或者 object
 
#### this.props 和 this.state 区别？
1. 二者都可以描述组件的特性
2. this.props 写在组件实例标签的属性上面，一般用于保存一些固定的特性值，不再更改
3. this.state 写在组件 getInitialState 方法的返回值里面，保存着用户互动经常产生变化的特性

#### this.setState
1. React的性能模型：每个setState都会重新渲染整个子树；
2. React的一大创新，就是将组件看成一个状态机，一开始有个初始状态，然后跟用户互动，导致状态变化，从而触发重新渲染UI;
3. getInitialState 方法用于定义初始状态，也就是一个对象，这个对象可以通过 this.state 属性读取；
4. 用户和组件交互，导致状态变化，this.setState 方法就是修改状态值，每次修改自动调用 render 方法，再次渲染组件
5. 如果要压缩性能，请将setState调用尽可能低，并使用shouldComponentUpdate来防止重新渲染大型子树；

#### 动态显示表单输入数据要点
1. 表单输入过程中，会触发 onChange 事件 ，
2. 事件对象会自动输入回掉函数的形参里面 `event`
     ```
        event: 触发事件
        dispatchConfig: {…}, _targetInst: ReactDOMComponent,
        nativeEvent: InputEvent,
        type: "change", target: input, …
     ```
3. 通过 event.target 获取触发事件的元素, event.target.value 获取元素的输入值

     `event.target = <input type="text">`
     
     `event.target.value = 表单输入值`


#### 组件生命周期的三种状态：
 1. Mounting : 已经插入真实DOM
 2. Updating: 正在被重新渲染
 3. Unmounting: 已经移除真实DOM
 
#### 三种状态 五种处理函数
 * componentWillMount()
 * componentDidMount()
 * componentWillUpdate(object nextProps, object nextState)
 * componentDidUpdate(object prevProps, object prevState)
 * componentWillUnmount()
 
#### 两种特殊状态的处理函数
 * componentWillReceiveProps(object nextProps)：已加载组件收到新的参数时调用
 * shouldComponentUpdate(object nextProps, object nextState)：组件判断是否重新渲染时调用
 
#### 重新渲染注意事项
 * 必须在页面挂载后，才能更改样式，否则看不到变化
 * 在 componentDidMount 中输出 只会打印一次
 * 在 组件中 设置定时器， 记得给定时器传的回掉函数指定 this 为 当前组件实例 否则 this 指向 window
 * 要更改初始化数据的value值，记得先给value值保存，保存后的变量值做动态修改，然后调用setState修改
 * 另外组件渲染时候 样式 放在大括号里面 不应该写成字符串

#### 
 

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 