## 海哥学习react基础

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
