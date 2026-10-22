# CS 230 Portfolio Reflection

## The Gaming Room Software Design

[View the completed software design document](./CS230_Project_Three_Software_Design_Tristan_White.docx)

## Client and Software Requirements

The client for this project was The Gaming Room. The company already had an Android game called *Draw It or Lose It* and wanted to expand it into a web-based application that could be used on multiple operating systems and devices. The software needed to support multiple games, teams, and players. It also needed to prevent duplicate game and team names, assign a unique identifier to each object, and maintain one shared instance of the game service. Since the application would operate in a distributed environment, the design also needed to consider security, storage, network communication, performance, and the ability to support more users as the application grows.

## What I Did Well

I believe one of the strongest parts of my work was connecting the technical recommendations back to the client’s actual needs. Instead of simply comparing Windows, macOS, Linux, and mobile devices in general, I evaluated how each platform would support this specific application. Based on that evaluation, I recommended Ubuntu Server LTS as the server platform while keeping the client side browser based. This would allow users on Windows, macOS, Linux, Android, and iOS to access the same application without requiring The Gaming Room to maintain a separate version for each operating system.

I also explained how PostgreSQL, cloud object storage, and a content delivery network could work together to manage game information and the image library. This gave the recommendation more detail than simply selecting an operating system.

## How the Design Document Helped with Development

Working through the design document helped me understand how the different parts of the application needed to connect before writing or changing the code. The UML diagram made the relationships between GameService, Game, Team, Player, and Entity easier to follow. It showed that GameService manages games, each game contains teams, and each team contains players.

The document also helped explain the purpose of the Singleton and Iterator patterns used in the Java application. The Singleton pattern makes sure the program uses one GameService instance, while the Iterator pattern allows the program to search existing collections before creating a new game, team, or player. Planning these relationships first made the code easier to understand and reduced the chance of adding unnecessary or repeated logic.

## What I Would Revise

If I could revise one part of the design document, I would add a complete system architecture diagram. The template did not require that section for this project, but a diagram would make the recommended distributed system easier to understand. I would show browser clients connecting through a load balancer to the Java application servers, with those servers connected to PostgreSQL, shared memory or session storage, and cloud object storage.

Adding that diagram would help both technical and nontechnical readers see how requests, game data, and image files move through the system. It would also make the relationship between the written recommendations and the final architecture clearer.

## Interpreting the User’s Needs

I interpreted the client’s needs by turning each business requirement into a technical design decision. The need to support several operating systems led to a browser-based client. The need to prevent duplicate names led to validation in the Java application and unique constraints in the database. The need for consistent game information led to making the server the authoritative source for game state. The need to support future growth led to recommendations for shared storage, a relational database, load balancing, and multiple application instances.

Considering the user’s needs is important because software can function correctly and still fail if it does not solve the client’s actual problem. A design decision should have a clear purpose that connects to usability, reliability, security, performance, or another client requirement.

## My Approach to Designing Software

My approach was to begin with the client’s requirements and identify the main objects, relationships, and responsibilities within the application. From there, I used the UML diagram and design patterns to organize the program before evaluating the operating platforms. I then compared the strengths and weaknesses of each platform based on how well it could support the completed design.

For a similar project in the future, I would continue separating functional requirements from nonfunctional requirements. Functional requirements describe what the application must do, while nonfunctional requirements address areas such as performance, security, reliability, and scalability. I would also create the architecture diagram earlier, build a small prototype to test important assumptions, and use security and performance testing throughout development. This process would make it easier to find design problems before they become larger problems in the completed application.

## AI Use Acknowledgment

I used OpenAI ChatGPT to help organize my response and review it for grammar and clarity. I reviewed the final response and made the final decisions about what to include.

OpenAI. (2026). *ChatGPT* [Large language model]. https://chatgpt.com/
