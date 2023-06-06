# Vue Router
A robust routing framework created specifically for Vue.js applications is called Vue Router. It has a thorough routing system and effortlessly interacts with Vue.js, a progressive JavaScript framework for creating user interfaces.
## Context and Background
Vue CLI( Vue Command Line) is a development tool that aims to simplify and streamline the process of creating, managing, and building Vue.js projects. The Vue.js is a progressive JavaScript framework for building approachable, flexible, and efficient user interfaces. Through a command-line interface, the CLI is a tool that enables developers to communicate with the Vue ecosystem, and provides various commands and features to scaffold new projects, configure project settings, run development servers, and optimize and build projects for production. Vue Router was developed to address the need for a robust routing system within Vue.js applications. It provides a way to map URLs to different views or components, allowing users to create dynamic and responsive Single-Page application. As we doing this project, we mainly focus on the plugins and extensions as it recommends.

## Development View
The development view analyzes the component-level structure of Vue Router, identifying the major modules and their dependencies. The below section offers an overview of the system's components, their organizations, and interactions.
#### System Components
The source code needs to be analyzed to understand the component-level architecture of the Vue Router. The source code analysis will also help in understanding the components of the system. Discussed below are the components of the Vue router repository:


## Applied Perspective
Client-Server Architecture Perspective:
The client side, which is in charge of the user interface and presentation logic. The two main components of the client-server architecture are the server and data storage, processing, and business logic management. The client and server often utilize HTTP or WebSocket to communicate across a network.

We will take into account the following issues when we examine the system's design from a Client-Server design perspective:
Scalability: The system's capacity to manage growing user volume and ongoing queries is the subject of this concern. We may examine the distributed processing capabilities, caching strategies, and load-balancing systems used in the overall framework of the vue-router system. It is crucial to determine if the design allows for horizontal scaling, which needs are increased by adding additional servers or adopting cloud-based solutions.
Safety: A key component of every client-server design is security. It entails safeguarding the system from dangers such as data breaches, illegal access, and other security issues. The authentication procedures, data encryption techniques, secure communication protocols (such as HTTPS), and access control measures are implemented in the vue-router system.

## Identify Styles & Patterns Used
#### High-level architectural style:
Vue Router follows the Model-View-ViewModel (MVVM) architectural approach, with clear distinctions between the Model, View, and ViewModel roles. These distinctions effectively separate data management, user interface, and data binding problems.

The Model layer in Vue Router is linked to the data points in a Vue component. This is where the application's information and functionality are saved. When this data changes in response to user activities, Vue Router may instantly update what the user sees on their screen. Vue Router offers a unique framework that connects the View to the ViewModel in an easy-to-use manner. This means that whenever the ViewModel changes, the View does as well.  The ViewModel layer, or the link between the Model and the View, is essentially a Vue component. A component in Vue Router performs the function of a ViewModel since it manages and modifies the data displayed on the View. It provides the View with attributes and methods and notifies it when something changes.


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

- Liskov Substitution Principle
<p>
Vue Router does not directly enforce the Liskov Substitution Principle because it does not involve inheritance or subclassing as a core part of its design. Instead, it focuses on providing routing functionality through composition and configuration within Vue.js applications. Therefore, the concept of substituting objects of a superclass with objects of its subclasses is not directly applicable to Vue Router.
While Vue Router itself does not enforce the LSP, it is a good practice to consider LSP when designing and implementing components that interact with Vue Router. For example, if a base component uses Vue Router's programmatic navigation methods, such as “router.push()” or “router.replace()”, a subclass component should be able to replace it and continue using these methods without introducing errors or breaking the navigation flow. This ensures that your components remain interchangeable and maintain the expected behavior when used in different contexts.
</p>

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
