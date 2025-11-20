# Coding Of Era

📍Code Tangling:  
Code tangling is the mixing of unrelated functions or concerns within a single piece of code, leading to tight coupling and decreased modularity. It occurs when multiple responsibilities, such as business logic, security, and logging, are intertwined in the same code module, making it difficult to understand, maintain, and modify.    
**How code tangling occurs**: _Mixing of concerns, Time and delivery pressure, Minor changes over time._	
**How to solve code tangling**: _Separation of concerns, Refactoring, Better naming, Careful commits._	

📍Code scattering:  
"Code scattering" refers to the dispersion of code related to a single concern across multiple parts of an application, leading to code duplication and making it difficult to maintain. A related problem, code tangling, occurs when a single piece of code performs multiple functions. This is often seen as an "aspect-oriented" problem where, for example, logging or security checks are repeated in many different methods instead of being handled in a single, centralized location.	    
**How code scattering happens**: _Due to repetitive tasks, As a result of minor changes, Under time pressure._		
**How to solve code scattering**: _Use Aspect-Oriented Programming (AOP), Modularize code, Implement a clear design, Focus on refactoring._	

📍Join Point:  
In Spring AOP, Joinpoint refers to a candidate point in application where we can plug in an Aspect.
Joinpoint can be a method or an exception or a field getting modified.
This is the place where the code of an Aspect is inserted to add new behavior in the existing execution flow.  

📍Advice:	  
An Advice in Spring AOP, is an object containing the actual action that an Aspect introduces.
An Advice is the code of cross cutting concern that gets executed.
There are multiple types of Advice in Spring AOP.

Spring AOP provides five kinds of Advice:	
1. Before Advice: This type of advice runs just before a method executes. We can use **@Before** annotation for this.
2. After (finally) Advice: This type of advice runs just after a method executes. Even if the method fails, this advice will run. We can use **@After** annotation here.
3. After Returning Advice: This type of advice runs after a method executes successfully. **@AfterReturning** annotation can be used here.
4. After Throwing Advice: This type of advice runs after a method executes and throws an exception. The annotation to be used is **@AfterThrowing**.
5. Around Advice: This type of advice runs before and after the method is invoked. We use **@Around** annotation for this.

📍Aspect:	  

📍Weaving:	  

