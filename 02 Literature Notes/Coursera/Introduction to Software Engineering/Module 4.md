---
tags:
  - literature
source: 
created: 2025-07-10
Type: "[Lecture | Book | PDF | Video]"
---
# Software Architecture and Design
## Introduction to Software Architecture
- The content focuses on the fundamental aspects of software architecture and its significance in software development.

- Understanding Software Architecture
	- Software architecture is the organization of a software system, serving as a blueprint for development.
	- It defines how components interact, the operating environment, and design principles, capturing early design decisions that are costly to change later.

- Importance of Well-Designed Architecture
	- A well-structured architecture balances stakeholder needs and facilitates communication among team members.
	- It influences technology stack choices and accommodates changing requirements, enhancing the software's lifespan.

- Artifacts in Software Architecture
	- Key artifacts produced during architectural design include the Software Design Document (SDD), architectural diagrams, and Unified Modeling Language (UML) diagrams.
	- These artifacts communicate design decisions and specifications, guiding the implementation and understanding of the software system.

## Software Design and Modelling
- This content focuses on key concepts in software design and modeling, particularly the use of structured design and Unified Modeling Language (UML).

- Structured Design
	- Breaks down software problems into smaller, organized modules and sub-modules.
	- Emphasizes [[cohesion]] (grouping related elements) and [[loose coupling]] (minimizing dependencies between modules).

- [[Unified Modeling Language (UML)]]
	- A standardized visual representation for software architecture, design, and implementation.
	- UML diagrams can be structural or behavioral, aiding in communication among developers and stakeholders.

- Behavioral Models
	- Describe system behavior without detailing implementation.
	- Include state transition diagrams (showing states and events) and interaction diagrams (illustrating object communication over time).

## Object-Oriented Analysis and Design
- The content focuses on the principles of object-oriented analysis and design (OOAD) in software engineering.

- Understanding Objects and Classes
	- Objects are entities that contain data and behaviors, representing real-world items or concepts.
	- A class serves as a blueprint for creating specific objects, known as instances, which have defined attributes and methods.

- Class Diagrams in OOAD
	- Class diagrams are structural UML diagrams that illustrate the relationships between classes in an object-oriented design.
	- They show attributes of classes and how subclasses inherit properties and methods from parent classes.

- The Role of OOAD
	- OOAD helps in planning software systems by breaking them down into interacting objects, allowing multiple developers to work simultaneously.
	- It emphasizes the importance of visual diagrams to represent both the static structure and dynamic behavior of a system.

## Insiders' Viewpoint: Importance of Design and Software Architecture
- The video lecture emphasizes the significance of design and software architecture in software engineering projects.

- Understanding the Importance of Design and Architecture
	- Design and architecture guide the development process, ensuring that developers know what their program needs to handle and the environment it operates in.
	- A well-structured architecture prevents wasted time on code that may not work as intended, promoting efficiency in the development process.

- Key Considerations in Software Architecture
	- It is essential to consider scalability and global availability, as solutions that work locally may not perform well on a larger scale.
	- Understanding data flow and service interactions is crucial to avoid performance issues, especially in microservice architectures.

- Long-term Planning in Software Development
	- Effective architecture requires thinking ahead, considering future needs and potential growth to avoid frequent redesigns.
	- Sustainable architecture should be built to last, minimizing the need for major changes over time, similar to how buildings are maintained.

- [[5 Architectural Patterns]]

# Software Architecture Patterns and Deployment Topologies
## Approaches to Application Architecture
- This content focuses on understanding component-based architectures, service-oriented architecture, and distributed systems in software engineering.

- Component Characteristics
	- Components are individual units of functionality that can be reused, replaced, and operate independently.
	- Key characteristics include reusability, replaceability, independence, extensibility, encapsulation, and being non-context specific.

- Service-Oriented Architecture (SOA)
	- Services are similar to components but are designed for independent deployment and reuse across multiple systems.
	- SOA allows services to communicate through a network using protocols, supporting the creation of distributed systems.

- Distributed Systems
	- A distributed system consists of multiple services on different machines that appear as a single coherent system to users.
	- They are fault-tolerant, scalable, and can run on various hardware and software, enhancing performance and resource sharing.

## Architectural Patterns in Software
- This content focuses on various software architectural patterns, providing an overview of their characteristics and examples.
- [[5 Architectural Patterns]]
	- 2-Tier Architecture
	- Also known as client-server architecture, where the server manages resources and services for multiple clients.
	- Example: Text messaging apps and database clients connecting with database servers.

- 3-Tier Architecture
	- Composed of three layers: presentation tier (user interface), application tier (business logic), and data tier (data management).
	- Commonly used in web applications, where each tier interacts with the others.

- Peer-to-Peer and Event-Driven Architectures
	- Peer-to-peer (P2P) architecture consists of decentralized nodes acting as both clients and servers, useful for file sharing and cryptocurrencies.
	- Event-driven architecture focuses on events triggered by users or systems, with producers and consumers processing these events, suitable for modern distributed systems.
## Application Deployment Environments
- This content focuses on understanding application deployment environments, including their types and purposes.

- Pre-Production Environments
	- Development: The platform where active coding occurs, often on a developer's workstation.
	- QA (Quality Assurance): The environment for testing application components by the QA team.

- Production Environment
	- Definition: The complete solution stack, including hardware and software, intended for general users.
	- Considerations: Must account for load, security, reliability, and scalability due to potential high user traffic.

- Deployment Options
	- On-Premises: Infrastructure located within the organization, offering greater security but often at a higher cost.
	- Cloud Models:
	    - Public Cloud: Shared infrastructure over the internet, cost-effective and scalable.
	    - Private Cloud: Exclusive infrastructure for a single organization, offering enhanced security and customization.
	    - Hybrid Cloud: A combination of public and private clouds, optimizing cost, security, and flexibility.
## Production Deployment Components
- This content focuses on the essential components required for deploying applications in a production environment.

- Deployment Architecture
	- The n-tier architecture includes a presentation tier (front-end client applications), a web tier (with a web load balancer), an application server tier (with an app load balancer), and a data tier (database server).
	- Firewalls protect the internal network by monitoring and controlling traffic, while load balancers distribute incoming traffic to prevent server overload.

- Key Components
	- Web servers deliver content (web pages, files, images) to clients, responding to HTTP requests from web browsers.
	- Application servers run business logic and provide applications to clients, enabling interaction with server-side application code.

- Database Management
	- Database servers store and manage data, controlled by a Database Management System (DBMS) that connects the database to users or applications.
	- High availability replicas of databases are often used to ensure reliability in production environments.
## Insiders' Viewpoints: Deployment Architecture
- The video lecture focuses on key aspects of software deployment architecture, emphasizing the importance of design principles and infrastructure choices.

- **Understanding Scale and Design Principles**
	- Consider the scale of your system, including user count, data flow, and real-time access needs.
	- Define metrics for a healthy system and monitor them to ensure service level objectives (SLOs) are met.

- **Infrastructure Choices and Testing**
	- Choose between serverless, hosted, or self-hosted infrastructure based on your project needs.
	- Emphasize the importance of testing, particularly through test-driven development (TDD), to ensure code quality.

- **Deployment Strategies**
	- Utilize canary releases to test new code in production without affecting the entire system.
	- Plan for quick rollbacks if issues arise during deployment, balancing the speed of releases with system stability.
# Summary & Highlights
- Congratulations! You have completed this module. At this point, you know that: 
	- Software architecture functions as a blueprint and represents the importance of a good architectural design. 
	- Structured design breaks down a software problem into well-organized smaller solution elements whereas behavioral models describe the behavior of the system without explaining how the system implements the behavior. 
	- Developing UML diagrams saves time and money by helping developers quickly get up to speed on a project, plan features in advance of coding, and navigate source code easily. Types of UML diagrams include state transition, interaction, and class diagrams.  
	- Objects contain data, and they also have behaviors that prescribe the actions the object can take, whereas classes are blueprints for objects.  
	- A service-oriented architecture (SOA) consists of loosely coupled services that interface with each other via a communication protocol over a network. Distributed systems run on multiple services on different machines, but they appear to the end-user as a single coherent system. 
	- An architectural pattern is a repeatable solution to an architectural problem. Types of architectural patterns include 2-tier, 3-tier, event-driven, peer-to-peer, and microservices. Two or more patterns can be combined in a single system, but some are mutually exclusive.  
	- Application environments include development, testing or QA, staging, and production. Production environments tend to be more complex than pre-production because they must take into account non-functional requirements like load, security, reliability, and scalability.  
	- Application environments can be deployed either on-premises on traditional hardware, or on public, private, or hybrid cloud platforms. 
	- Common components needed for a production environment include a firewall, a load balancer, web and application servers, proxy servers, and database servers.