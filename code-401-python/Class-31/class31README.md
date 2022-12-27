## Component-Based Architecture


Component-based architecture focuses on the decomposition of the design into individual functional or logical components that represent well-defined communication 
interfaces containing methods, events, and properties. It provides a higher level of abstraction and divides the problem into sub-problems, each associated with 
component partitions.


### What is a Component?

A component is a modular, portable, replaceable, and reusable set of well-defined functionality that encapsulates its implementation and exporting it as a 
higher-level interface.

A component is a software object, intended to interact with other components, encapsulating certain functionality or a set of functionalities. It has an obviously
defined interface and conforms to a recommended behavior common to all components within an architecture.


### Characteristics of Components

- Reusability − Components are usually designed to be reused in different situations in different applications. However, some components may be designed for a 
  specific task.

- Replaceable − Components may be freely substituted with other similar components.

- Not context specific − Components are designed to operate in different environments and contexts.

- Extensible − A component can be extended from existing components to provide new behavior.

- Encapsulated − A A component depicts the interfaces, which allow the caller to use its functionality, and do not expose details of the internal processes or any 
  internal variables or state.

- Independent − Components are designed to have minimal dependencies on other components.



### Principles of Component−Based Design

- the software system is decomposed into reusable, cohesive, and encapsulated component units.

- Each component has its own interface that specifies required ports and provided ports; each component hides its detailed implementation.

- A component should be extended without the need to make internal code or design modifications to the existing parts of the component.

- Depend on abstractions component do not depend on other concrete components, which increase difficulty in expendability.

- Connectors connected components, specifying and ruling the interaction among components. The interaction type is specified by the interfaces of the components.

- Components interaction can take the form of method invocations, asynchronous invocations, broadcasting, message driven interactions, data stream communications,
  and other protocol specific interactions.

- For a server class, specialized interfaces should be created to serve major categories of clients. Only those operations that are relevant to a particular
  category of clients should be specified in the interface.

- A component can extend to other components and still offer its own extension points. It is the concept of plug-in based architecture. This allows a plugin to
  offer another plugin API.
  
 ![image](https://www.tutorialspoint.com/software_architecture_design/images/principles_of_component_based_design.jpg)
 
 
 
 ### Component-Level Design Guidelines
 
- Attains architectural component names from the problem domain and ensures that they have meaning to all stakeholders who view the architectural model.

- Extracts the business process entities that can exist independently without any associated dependency on other entities.

- Recognizes and discover these independent entities as new components.

- Uses infrastructure component names that reflect their implementation-specific meaning.

- Models any dependencies from left to right and inheritance from top (base class) to bottom (derived classes).

- Model any component dependencies as interfaces rather than representing them as a direct component-to-component dependency.


### Advantages

1. Ease of deployment 

2. Reduced cost 

3. Ease of development 

4. Reusable 

5. Modification of technical complexity 

6. Reliability 

7. System maintenance and evolution 

8. Independent 
