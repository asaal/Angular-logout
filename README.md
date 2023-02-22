# Angular-logout

To implement a feature where the user is logged out when the tab is closed, but not when the page is refreshed, you can make use of the window object's beforeunload event.

Implementation using Angular:

Create an AuthService to handle the authentication status of the user.
In your app component or a top-level component, listen for the beforeunload event and call the logout method of your AuthService.
The @HostListener decorator listens for the beforeunload event on the window object and calls the unloadHandler method. 
In the unloadHandler method, we call the logout method of our AuthService
In your login component, call the login method of your AuthService when the user logs in.
With this implementation, when the user logs in, the isLoggedIn property of the AuthService is set to true. 
When the user closes the tab or navigates away from the page, the beforeunload event is fired and the unloadHandler method is called, 
which calls the logout method of the AuthService, setting isLoggedIn back to false.
However, if the user refreshes the page, the unloadHandler method is not called, and the AuthService state remains unchanged.
