# Vue Router
## Introduction
Vue Router is a routing library that allows developers to manage client-side routing in single-page applications (SPAs) built with the Vue.js framework. It enables the creation of dynamic and interactive user interfaces by mapping URLs to specific components. Features include:
  <ul>
    <li>Nested routes mapping</li>
    <li>Dynamic Routing</li>
    <li>Modular, component-based router configuration</li>
    <li>Route params, query, wildcards</li>
    <li>View transition effects powered by Vue.js' transition system</li>
    <li>Fine-grained navigation control</li>
    <li>Links with automatic active CSS classes</li>
    <li>HTML5 history mode or hash mode</li>
    <li>Customizable Scroll Behavior</li>
    <li>Proper encoding for URLs</li>
  </ul>
<p>Vue Router was created by Evan You, the creator of Vue.js, and is currently maintained by the Vue.js team and the open-source community. The Vue.js team is responsible for approving changes to its code and architecture, and the library is developed and maintained as an open-source project.</p>

## Report

### Applied Perspective:
- Client-Server Architecture Perspective:
<p>The client side, which is in charge of the user interface and presentation logic. The two main components of the client-server architecture are the server and data storage, processing, and business logic management. The client and server often utilize HTTP or WebSocket to communicate across a network.</p>

- Relevant Client-Server Architecture Concerns
<ul>

**Scalability** : Consider the system's capacity to scale in order to accommodate growing user traffic and many continuous inquiries. This entails investigating the distributed processing capabilities, caching techniques, and load balancing systems.

**Safety** : Evaluate the system's security procedures in place to guard against unauthorized access, data breaches, and other security risks. Analyzing authentication processes, data encryption, and secure communication protocols may be necessary for this.

**Performance** : Consider the client-server aspect of the vue-router architecture while evaluating performance. To find possible bottlenecks or opportunities for improvement, analyze variables like response times, network latency, and resource use.

**Network Communication** : Consider the client-server interactions and data types used in the vue-router system. This involves investigating any used communication techniques, such as WebSocket connections or RESTful APIs.

**Client-Side Rendering** : Take into account how the vue-router system manages client-side rendering. Analyze the effectiveness of client-side component rendering and how it affects both performance and user experience.

**Data Storage and Management** : Analyze the server-side data storage technologies employed by the system for data management. To guarantee effective data storage and retrieval, examine the data models, database technology, and data management techniques used.
</ul>

### Identify Styles & Patterns Used:

- High-level architectural style:

**Client-side:** Vue Router controls routing logic within the browser rather than on the server. This method enables dynamic changes and smoother transitions between views or pages without requiring a full page reload. Client-side routing allows for a more engaging and responsive user experience.

**Presentation Layer:** This layer is responsible for drawing components and handling user interactions and constitutes the user interface (UI). Vue components serve as the presentation layer in Vue.js apps. Vue Router is embedded into the presentation layer and is in charge of routing and navigation issues. It contains the components and logic required to enable navigating between multiple views based on the active route.

-  Software Design Patterns:

**“Front Controller" design pattern**

The Vue Router uses the "Front Controller" design pattern. The Front Controller design centralizes request handling and serves as a single point of entry for routing and request processing. The router instance functions as the front controller in the context of Vue Router, controlling the routing logic and processing requests for multiple routes.

The Front Controller design is used by Vue Router, which provides a centralized router instance that controls routing setup and handles navigation within a Vue.js application. The router instance defines the accessible routes and associated components, and it handles component rendering based on the active route. Vue Router provides a consistent and centralized method to routing in Vue.js applications, fostering separation of concerns and modularization.
