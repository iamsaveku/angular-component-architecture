# Angular Base Component Architecture.

# Question

Consider a scenario wherein you have to develop a UI dashboard application having many widgets on the page. And Each widget can show different data from the server, but at any point in time each widget will be in one of the four states and they are Data, No-Data, Loading and Error state. So, how to design this application?

# Answer

I would try designing the application with a base component. A base component will hold the loading, no-data and error state of the widget. So that we can reuse the base component as a wrapper to any kind of component and handle the states in a better way.

To test this architecture pattern, please clone this repo and run the angular application. We can reuse this pattern for any kind of component project. That is, we can use this idea in designing our React, Vue or Web component projects.

# Project Setup

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 8.3.23.

1. Git clone `https://github.com/iamsaveku/angular-base-component-architecture.git`
2. Goto cloned location and open the command prompt.
3. `npm install`
4. `ng build`
5. `ng serve`
6. Navigate to `http://localhost:4200/`.

# Application.

After loading the demo application you will see all the below widgets changing its state every 3 seconds. Each widget will show only one state at a particular time.

![Image of Dashboard](readme-assets/dashboard.png)

As you can see, we have three widgets on the screen with each in its state and color. Widget 1 showing no-data, widget 2 showing error and Widget 3 showing loading component.

And the code to handle the same in angular is as below. We have used the same base component `app-base` as a wrapper for our three widgets Widget1, Widget2, and Widget3 so that it can handle the respective widgets loading, error, and no-data state. If the data comes from the server it will show the widget wrapped inside the base component else it will show other states based on the server response.

![Dashboard Angular Code](readme-assets/dashboard-code.png)

As you can see below, we created an error, loader, and no-data as a separate component but using the inside base component. Because of the `ng-content` directive, we can show the content of widget 1, 2 and 3 inside the base component as shown above with a yellow border. The logic for showing different component states will be handled in the base component.

![Base component](readme-assets/base.png)

By this, we can reuse the base component in multiple widgets of our application with a generic loader, no-data and error component to make it consistent across the application.

# Improvements
Instead of directly writing the error, no-data and loader directive inside the base component HTML, in Angular we can dynamically inject the respective component from base component .ts file. I hope you will take it as a challenge and implement it.

# Licence
MIT


> The day you stop learning, you stop earning ~ @iamsaveku
