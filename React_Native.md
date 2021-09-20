-----------------------------------------------------------------------------
# JK-Tech 3-spt-21
--------------------
- Differnace between React and React-Native.
- Differnace between State and Props.
- Advantages of React and React-Native.
- Difference between Virtual dom and shadow dom? [+]
- How Doms work in React-Native. [+]
- Difference between Class and Function components?
- What is Interaction Manager.
- Pure component.
- Hot reloading and live relaoding. [+]
- HOC, why we need
- Redux
- AsyncStorage
- Fetch API implementaions with POST, GET and Paramas
- what is ref and id?
- Things to take care for App security.
- What is AppRegistery, Index.js, App.js, Package.json files, what these files do ?
-----------------------------------------------------------------------------





1. React native architecture (shadow thread, JavaScriptcore)
2. Components 
3. Props and state.
4. Life cycle of component. (which methods are deprecated and why).
5. Redux and flux, store.
6. Pure component. (do shallow comparision by It does this by iterating on the keys of the objects being compared.)
7. Navigation and routing 
8. react latest version and changes from last version.
. What is Fabric.  The new architecture is codenamed Fabric and would allow React Native to perform high priority UI updates in a synchronous manner. This means the UI would be more responsive.
9. arrow function.
10. Async and await. (alternate to promise, no need to add catch with every promise. clear code. Otimized error handling ) https://blog.pusher.com/promises-async-await/
11. Async storage.
12. ES6 changes and improvement.
13. Make a component for react native and export it to react to use.
14. Communication from react native to native and vice versa.
15. java script engine v8 engine of microsoft.
16. what is JSX. (Add XML syntex to Java script)
17. difference between Button,touchableHighlite, Touchable opacity. (Low priority)
18. Async and await.
19. Component Life cycle method componentWillMount() and componentWillReceiveProps() are depracated WHY ?.
20. arrow function performance in render menthod. arrow function best practices.
21. promise. (USED FOR ASYNC CALLING, its have 2 state ) 
22. Context for passing info to child.    "https://hackernoon.com/everything-you-need-to-know-about-reacts-context-api-e5c8c32ef202"
23. Redux Thunk.  
24. Closure "A closure is a function having access to the parent scope, even after the parent function has closed."
25. Function pointer.
26. prototype (works as same as static method in java. supports inheritance in JS). When a certain method(or property) is called, it first checks inside the object but when it doesn’t find, then search moves on Object’s prototype.

defining the prototype:- Person.prototype.calculateAge= function(){ 
    console.log('The current age is: '+(2019- this.yearOfBirth)); 
} 

27. Higher Order Function.
28. What is babel. (Babeljs is a configurable transpiler, a compiler which translates from Javascript to Javascript unlike a compiler which translates high level application code into lower level code or binaries. The babel team implemented various plugins to compile React's JSX to `React.createElement` In short - it allows you to use language features “from the future”. It does so by transpiling your code to the currently supported version of JavaScript.)
28:- alternate of balel.

29. function component.
31. Stateless component.
30. Uses of Force Update.
32. Use of key in flat list.
33. Recoincelation in react native.
33. Diffing process, How its works.
34. How to compare two objects in JS.
35. Curring :- Currying is the process of turning a function with multiple number of parameter into a function with less number of parametres.
36. react memo
37. react fragments. in which condition use fragments.
38. profiler in android and react.
39. Difference between .bind and arrow =() => function : this, super, and arguments
 .bind() only this is bounded by it.
  arrow:- arrow function binds this, super, and arguments.

34. Redux Thunk vs Saga.
35. Airbnb why left react.
36. different dom trees. which one you will choose in different condition.
37. redux rules:- 
38. Hooks. uses of hooks. React Native 0.59 and above support Hooks.  
Hooks helps you use state and lifecycle methods behavior in functional React components, that is, without writing a class.
useEffect:-  Similar to componentDidMount and componentDidUpdate.

39. can we access store without conncet.

40:- Callback:- It is very important to highlight that the callback is not invoked immediately after the native function completes - remember that bridge communication is asynchronous, and this too is tied to the run loop.
















36. MVC and MVVM design pattern.
37. how animation works in react native.
38. PropTypes in react : https://medium.com/better-programming/prototypes-in-javascript-5bba2990e04b
39. what are call, apply or other methods.
40. generators in es6 
41. uses of yield.
42. Saga vs thunk.
43. what is callback 

Thinksys:- 

1. difference between map and forin
2. curring
3. prototype
4. return type of bind method.
5. how to compare two objects.
6. refrences.
7. async await
8. arrow function internal working.
9. what bind function returns.

reducer , how reducer identify if state change, reducer



callback, saga, use method of native to react native. 
generators, hooks,




Difference between forEach and Map. 

forEach: This iterates over a list and applies some operation with side effects to each list member (example: saving every list item to the database)

map: This iterates over a list, transforms each member of that list, and returns another list of the same size with the transformed members (example: transforming list of strings to uppercase)


animation working, how its works. scrolling in android.
`

Problem faced:-
  
  1. Https with self signed certificate (Use fetchBlob).
  2. On previous version multiple click on view. 
  3. 

difference between MVC, MVP and MVVM

https://www.linkedin.com/pulse/understanding-difference-between-mvc-mvp-mvvm-design-rishabh-software/

MVC :- Viewcan directly communivate with Model.

MVP: every view has its presenter. This presenter address the events from View and return result back to View. Use interface to communicate.

MVVM: modal => ViewModal => View.

MVVM pattern supports two-way data binding between View and ViewModel. This allows automatic propagation of changes, inside the state of ViewModel to the View. Generally, the ViewModel utilizes the observer pattern to inform changes in the ViewModel to the Model.


Arrow Function:- An arrow function does not have its own this. The this value of the enclosing lexical scope is used; arrow functions follow the normal variable lookup rules. So while searching for this which is not present in current scope they end up finding this from its enclosing scope.




Redux Thunk vs Saga
Type script
proto type : uses: 1) to find properties and methods of an object 2) to implement inheritance in JavaScript.


array funcction , iteration, 
flat list: 
extra data, 
difference between == and ==== in details :=> 
    === is used for comparing two variables, but this operator also checks datatype and compares two values.
     == in JavaScript is used for comparing two variables, but it ignores the datatype of variable.
difference between call and apply
refrences in React
Hoisting : finction and variable can be used before declared. Using ‘JavaScript Hoisting’ method, when an interpreter runs the code, all the variables are hoisted to the top of the original /current scope.

how to achieve clear top functionality in react native : this.props.navigation.navigate('RouteName') pushes a new route to the stack navigator if it's not already in the stack, otherwise it jumps to that screen.
 or this.props.navigation.goBack(route key ) . save route key by this.props.navigation.state.key



Strict mode : Explore for dev purpose.
react-native-screens benefits of it.

UpdateSpace kvj



+ 
map 
promise 
refs



1. Simplifi npm and strecture.
2. Elderly npm overview.
 

boot process in android

Travel Triangle:-
1. code analyzer in react native (ESLint)
2. paraller call for api and return combine result. (Promise.all[] or Promise.allSettled[])
3. How react native bridge works internally.
4. function and timeout.
5. what is action creator.




paraller api call :-

use Promise.ALL 


first 2 call will exexute parallerly.

async componentDidMount() {

  // Make first two requests
  const [firstResponse, secondResponse] = await Promise.all([
    axios.get(`https://maps.googleapis.com/maps/api/geocode/json?&address=${this.props.p1}`),
    axios.get(`https://maps.googleapis.com/maps/api/geocode/json?&address=${this.props.p2}`)
  ]);

  // Make third request using responses from the first two
  const thirdResponse = await axios.get('https://maps.googleapis.com/maps/api/directions/json?origin=place_id:' + firstResponse.data.results.place_id + '&destination=place_id:' + secondResponse.data.results.place_id + '&key=' + 'API-KEY-HIDDEN');

  // Update state once with all 3 responses
  this.setState({
    p1Location: firstResponse.data,
    p2Location: secondResponse.data,
    route: thirdResponse.data,
  });

}


Limitation of React-Native: -

1. if there is some change at native side then NPM should be updated.
2. Developer should have native knowledge.
3. If any available npm library is urelaible or have some issue then we need to write our own npm. in case we need to be expert in android, ios and react-native.
4. Low Security 
5. can not share the memory between js and native thread.
Bridge Serialization
All data has to get serialized into JSON on its way in and deserialized on its way out. This double ser-de pass can be costly for data-intensive problems. It also prevents sharing any memory between native and JS.
6. Single Threadfor java script. JS is single threaded, which means there will always be limitations around doing meaningful work in the JS context.
7. 



Animation working in react native:- https://www.freecodecamp.org/news/how-react-native-animations-work/#:~:text=Well%2C%20simply%20put%2C%20it%20means,like%20repetitive%20taps%20from%20user.


faster Ui response :- use interactionmanager  
InteractionManager allows long-running work to be scheduled after any interactions/animations have completed. In particular, this allows JavaScript animations to run smoothly.

react navigation : - 
NavigationContainer
 add <Stack.Navigator inside
    add <Stack.Screen inside 

Unidirectional Data Flow:-
It is also known as one-way data flow, which means the data has one, and only one way to be transferred to other parts of the application. In essence, this means child components are not able to update the data that is coming from the parent component. In React, data coming from a parent is called props. Angular makes use of bi-directional binding in which the data flow takes place in both directions. React doesn’t support bi-directional binding to make sure you are following a clean data flow architecture. The major benefit of this approach is that data flows throughout your app in a single direction, giving you better control over it.
In terms of React it means:

state is passed to the view and to child components
actions are triggered by the view
actions can update the state
the state change is passed to the view and to child components


topics:-
immutables,
Fragemnts,
react architecture,
controlled components
How to manage different screen sizes. https://medium.com/@shanerudolfworktive/7-tips-to-develop-react-native-uis-for-all-screen-sizes-7ec5271be25c
how to provide images for mdpi, dhpi etc. use images like @2x, @3x, 
How to handle screens for tablet and mobile. https://medium.com/@shanerudolfworktive/7-tips-to-develop-react-native-uis-for-all-screen-sizes-7ec5271be25c
      :- 



React native 63 improveents:- 
Logbox 
    Concise error, Formatted, Actionble(should be actionable)
Log Notification
Code frame
Component stack
Formatted syntax
Collapse error

 Pressable
Native color
Dropping support for iOS 9 and Node js 8

Performance Review: Show Perf Monitor 


Pure software:- 
web workers.
debouncing.
synthetic event. (React only)
optimization in react native , use pure component, functional component, fragments, small Images, use  NativeDriver for Animation
   useMemoHooks(Memoization speeds up computer programs by storing the results of expensive function calls and returning the cached result when the same inputs occur again), useCallback() Hook, 
Merge a nested array.
prototype 
variable hoisting 
closure :-
use of useCallBack 

Web Workers
Web Workers provides an API where we can run a JS code in another thread other than the main thread of script runs in. When we run CPU intensive op in the main thread, we will be greeted by the familiar “unresponsive” script dialog.

Push notification on IOS:-

apns :- Apple push notification server in place of firebase console. app has to register itself on OS for push. 


This is hradesh kumar. I am working as a technical lead in harman connected servives. i have experience in react native, android and aosp. i have 9 yeras of experince. I am handling a team of 10 peoples and following agile practices. i have experince in GPS tracking, chat application, banking domain, entertainment and medical doamin.


git questions:-

if you have a branch and commited some code to another branch and pushed some more commit to that branch then what isyor stretagy to get the changes to correct branch.





https://play.google.com/store/apps/details?id=com.sprint.trebl


have a lokk into IOT and gizbee . 

------------------------------
# Live & Hot reloading 
Live reloading reloads or refreshes the entire app when a file changes. For example, if you were four links deep into your navigation and saved a change, live reloading would restart the app and load the app back to the initial route.

Hot reloading only refreshes the files that were changed without losing the state of the app. For example, if you were four links deep into your navigation and saved a change to some styling, the state would not change, but the new styles would appear on the page without having to navigate back to the page you are on because you would still be on the same page.
------------------------------


5) How many threads run in React Native?
The React Native app contains the following thread:

1. React Native UI Thread (Main Thread): This thread is used for the layout of the mobile app.
2. React Native JavaScript Thread: It is a thread where our business logic will run. It means JS thread is a place where our JavaScript code is executed.
3. React Native Modules Thread: Sometimes, our app needs access to platform API, which happens as a part of native module thread.
4. React Native Render Thread: This thread is used to generate actual OpenGL commands used to draw the app UI.

25) What are Refs in React Native?
React refs are useful features that allow you to access DOM elements or component's instance directly within React. It comes handy in situations where you want to change the child of a component without using props or re-rendering the whole component.


# useEffect (Hooks)
If you’re familiar with React class lifecycle methods, you can think of useEffect Hook as componentDidMount, componentDidUpdate, and componentWillUnmount combined.

# Fetch

-- [ Timeout ]   Fetch() provides functionality through the AbortController interface.
        (Source - https://blog.logrocket.com/axios-or-fetch-api/)
        const controller = new AbortController();
        const options = {
          method: 'POST',
          signal: controller.signal,
          body: JSON.stringify({
            firstName: 'David',
            lastName: 'Pollock'
          })
        };  
        const promise = fetch('/login', options);
        const timeoutId = setTimeout(() => controller.abort(), 4000);

        promise
          .then(response => {/* handle the response */})
          .catch(error => console.error('timeout exceeded'));
        Here, we create an AbortController object using the AbortController.AbortController() constructor, which allows us to later abort the request. signal is a read-only property of AbortController providing a means to communicate with a request or abort it. If the server doesn’t respond in less than four seconds, controller.abort() is called, and the operation is terminated.

-- [ Interceptors ]
        By default, fetch() doesn’t provide a way to intercept requests, but it’s not hard to come up with a workaround. You can overwrite the global fetch method and define your own interceptor, like this:

        fetch = (originalFetch => {
          return (...arguments) => {
            const result = originalFetch.apply(this, arguments);
              return result.then(console.log('Request was sent'));
          };
        })(fetch);

        fetch('https://api.github.com/orgs/axios')
          .then(response => response.json())
          .then(data => {
            console.log(data) 
          });

Live reloading reloads or refreshes the entire app when a file changes. For example, if you were four links deep into your navigation and saved a change, live reloading would restart the app and load the app back to the initial route.

Hot reloading only refreshes the files that were changed without losing the state of the app. For example, if you were four links deep into your navigation and saved a change to some styling, the state would not change, but the new styles would appear on the page without having to navigate back to the page you are on because you would still be on the same page.

4. Differences between Shadow DOM and Virtual DOM
The only thing which is common for both is that they help with performance issues. Both create a separate instance of the Document Object Model; besides this, both concepts are different. Virtual DOM is creating a copy of the whole DOM object, and Shadow DOM creates small pieces of the DOM object which has their own, isolated scope for the element they represent.

---- T O  D O 

> Promise
> Callbacks
> 


10) Define Destructor?

A destructor is a method which is automatically called when the object is made of scope or destroyed. Destructor name is also same as class name but with the tilde symbol before the name.


 
