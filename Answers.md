## Questions - Self Study - You can exercise your Google-Fu for this and any other _Sprint Challenge_ in the future.

1.  Name 3 JavaScript Array/Object Methods that do not produce side-effects? Which method do we use to create a new object while extending the properties of another object?
Object.assign() is a method that creates a new object while extending the props of another object.  It makes a 'deep copy'.  Other methods that do not produce side-effects are filter(), concat(), and map().

2.  Describe `actions`, `reducers` and the `store` and their role in Redux. What does each piece do? Why is the store known as a 'single source of truth' in a redux application?
Reducers define the store and give the direction on what to do with various actions.  Actions define what may happen in the app and call the different actions defined in the reducer.  The Store is the state which is available to all parts of the app connected to the store.  The store is known as a 'single source of truth' because it is (possibly) connected to the entire app.   

3.  What is the difference between Application state and Component state? When would be a good time to use one over the other?
Application state is just presentational.  It is best to use this type if you're not interacting with the store. Component state has access to the store and it best to use if you need to interact with the store.

4.  What is middleware?
Middleware gets between the action and redux.  It allows a delay in action, which redux doesn't allow by default.  

5.  Describe `redux-thunk`, what does it allow us to do? How does it change our `action-creators`?
Redux-thunk is a middleware.  It gives us access to dispatch and lets us call it whenever we want.  This allows us to receive data and then chose when to change state via the action-creators.  By default, redux would do this asap, but when awaiting input from a server/api, there may be a delay that could cause an error in your app - this is why thunk is needed.  
6.  Which `react-redux` method links up our `components` with our `redux store`?
Connect

1. (Stretch goal question for if you get the DELETE endpoint working) The server's DELETE endpoint functionality is not optimal, since it requires you to either make a second `getSmurfs` request to fetch the updated list of Smurfs after deletion, or you need to keep two sources of truth synchronized, one in the client and one in the server. What change would you propose to make the server DELETE functionality more optimal such that either of these two issues are not encountered?