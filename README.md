# BuddyTreeQuestions

1.  **What is a closure? What does it allow you to do?**

    Closures are functions that have access to the outer (enclosing) function's variables—scope chain even after the outer function has returned.

    Here is an example that explains the concept of closure:

        function welcomeCustomer() {
        var customerName = "John";
        function greetingMsg() {
        console.log("Hi! " + customerName); // Hi! John
            }
        welcomeCustomer();
        }

    In the above code we can see that greetingMsg() has access to the variable customerName that is declared in the outer function welcomeCustomer().

2.  **What is micro-frontend architecture?**
    I have not worked on any micro front end applications.As per the knowledge from my peers,Micro-frontend architecture is a design approach in which a front-end app is decomposed into individual, semi-independent “microapps” working loosely together.
    **The Advantages of Microfront end architechture are:**
    a.Micro-frontend architectures may be simpler, and thus easier to reason about and manage.
    b.Independent development teams can collaborate on a front-end app more easily.
    c.They can provide a means for migrating from an “old” app by having a “new” app running side by side with it.

    **The disadvantages are:**
    a. The option for troubleshooting becomes complex as many logs have to be generated to solve the bug.
    b. It may make the architechture of the application difficult.

3.  **What did useEffect replace in React 16.8?**

    The useEffect hook was introduced in the react version 16.8. useEffect can be considered as a combination of componentDidMount, componentDidUpdate, and componentWillUnmount from React class lifecycle.
    The useEffect runs every time after first render and each time after update
    Here is an example code for useEffect hook:

    ```import React, { useEffect } from "react";
    const UseEffectExpln = () => {
    const [value, setValue] = useState(0);
    useEffect(() => {
    console.log('call useEffect');
    if (value > 0) {
    document.title = `New Messages(${value})`;
    }
    });
    return (
    <>
    <h1>{value}</h1>
    <button className='btn' onClick={() => setValue(value + 1)}>
    click me
    </button>
    </>
    );
    };
    console.log('render component');
    //Here the hook runs everytime the value gets updated (the component is rerendered)//

    ```

4.  **What's the difference between useMemo and useEffect hook**
    useMemo: React hook that memorizes the output of a function.That is it. useMemo accepts two arguments: a function and a list of dependencies. useMemo will call the function and return its return value.

    useEffect: it accepts the list of dependencies and it is mainly intended for side effects.
    The main difference is that useEffect is intended for side-effects (hence the name), while functions in useMemo are supposed to be pure and with no side-effects.

5.  **What's the difference between call() and apply()?**
    **call()**  
    The main purpose of call() is that function/method assigned for one object can be reused for another object. It helps us to avoid rewriting the function/method again for a diffrent object. Here is an example of call()

    ````function Product(name, price) {
    this.name = name;
    this.price = price;
    }

    function Laptop(name, price) {
    Product.call(this, name, price);
     this.category = 'laptop';
    }

    function Watch(name, price) {
    Product.call(this, name, price);
    this.category = 'watch';
    }
    const laptop = new Laptop('mac', 5); //the arguements are passed one by one/
    const watch = new Watch('rolex', 40);```
    ````

    here the constructor for Product object is defined with 2 parameters name and price.Two other functions, Laptop and Watch, invoke Product, passing this, name, and price.

    **apply()**
    The apply() method calls a function with a given this value and the arguments provided as an array. The only difference is apply takes the argument as an array and call() takes arguement one by one
    Here is an example:

    ```const array = ['a', 'b'];
    const elements = [0, 1, 2];
    ```

    array.push.apply(array,elements);
    console.info(array);

    The output will be :
    ["a", "b", 0, 1, 2]

````

```

```
````
