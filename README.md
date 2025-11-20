# Coding Of Era

📍Code Tangling:  
Code tangling is the mixing of unrelated functions or concerns within a single piece of code, leading to tight coupling and decreased modularity. It occurs when multiple responsibilities, such as business logic, security, and logging, are intertwined in the same code module, making it difficult to understand, maintain, and modify.	
How code tangling occurs: Mixing of concerns, Time and delivery pressure, Minor changes over time.	
How to solve code tangling: Separation of concerns, Refactoring, Better naming, Careful commits.	

📍Code scattering:  
"Code scattering" refers to the dispersion of code related to a single concern across multiple parts of an application, leading to code duplication and making it difficult to maintain. A related problem, code tangling, occurs when a single piece of code performs multiple functions. This is often seen as an "aspect-oriented" problem where, for example, logging or security checks are repeated in many different methods instead of being handled in a single, centralized location.	
How code scattering happens: Due to repetitive tasks, As a result of minor changes, Under time pressure.		
How to solve code scattering: Use Aspect-Oriented Programming (AOP), Modularize code, Implement a clear design, Focus on refactoring.	

📍Join Point:  
In Spring AOP, Joinpoint refers to a candidate point in application where we can plug in an Aspect.
Joinpoint can be a method or an exception or a field getting modified.
This is the place where the code of an Aspect is inserted to add new behavior in the existing execution flow.  

📍Advice:	  

📍Aspect:	  

📍Weaving:	  

