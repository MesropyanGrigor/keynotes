
**Thinking Architecturally**

- N-Tier System, teams represent layers (like asking DB team to update the DB)

- Story: A description of the user's work - a story touches every piece of the system,
    it is not description of the computer program

- Agile is to build one small piece and then add it, so Design evolves increamentaly

- Domain-Driven Design (DDD): the structure of your code should map to the structure of the problem domain 

<<
A: Your team is creating software that must support only a few users at first. The number of users will increase substantially later. Which base design should you use and why?

Q: Use an agile incremental design because you can deploy something quickly and add more functionality later, as the user base increases.


Q: How does agile software development differ from siloed software development, and what advantage does this provide?

A: You work on thin, vertical slices compared to completely isolated and segmented parts, reducing development delays.
>>



**Design Process: A brief introduction**

- problem statement, you need to know what is user's problems, need to describe the problem
- when you understand the problem you can solve it, User Story: Describes your user work
- (Example: Need a way to submit comments about their articals and authors need a way to respond)
- Next step is refine the user story, helpful to use UML
- 

<<
Q: You are to begin the development of an architecture for an accounting system. How should you approach writing the problem statement for this project?

A: Describe the end user’s problem and the solution to this problem in the same way an accountant would.
>>

**Broad Architecural Patterns**

Monolith - is a one larg executable unit, 100 000 lines, Test and Deploy monolith is not trival task
Microkernel (plugin) architecture - Kernel and sum other services

