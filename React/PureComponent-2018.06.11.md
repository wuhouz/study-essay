# React.PureComponent
 - `React.PureComponent` 与 `React.Component` 几乎完全相同，但 `React.PureComponent` 通过 `prop` 和 `state` 的浅对比来实现 `shouldComponentUpdate()` 。
 - 如果`React` 的`render()` 函数在给定相同的props和state下渲染为相同的结果，在某些场景下你可以使用`React.PureComponent` 来提升性能
 - `React.PureComponent` 的 `shouldComponentUpdate()` 只会对对象进行浅对比。如果对象包含复杂的数据结构，它可能会因深层的数据不一致而产生错误的否定判断（表现为对象深层的数据已改变视图却未更新）。当你期待只拥有简单的props和state时，才去继承`PureComponent`, 或者，考虑使用 不可变对象 来促进嵌套数据的快速比较。
此外,React.PureComponent 的 shouldComponentUpate() 会忽略整个组件的子级。请确保所有的子级组件也是”Pure”的。