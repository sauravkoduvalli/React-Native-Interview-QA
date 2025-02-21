<div align="center">

  <img height="60" src="https://img.icons8.com/color/256/react-native">
  <h1>React Native Interview Questions and Answers</h1>

<span>A curated collection of **React Native, Redux, JavaScript, and TypeScript** interview questions with detailed answers. This repository is designed to help junior to senior developers to brush up their knowledge and prepare for technical interviews with confidence. 🚀
</span>

## Topics Covered  
✔ React Native Basics & Advanced Concepts  
✔ Redux & State Management  
✔ JavaScript & TypeScript Fundamentals 

## Contributing 
Feel free to **add more questions, improve answers, or suggest updates** through pull requests.

<em>Feel free to reach out to me!</em> 😀 <br />
<a href="mailto:sauravkoduvalli@gmail.com">Email</a> • <a href="https://www.linkedin.com/in/sauravkoduvalli/">LinkedIn</a>

| If you find this repository useful, kindly give it a star ⭐. Thank you and have fun! 🔥 |
|---|
</div>

<hr />


| Q No |  Questions       |
|-------|------------------|
| 01 | [What is React Native and how it is different from React JS?](#q1-what-is-react-native-and-how-it-is-different-from-react-js) |
| 02 | [Explain the concept of JSX in React Native?](#q2-explain-the-concept-of-jsx-in-react-native) |
| 03 | [Explain React Native architecture?](#q3-explain-react-native-architecture) |
| 04 | [Describe threads used in React Native?](#q4-describe-threads-used-in-react-native) |
| 05 | [What is the importance of JSX expression to have only one root element? How can you handle multiple elements?](#q5-what-is-the-importance-of-jsx-expression-to-have-only-one-root-element-how-can-you-handle-multiple-elements) |
| 06 | [What are the two main types of components in React Native?](#q6-what-are-the-two-main-types-of-components-in-react-native) |
| 07 | [What are props in React Native components, and how are they used?](#q7-what-are-props-in-react-native-components-and-how-are-they-used) |
| 08 | [What is state in React Native components, and how is it different from props?](#q8-what-is-state-in-react-native-components-and-how-is-it-different-from-props) |
| 09 | [Explain the component lifecycle methods in class components?](#q9-explain-the-component-lifecycle-methods-in-class-components) |
| 10 | []() |
| 11 | []() |
| 12 | []() |

<br />
<hr />

## Q1. What is React Native and how it is different from React JS?

### Overview
React JS and React Native are both developed by Meta and both uses JavaScript, but they serve different purposes. React JS is a JavaScript library for building web applications, while React Native is a framework for building native compiled mobile applications for iOS and Android platforms. The use of JSX, state, props, and React Hooks further reinforces their similarities.

**Library**: A collections of functions that other programs can use. They are often used to control program flow. </br>
**Framework**: A set of pre-written code that provides a structured environment where developers follow predefined rules and use existing components to build their application. 


### Key Differences
- **Platform**: React JS is used for web applications, whereas React Native is used for mobile applications.
- **Rendering**: React JS renders UI using HTML and CSS in web browsers, while React Native uses native components such as `<View>`, `<Text>`, and `<Image>`.
- **Styling**: React JS relies on standard CSS, while React Native supports a subset, only Flexbox layout.
- **Navigation**: React JS uses URL-based navigation (React Router), whereas React Native suggests React Navigation.
- **Performance**: React Native provides better performance on mobile by using native modules, while React relies on the virtual DOM for web rendering.

[⬆ Back to Top](#react-native-interview-questions-and-answers)

## Q2. Explain the concept of JSX in React Native?
`JSX (JavaScript XML)` is a syntax extension that allows to write UI components in a syntax similar to HTML. In React JS, JSX is used to create virtual DOM elements that render as HTML in the browser. In React Native, it renders native mobile UI component instead of HTML elements. JSX makes code more readable, maintainable, and it allows `curly braces {}` to embed JavaScript expressions within UI.

[⬆ Back to Top](#react-native-interview-questions-and-answers)

## Q3. Explain React Native architecture?
<em>Will update the answer👨‍💻</em>

[⬆ Back to Top](#react-native-interview-questions-and-answers)

## Q4. Describe threads used in React Native?
React Native runs on multiple threads to efficiently manage UI updates, JavaScript execution, and layout calculations. It primarily uses three core threads and additional supporting threads for specific tasks. </br>
1) **JavaScript Thread**: This thread executes the JavaScript code related to React components and business logic. 
2) **Main/UI thread**: This is the primary thread responsible for rendering the user interface, handling user interactions, animations and updating the screen directly. 
3) **Background/Shadow thread**: Reponsible for performing long-running tasks, such as network requests, image processing, without blocking the JS thread and UI thread.
4) **Native Modules Thread**: Runs native module operations in Java/Kotlin (Android) or Objective-C/Swift (iOS) to offloads work from the JS thread.
5) **Networking Thread**: Handles API requests and responses for fetch/axios or native networking modules.
6) **Hermes Bytecode Thread (if using Hermes)**: Optimizes JavaScript execution and garbage collection. Runs on Hermes Virtual Machine. Inside `android/app/build.gradle` file, add `enableHermes: true` and rebuild the app. </br>

| Thread             | Purpose                                                | Common Issues                                  | Optimization Tips                                     |
|--------------------|--------------------------------------------------------|-------------------------------------------------|------------------------------------------------------|
| JavaScript Thread  | Runs JS logic, state updates, event listeners          | Blocking operations can freeze UI               | Use background threads for heavy computations        |
| UI Thread (Main Thread) | Handles UI rendering, gestures, animations        | Slow UI if overloaded                           | Optimize re-renders, use `useMemo()`                 |
| Shadow Thread      | Computes layouts using Yoga Engine                     | Complex layouts can slow rendering              | Minimize nested flex layouts                         |
| Native Modules Thread | Runs platform-specific code in Java/Kotlin/Swift    | Poorly written modules can crash the app        | Optimize native module implementations               |
| Networking Thread   | Manages API calls (fetch, axios)                      | Too many requests slow down performance         | Implement caching & debounce API calls               |
| Hermes Bytecode Thread | Optimizes JS execution (Hermes engine)             | Not available on iOS                            | Enable Hermes for better performance (Android only)  |

[⬆ Back to Top](#react-native-interview-questions-and-answers)

## Q5. What is the importance of JSX expression to have only one root element? How can you handle multiple elements?
JSX is ultimately transformed into JavaScript function calls. These function calls need to return a single value. Therefore, a JSX expression must have one root element. To return multiple elements, wrap the JSX children components in a single containing element, That is, `<View>` component, but this adds an extra node to the DOM. A better option is to use React's `<Fragment>` component (or the shorthand <></>) which groups elements without adding an extra DOM node.

[⬆ Back to Top](#react-native-interview-questions-and-answers)

## Q6. What are the two main types of components in React Native?

Components are the building blocks of React Native applications. They promote code reusability, make code more organized, and make it easier to manage complex UIs. There are 2 typs of components in React Native.
1) **Class Components**: Class components are ES6 classes that extend `React.Component`. They have a `render()` method that returns JSX and manage state using `this.state` and `this.setState()`. Before Hooks, they were the only way to manage state and lifecycle methods (`componentDidMount`, `componentDidUpdate`). However, they are more complex and less commonly used in modern React Native development.
   
    ```typescript
    class Greeting extends React.Component {
      render() {
        return <Text>Hello, {this.props.name}!</Text>;
      }
    }
    ```
2) **Functional Components**: Functional components are JavaScript functions that return JSX elements. They uses `React Native Hooks` to manage state and life-cycle behavior. They improve performance because they do not require an instance creation, reducing memory consumption and preffered way to create components in modern React Native applications.

   ```typescript
   const Greeting = ({ name }) => {
     return <Text>Hello, {name}!</Text>;
   };
   ```

[⬆ Back to Top](#react-native-interview-questions-and-answers)

## Q7. What are props in React Native components, and how are they used?

Props (short for properties) are a way to pass data from a parent component to a child component. They are immutable, meaning the child component cannot change them. Props are used to customize the appearance and behavior of a component. For example:

  ```typescript
  // Parent component
  <MyComponent name="Alice" />

  // Child component
  const MyComponent = (props) => {
    return <Text>Hello, {props.name}!</Text>; // Accessing the prop
  };
  ```

[⬆ Back to Top](#react-native-interview-questions-and-answers)

## Q8. What is state in React Native components, and how is it different from props?

State is data that is managed within a component. Unlike props, which are passed down from parent components, state is owned and controlled by the component itself. State can change over time, and when it does, the component re-renders. This is how components become dynamic. Props are immutable; state is mutable.

[⬆ Back to Top](#react-native-interview-questions-and-answers)

## Q9. Explain the component lifecycle methods in class components?

Life cycle methods are functions called at specific stages of a component's existence. These stages are typically referred to as "Mounting", "Updating", and "Unmounting" phases and each phase has specific lifecycle methods.

### Key Lifecycle Methods
1) **Mounting Phase**: 
   Initital Phase when a class component is initialized and added to the UI.
   
   - **Constructor()**: This is the first method executed when the component is created. Used to initialize state and bind event handlers.
   - **static getDerivedStateFromProps(props, state)**: This method synchronizes state with props before rendering. It runs before render() and is rarely used.
   - **render()**: This method is required in every class component. It returns JSX to render the UI.
   - **componentDidMount()**: Runs after the component is mounted (i.e., after the first render()). Used for API calls, event listeners, and timers.
     
3) **Updating Phase**:
   This phase occurs when the component updates due to state or props changes.
   
   - **shouldComponentUpdate(nextProps, nextState)**: Determines whether the component should re-render. Returns true (default) to allow re-render or false to prevent it.
   - **render()**: Called again when state or props change.
   - **getSnapshotBeforeUpdate(prevProps, prevState)**: Runs before the DOM updates and can capture information. Returns a value that is passed to `componentDidUpdate()`.
   - **componentDidUpdate(prevProps, prevState, snapshot)**: Runs after the component updates (re-renders). Used for network requests, animations, and syncing with external systems.
     
4) **Unmounting Phase**:
   When a component is about to be removed, this method runs.
   
   - **componentWillUnmount()**: Cleans up event listeners, timers, or network requests.

[⬆ Back to Top](#react-native-interview-questions-and-answers)
