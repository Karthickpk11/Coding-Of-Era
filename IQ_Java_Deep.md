In Java, a **ClassLoader** is part of the **Java Runtime Environment (JRE)** that **dynamically loads `.class` files into memory when they are needed**. Instead of loading all classes at startup, Java loads classes **on demand**, which saves memory and improves startup time.

---

## 1. What is a ClassLoader?

A **ClassLoader** is a Java class responsible for:

* **Loading class bytecode (`.class` files)**
* **Converting bytecode into a Java `Class` object**
* **Placing the class into JVM memory**

Every Java class is loaded by some **ClassLoader**.

Example:
When you write:

```java
MyClass obj = new MyClass();
```

If `MyClass` is not already loaded, the JVM asks a **ClassLoader** to load it.

---

## 2. Class Loading Process in JVM

The class loading process has **three main phases**:

### 1️⃣ Loading

The **ClassLoader reads the `.class` file** and creates a `Class` object in memory.

### 2️⃣ Linking

Linking has **three steps**:

**a. Verification**

* Ensures bytecode is **valid and secure**
* Prevents illegal operations

Example:    
* Stack overflow
* Invalid bytecode

**b. Preparation**

* Allocates **memory for static variables**
* Initializes them with **default values**

**c. Resolution**

* Converts **symbolic references → direct references**

becomes a real memory reference.

### 3️⃣ Initialization

Static variables and static blocks are initialized.

Example:

```java
static int x = 10;

static {
    System.out.println("Class initialized");
}
```
---

## 3. Types of ClassLoaders in Java

Java uses a **hierarchy of class loaders**.

### 1️⃣ Bootstrap ClassLoader

* Written in **native code**
* Loads **core Java classes**

Examples:

* `java.lang.String`
* `java.lang.Object`
* `java.util.*`

### 2️⃣ Extension ClassLoader (Platform ClassLoader in modern Java)

Loads classes from:

Example libraries:

* Java extension APIs

### 3️⃣ Application ClassLoader

Loads classes from the **application classpath**.    
This loader loads **your project classes**.

---

## 4. ClassLoader Delegation Model (Very Important)

Java follows a **Parent Delegation Model**.

When a class is requested:

1. **Application ClassLoader** receives request
2. It asks **Parent (Extension)**
3. Extension asks **Bootstrap**
4. Bootstrap tries to load
5. If not found → control returns down the chain

Flow:

```
Application ClassLoader
        ↓
Extension ClassLoader
        ↓
Bootstrap ClassLoader
```

Why?

### Security

Your code **cannot override core classes**.

Example:

You cannot replace:

```
java.lang.String
```

with a malicious class.

---

## 5. Example: Checking ClassLoader

```java
public class Test {
    public static void main(String[] args) {
        System.out.println(String.class.getClassLoader());
        System.out.println(Test.class.getClassLoader());
    }
}
```

Output:

```
null
jdk.internal.loader.ClassLoaders$AppClassLoader@xxx
```

Explanation:

* `String` → **Bootstrap loader (null)**
* `Test` → **Application loader**

---

## 6. Custom ClassLoader

You can create your **own ClassLoader** by extending:

```java
ClassLoader
```

Example:

```java
class MyClassLoader extends ClassLoader {

    @Override
    protected Class<?> findClass(String name) throws ClassNotFoundException {
        byte[] classData = loadClassFromFile(name);
        return defineClass(name, classData, 0, classData.length);
    }
}
```

Uses:

* Dynamic module systems
* Plugin systems
* Application servers
* Hot deployment

Example systems:

* Tomcat
* Spring Boot
* OSGi

---

## 7. Real Example (Why ClassLoader is Powerful)

Application servers like **Tomcat** load **multiple versions of the same library**.

Each application has its **own ClassLoader**, preventing conflicts.

---

## 8. Quick Visual Flow

```
Request to load class
        ↓
Application ClassLoader
        ↓
Extension ClassLoader
        ↓
Bootstrap ClassLoader
        ↓
If found → return class
Else → go back and try next loader
```

---

✅ **In one line:**

> A **ClassLoader dynamically loads Java classes into JVM memory and follows a parent delegation model to ensure security and avoid duplicate loading.**

---
