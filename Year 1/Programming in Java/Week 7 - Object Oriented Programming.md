**Concepts of OOP**

Object Oriented Programming OOP
- OOP models the world with objects, each having its own state and behaviour
- Objects are instances of classes, and each object occupies its own space in memory

Key Concepts: 

1. State: 
    
    - Represented by an object’s variables (attributes or fields). 
        
    - States can change based on the class intended behaviour (e.g., a human object can be asleep or awake). 
        
2. Behaviour: 
    
    - Represented by the methods of the object. 
        
    - Methods change an objects state 
        
3. Encapsulation: 
    
    - Hides the internal state of an object to prevent unintentional modifications. 
        
    - States should be modified only through the object’s methods, ensuring controlled access. 
        
    - Attributes should be accessed from the main code by calling the objects method, rather than referring to the object directly.  
        
    - E.g. studentNum = Student.studentNum violates encapsulation. studentNum = Student.getStudentNum() is better.  
        

Class Definition: 

- Specifies what the object is (possible states) and how it behaves. 
    
- Different objects of the same class can act independently. 
    

Getters and Setters: 

- Setters: Methods that update an object’s state, taking input from the code (returns void). 
    
- Getters: Methods that retrieve information from the object and return it to the code (always return a value). 
    
- Use verbs in method names where possible to represent modelled behaviours.  
    

The this Keyword: 

- Refers to the class’s own attributes in a method or constructor. 
    
- Useful to avoid confusion between class attributes and parameters with the same name. (class attribute is shadowed by a method or constructor parameter) 
    
- Best practice is to use this for clarity and to ensure correct referencing. 
    

Constructor: 

- A special method to initialize an object in a specific state without needing setters. 
    
- Constructors are optional and can initialize all or some attributes, leaving the rest for future updates via methods. 
    
- Constructors can be overloaded, meaning there are multiple constructors with amounts of parameters. This allows the class to be initialised with different numbers of parameters. 
    

Access Modifiers 

- Private is a keyword that can be used when declaring a classes attributes. 
    
- It is called an access modifier.  
    
- It can help uphold encapsulation, as it means the attribute will only be visible from within the class. The only way to access the attributes from the outside code would be through getter and setter methods. 
    
- If a private class attribute is attempted to be accessed directly from outside the class, an error will be thrown.  
    
- Most methods from within the class are defined as public, so they can be accessed from the outside (such as getters and setter) but there are cases where private methods may be used.  
    
- Private methods may be used if you have a method within the class that is called from another method within the class. But if you know the method will be used from outside the class, you will need a public access modifier.  
    
- Default and protected are other access modifiers, but these are not covered on the module.