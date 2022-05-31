# Chapter 11: Systems

- Software systems should separate the startup process, when the application objects are constructed and the dependencies are “wired” together, from the runtime logic that takes over after startup.
- The startup process is a concern that any application must address.
- Software system architectures can grow incrementally, if we maintain the proper separation of concerns.
    - The system must be built in a way that can be iterated over time, such as a repository that is separated into different components / building blocks that can work independent of each other, but connects nicely to form a big picture.
    - Concept of modularity and separation of concerns. 