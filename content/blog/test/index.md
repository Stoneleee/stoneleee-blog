---
title: Test content111
date: "2019-06-10T22:40:32.169Z"
tags: ['2019']
disqus: true
---

### 旧生命周期(v16.0前) | 新生命周期(v16.0后)

---|---

constructor(props)     | constructor(props)

componentWillMount     | ---

componentWillReceiveProps  | ---

componentWillUpdate     | getDerivedStateFromProps(nextProps, prevState)

shouldComponentUpdate    | shouldComponentUpdate(nextProps)

render           | render

---             | getSnapshotBeforeUpdate(prevProps, prevState)

componentDidUpdate     | componentDidUpdate(prevProps, prevState, snapshot)

componentDidMount      | componentDidMount

componentWillUnmount    | componentWillUnmount

---             | componentDidCatch





1、父组件render，传入子组件props，无论props是否改变，都会引起子组件的重新渲染，可用shouldComponentUpdate判断是否需要重新渲染，优化性能。



2、componentWillUnmount做一些清理工作，比如清除定时器，清除在componentDidMount中手动创建的DOM元素等。



3、为什么数据请求放在componentDidMount里面更好一点：

1),在服务器渲染时,如果在 componentWillMount 里获取数据，fetch data会执行两次，一次在服务端一次在客户端，这造成了多余的请求.2),在React 16进行React Fiber重写后,componentWillMount可能在一次渲染中多次调用,原因是render之前的生命周期可以被中断



4、pureComponent的作用以及使用陷阱：（pureComponent会自动比较props,state,如果没有改变，则不会重新渲染）



[https://www.jianshu.com/p/33cda0dc316a](https://www.jianshu.com/p/33cda0dc316a)



5、



6、



### Vue优于React:

\1. 最新文档和更简单的语法。

\2. 更小，更快，更灵活。

\3. 丰富的HTML模板，易于开发。



### React优于Vue:

\1. 需要构建移动应用程序。

\2. 专业和出色的社区支持，以解决任何问题。

\3. 需要构建大型应用程序。

\4. 轻量级，易于版本迁移。



Vue | React

---|---

如果您想要一个轻量级，更快速，更现代的UI库来制作一流的SPA（单页面应用程序），您应该选择Vue.js. 对于习惯使用HTML的开发人员来说，这是有利的。此外，它还提供了组件的可重用性，使其成为开发人员在Web应用程序中构建无与伦比的用户体验的选择。 | 当你是JavaScript的粉丝！React拥有一个成熟且规模更大的专业开发团队，致力于使其更先进。React由Facebook提供支持，其中包含许多用例，解决方案，资源和项目。此外，由于成熟的用户群，React适用于大规模应用程序和移动应用程序。很明显，如果您想使用JavaScript构建移动应用程序，React Native绝对是您的选择

