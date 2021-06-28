# Day 13

## Spotify: Application state using redux - Part 1

- On [Day 11](https://github.com/exponentsoftware/FDOC_FE_11) we have created signin component to create the authentication flow. We have also made few routes private so that user can't access these unless they have logged in.   
  For that we may have store the login details in the `App` component, but this will complex to share these details among multiple components once the DOM tree level increases.  
  To avoid that let's create an application state with the help of `redux` so that the data can be shared across multiple components easily
- Create a `store` in the `index.js` file and provide it to the root component
- Before creating state you have to create `reducer` with two `actions` as follows: 
    - `LOGIN`: Add user details in the state when triggered
    - `LOGOUT`: Delete user details in the state when triggered
- We have store and reducer in place not it's time to dispatch an action.  
  When user clicks on Signin button in the `Signin` component dispatch the `LOGIN` action along with the payload to the reducer. The `LOGIN` action may look like below  
  ```js
   const loginAction = {
       type: "LOGIN",
       payload: <userdetails>
   }
  ```
- Create a Logout button somewhere in the navigation and dispatch `LOGOUT` action when user clicks on it. `LOGOUT` action may look like as below  
  ```js
   const logoutAction = {
       type: "LOGOUT"
   }
  ```