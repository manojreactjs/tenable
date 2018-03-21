Tenable - Nessus UI Assessment

1) A server sends the following data when requesting 'http://[yourserver]/download/request?host=2'  :

{
"configurations" : [
     {
        "name" : "host1",
        "hostname" : "nessus-ntp.lab.com",
        "port" : 1241,
        "username" : "toto"
     },
     {
        "name" : "host2",
        "hostname" : "nessus-xml.lab.com",
        "port" : 3384,
        "username" : "admin"
     }
 ]
}

Write an HTML/JS code to send this request and display the result.

I wrote the request code within the handleSubmit function in the NumConfigurationInput component. Since the server doesn't actually exist it always fails, so within the catch clause I just simulate what a request would look like and pretend I got it from the server. I also have a unit test in App.test.js that tests whether the response from the server is what is expected. (It always fails).

2) Use jQuery to add some style and design to the previous code.

 Since I chose to use React for this application, it didn't really make sense for me to use a whole lot of jQuery. React's declarative style where updating state automatically causes affected components to be rerendered makes direct DOM manipulation pretty much unnecessary. I created a HeaderCaseToggle component that let the user toggle the case of the table headers dynamically using jQuery.

3) Add some CSS design/style
 
Done 

4) Use the React framework and any additonal JavaScript libraries in the React ecosystem that you want and/or like to show us your skills on this small web application.
 Find In readme file

5) instead of sending host=2 you now send host=10000 and the response contains 10000 fields. How would you handle that? What could be improved to get the best performance?


optimized for this by implementing lazy loading via the react-virtualized library. I have a table that contains all of the configurations, but it only renders the rows that are visible on the screen at any given time. If I wanted to further improve the performance, I could've implemented server-side pagination. Basically I would impose an upper limit on the amount of configurations that could be returned from the server at any given time. (For ex:, each request can return a max of 1000 configs). Then I would add an event that when someone scrolls to the bottom of the list, I query the server and see if there are more configs below the bottom one they've seen. If there are, I would add the next set of configs to the app state.
