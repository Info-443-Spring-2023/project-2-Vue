# Vue Router
A robust routing framework created specifically for Vue.js applications is called Vue Router. It has a thorough routing system and effortlessly interacts with Vue.js, a progressive JavaScript framework for creating user interfaces.Developers may quickly associate URLs with various components using Vue Router, allowing dynamic and responsive Single-Page Applications (SPAs). It enables developers to design contemporary web applications with fluid navigation and user experiences by supporting features like nested routes, lazy-loading routes, and parameter passing.

## Context and Background
Vue CLI( Vue Command Line) is a development tool that aims to simplify and streamline the process of creating, managing, and building Vue.js projects. The Vue.js is a progressive JavaScript framework for building approachable, flexible, and efficient user interfaces. Through a command-line interface, the CLI is a tool that enables developers to communicate with the Vue ecosystem, and provides various commands and features to scaffold new projects, configure project settings, run development servers, and optimize and build projects for production. Vue Router was developed to address the need for a robust routing system within Vue.js applications. It provides a way to map URLs to different views or components, allowing users to create dynamic and responsive Single-Page application. As we doing this project, we mainly focus on the plugins and extensions as it recommends.

## Development View
The development view analyzes the component-level structure of Vue Router, identifying the major modules and their dependencies. The below section offers an overview of the system's components, their organizations, and interactions.
#### System Components
The source code needs to be analyzed to understand the component-level architecture of the Vue Router. The source code analysis will also help in understanding the components of the system. Discussed below are the components of the Vue router repository:

#### Dependencies
The component-level architecture also includes dependencies within and outside the system. Vue Router relies on the Vue.js framework as a foundational element. Vue Router relies on the Vue.js framework to integrate routing functionality seamlessly into Vue.js applications. It leverages Vue.js's reactive data-binding, component composition, and virtual DOM capabilities to enable dynamic and responsive single-page applications. Vue Router extends Vue.js by providing a routing system that maps URLs to different views or components, facilitating the creation of a smooth and intuitive user experience. In addition to its dependence on the Vue.js framework, Vue Router also has dependencies on external libraries or modules that enhance its functionality. These dependencies include libraries for handling authentication, managing state or providing additional features and utilities. Vue Router can offer a more comprehensive and feature-rich routing solution for Vue.js applications by leveraging these external dependencies.
#### Source Code Structure
The source code structure of Vue Router reflects the component organization. Further exploration of the GitHub repository is necessary to gain a more comprehensive understanding of the specific files and their roles. Analyzing the repository's files and directories will unveil the distribution of different components and modules.


## Applied Perspective
Client-Server Architecture Perspective:
The client side, which is in charge of the user interface and presentation logic. The two main components of the client-server architecture are the server and data storage, processing, and business logic management. The client and server often utilize HTTP or WebSocket to communicate across a network.

We will take into account the following issues when we examine the system's design from a Client-Server design perspective:

- Scalability: The system's capacity to manage growing user volume and ongoing queries is the subject of this concern. We may examine the distributed processing capabilities, caching strategies, and load-balancing systems used in the overall framework of the vue-router system. It is crucial to determine if the design allows for horizontal scaling, which needs are increased by adding additional servers or adopting cloud-based solutions.

- Safety: A key component of every client-server design is security. It entails safeguarding the system from dangers such as data breaches, illegal access, and other security issues. The authentication procedures, data encryption techniques, secure communication protocols (such as HTTPS), and access control measures are implemented in the vue-router system.

- Performance: In client-server designs, performance is crucial, and it's crucial to assess the system's reaction times, network latency, and resource use. We can find possible obstacles and possibilities for development by examining these aspects. Performance in the vue-router system may be improved by methods including caching, improving network connection, and reducing server-side computation.
- Network Communication: Consider the client-server interactions and data types used in the vue-router system. This involves investigating any used communication techniques, such as WebSocket connections or RESTful APIs.
- Client-Side Rendering: Take into account how the vue-router system manages client-side rendering. Analyze the effectiveness of client-side component rendering and how it affects both performance and user experience.
Data Storage and Management: Analyze the server-side data storage technologies employed by the system for data management. To guarantee effective data storage and retrieval, examine the data models, database technology, and data management techniques used.

## Identify Styles & Patterns Used
#### High-level architectural style:
Vue Router follows the Model-View-ViewModel (MVVM) architectural approach, with clear distinctions between the Model, View, and ViewModel roles. These distinctions effectively separate data management, user interface, and data binding problems.

The Model layer in Vue Router is linked to the data points in a Vue component. This is where the application's information and functionality are saved. When this data changes in response to user activities, Vue Router may instantly update what the user sees on their screen. Vue Router offers a unique framework that connects the View to the ViewModel in an easy-to-use manner. This means that whenever the ViewModel changes, the View does as well.  The ViewModel layer, or the link between the Model and the View, is essentially a Vue component. A component in Vue Router performs the function of a ViewModel since it manages and modifies the data displayed on the View. It provides the View with attributes and methods and notifies it when something changes.

The Vue Router is an important feature in Vue.js applications that works in tandem with the ViewModel layer. It improves the MVVM architecture's efficacy by controlling application navigation, allowing for more sophisticated user interfaces with multiple views and navigation pathways. Vue Router refreshes the ViewModel, which then updates the View when the navigation path changes. This enables the user interface to be relatively simple.

Indeed, Vue Router employs several important software design patterns to improve its efficiency and maintainability.

## Architectural Assessment
- Single Responsibility Principle
<p>
Vue Router 3.0 adheres to the SRP by focusing on the responsibility of handling navigation and routing within a Vue.js application. Its primary role is to provide a way to define routes, map them to components, and manage the navigation flow. By limiting its scope to routing and navigation-related tasks, Vue Router promotes separation of concerns and keeps the responsibility of routing separate from other application logic. This enhances the modularity and maintainability of the codebase, as changes in routing requirements can be isolated to the router-related code without affecting other parts of the application. Additionally, Vue Router integrates seamlessly with Vue.js components and supports features like route-based code splitting, lazy-loading, and navigation guards. These features further reinforce the SRP by allowing developers to encapsulate specific functionality within individual components, keeping them focused on their primary responsibilities.
</p>
**code chunk

In link.js, the guardEvent function is responsible for checking various conditions before allowing the default navigation behavior to occur. It checks for control keys, default prevention, right-clicks, and target="_blank" attributes. This function has a single responsibility related to event guarding, which adheres to the SRP.

Additionally, the RouterView component in view.js and its helper functions have responsibilities related to rendering the appropriate component based on the route and handling props. They are closely related to the purpose of the component, making it cohesively follows the Single Responsibility Principle.

- Open-Closed Principle
<p>
Vue Router 3.0 adheres to the Open-Closed Principle by providing extension points and customizable APIs that allow developers to modify and enhance routing behavior without directly modifying the core implementation.
Vue Router enables developers to build upon its existing capabilities without the need to modify the underlying router code. This approach promotes code extensibility, maintainability, and reduces the risk of introducing regressions when making changes to the routing behavior.
For example, developers can customize route matching rules, introduce additional navigation guards, or create custom route components to handle specific scenarios. These extensions can be implemented through options provided by Vue Router, such as “beforeEach” or “beforeResolve” navigation guards, or by using advanced features like route components with custom logic.
By allowing for such extensions, Vue Router empowers developers to adapt the routing behavior to the specific needs of their application, while keeping the core router implementation intact. This separation between the core implementation and extension points aligns with the principles of the OCP.
</p>

Similarly, some examples can be found in the components of Vue Router.
** code chunk
The eventTypes array defines the types of events that can be specified as the event prop of the RouterLink component. By including different event types in this array, the component can handle additional events without modifying the existing code. This adheres to the Open-Closed Principle because the code is closed for modification, but it can be extended by adding new event types to the eventTypes array.

In view.js, the name prop in RouterView allows for the extension of its component by specifying a different view component name. This means that new view components can be added and rendered without modifying the existing RouterView component code. The component remains closed for modification while being open for extension through the name prop.

- Liskov Substitution Principle
<p>
Vue Router does not directly enforce the Liskov Substitution Principle because it does not involve inheritance or subclassing as a core part of its design. Instead, it focuses on providing routing functionality through composition and configuration within Vue.js applications. Therefore, the concept of substituting objects of a superclass with objects of its subclasses is not directly applicable to Vue Router.
While Vue Router itself does not enforce the LSP, it is a good practice to consider LSP when designing and implementing components that interact with Vue Router. For example, if a base component uses Vue Router's programmatic navigation methods, such as “router.push()” or “router.replace()”, a subclass component should be able to replace it and continue using these methods without introducing errors or breaking the navigation flow. This ensures that your components remain interchangeable and maintain the expected behavior when used in different contexts.
</p>

In the module of navigation guards, isUpdateNavigation and isLeaveNavigation functions are used to determine whether a navigation event should trigger the corresponding guard. When the behavior of these functions is not consistent with the behavior expected from their parent class useFilteredGuard, the LSP is violated.

## code chunk
Again, router view assumes that the matched object will contain components with specific names and performs actions based on that assumption. However, substituting the matched object with a different implementation that does not conform to these assumptions would lead to incorrect behavior or errors in the RouterView component.


- Interface Segregation Principle
<p>
In the context of Vue Router 3.0, ISP is highly relevant as it provides a modular and cohesive API that allows clients, such as Vue.js components and views, to selectively use the specific parts they require without being forced to depend on unnecessary functionality.
By adhering to ISP, Vue Router enables developers to separate concerns and keep components decoupled from unnecessary dependencies. Clients can interact with Vue Router through specific APIs like route configuration, programmatic navigation methods, navigation guards, and route parameters. This promotes a clean separation of responsibilities and improves code maintainability.
If a component only needs to define routes and handle basic navigation, it can focus solely on the route configuration aspects of Vue Router without being burdened by other functionalities. This allows the component to remain lightweight and focused on its specific responsibilities.
</p>

- Dependency Inversion Principle
<p>
Since Vue Router is primarily a low-level module that provides routing functionality to higher-level components and views within a Vue.js application. It is not responsible for managing dependencies or enforcing inversion of control.
Developers can just define their own abstractions or interfaces that represent the routing functionality required by their components. By depending on these abstractions, rather than directly on the Vue Router instance, components become independent of the concrete router implementation. Rather than directly importing and using the Vue Router instance in a component, the component could depend on a custom router interface that provides the necessary routing methods and properties. This allows for easier substitution of different routing implementations or mocks during testing.
</p>

## System Improvement
Multiple actions may be taken to improve the Vue Router system's performance. The system's reaction times will be improved, network latency will be decreased, and resource use will be optimized. The following suggestions can be taken into account:

- **Caching Strategy:**
Use caching to avoid performing time-consuming calculations and data retrieval. Route components, API answers, and other frequently accessed data can all benefit from caching. The technology can speed up response times and lower server load by caching data.

- **Network Connection Optimization:**
Use methods like HTTP/2, connection pooling, and compression to improve network connections. These improvements can help the system run more productively and minimize latency. Moreover, think about employing Content Delivery Networks (CDNs) to distribute static assets, optimizing speed.

- **Minification and Compression:**
JavaScript, CSS, and other static assets should be minified and compressed to minimize their file sizes. Faster download times and better performance, especially on networks with constrained capacity, are caused by smaller file sizes.

- **Code Splitting:**
Implement code-splitting strategies to ensure that only the JavaScript code required for each route or component is loaded. The first load time can be shortened and additional loads can be postponed until they are needed by breaking the code up into smaller portions. This strategy enhances perceived performance and aids in early rendering optimization.

- **Lazy Loading:**
Implement lazy loading to load route components only when they are required. This method shortens the first bundle and accelerates the loading of the first page. You can use dynamic imports or lazy loading or by leveraging Webpack's code-splitting capabilities.

- **Performance Testing and Optimization:**
Perform performance tests often to locate bottlenecks and potential areas for progress. To gauge and assess the system's performance, utilize tools like Lighthouse, WebPageTest, or Chrome DevTools. Apply improvements including crucial rendering route optimization, resource reduction for render-blocking, and TTFB improvement based on test findings.

- **Server-Side Rendering (SSR):**
Consider using server-side rendering (SSR) for pages that demand quicker page loads or improved search engine optimization (SEO). SSR reduces client-side rendering costs and boosts perceived performance by pre-rendering the Vue components on the server and sending the produced HTML to the client.

- **Progressive Web App (PWA) Features:**
Implement PWA capabilities, such as offline caching and service workers, to enable offline access and stimulate speed on subsequent visits. The application may continue to run even when there is no active network connection thanks to the offline functionality provided by service workers, who can also cache static assets and API answers.

- **Database and Data Storage Optimization:**
To guarantee effective data retrieval and manipulation, optimize database queries and data storage. To reduce the time it takes to access data, use effective indexing techniques, denormalization methods, and database speed optimization.

- **Performance Monitoring:**
Implement performance analytics and monitoring to track and evaluate the system's performance over time. To spot performance decline and take proactive measures to solve any problems, use tools like Google Analytics, New Relic, or bespoke monitoring solutions.

The Vue Router system may give quicker response times, enhanced user experiences, and effective resource use by putting these performance improvements into place, which will make the application more performant and responsive.


**Feature improvement:**
In the original code, when a developer makes a mistake by calling certain methods in the wrong place, the error message they see might be confusing. In the updated version, we made the error message more helpful. It now tells the developer that they might be using those methods outside of a Vue component, which is not allowed. This should make it easier for them to understand their mistake and how to fix it.

**code chunk**

function throwNoCurrentInstance (method) {
  if (!getCurrentInstance()) {
    throw new Error(
      ("[vue-router]: Missing current instance. " + method + "() must be called inside <script setup> or setup(). " +
      "Check that you are within a Vue component context when calling " + method + "().")
    )
  }
}

This error message now provides a little more context to the developer as to what might be the problem and what they should look into. Error messages should guide developers to the right solution and not leave them more confused.
