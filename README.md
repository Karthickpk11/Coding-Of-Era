# Coding Of Era

⭐ SOLID Principles (Object-Oriented Design)

SOLID is a set of five design principles that make software maintainable, scalable, flexible, and easier to test.

They are:

S — Single Responsibility Principle (SRP)	    
O — Open/Closed Principle (OCP)		    
L — Liskov Substitution Principle (LSP)		    
I — Interface Segregation Principle (ISP)	    
D — Dependency Inversion Principle (DIP)	    

Let’s break them down.

1️⃣ Single Responsibility Principle (SRP)

A class should have only one reason to change.
Meaning: A class should do one job, not many.

✔ Example (Bad)
class Invoice {
    void calculateTotal() { }
    void printInvoice() { }
    void saveToDB() { }
}

This class calculates, prints, and saves — 3 responsibilities.

✔ Example (Good)
class InvoiceCalculator { }
class InvoicePrinter { }
class InvoiceRepository { }

Each class has one responsibility → easier to maintain.


2️⃣ Open/Closed Principle (OCP)

Software entities should be open for extension but closed for modification.
You should be able to add new functionality without changing existing code.

✔ Example

Instead of modifying a method when new payment types are added:

Bad

if (type == "UPI") { ... }
else if (type == "Card") { ... }


Good: Use polymorphism

interface Payment {
    void pay();
}

class UPIPayment implements Payment { ... }
class CardPayment implements Payment { ... }

Now you can add new payment types without modifying existing classes.


3️⃣ Liskov Substitution Principle (LSP)

Subclasses should be substitutable for their parent classes without breaking the program.

If B is a subclass of A, then objects of type A should be replaceable with objects of type B.

❌ Bad example

A Square subclass changing the behavior of a Rectangle (height = width breaks methods expecting independent values).

✔ Good example
class Bird {
   void fly();
}

class Sparrow extends Bird { }

The child doesn’t violate the parent’s expected behavior.


4️⃣ Interface Segregation Principle (ISP)

Clients should not be forced to depend on interfaces they do not use.

❌ Bad example

A large interface:

interface Machine {
    void print();
    void scan();
    void fax();
}

A simple printer shouldn't implement scan or fax.

✔ Good example

Split into smaller interfaces:

interface Printer { void print(); }
interface Scanner { void scan(); }
interface Fax { void fax(); }

Classes only implement what they actually need.


5️⃣ Dependency Inversion Principle (DIP)

Depend on abstractions, not concrete implementations.

High-level modules shouldn’t depend on low-level modules directly.

✔ Example

Instead of:

class Notification {
    EmailService emailService = new EmailService();
}

Use abstraction:

interface MessageService {
    void sendMessage();
}

class EmailService implements MessageService { }

class Notification {
    private MessageService service;
    Notification(MessageService service) { this.service = service; }
}

This allows using Email, SMS, Push, etc. → improves testability and flexibility.

🎯 Easy Summary for Interviews

SOLID helps create flexible, testable, and maintainable object-oriented systems.
SRP gives one responsibility per class, OCP allows extension without modification, LSP ensures subclasses work as expected, ISP splits large interfaces, and DIP makes classes depend on abstractions instead of concrete implementations.


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


<ins>Microservice Pattern & Architecture:</ins>	
_Services Communication_:	  
📍Inter-Process Communication Types:	  
<img width="1210" height="708" alt="image" src="https://github.com/user-attachments/assets/d9cc4c38-0afb-432b-adda-4f649629e054" />


