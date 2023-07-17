- The SOLID principles are five principles of Object-Oriented class design.
- The SOLID principles were first introduced by the famous Computer Scientist Robert J. Martin (a.k.a Uncle Bob)
- Let's look at each principles one by one. Following the SOLID acronym, they are:
1) The Single Responsibility Principle (SRP)
2) The Open-Closed Principle (OCP)
3) The Liskov Substitution Principle (LSP)
4) The Interface Segration Principle (ISP)
5) The Dependency Inversion Priciple (DIP)

    1) The Single Responsibility Principle (SRP)
    - A class should have one, only one reason to change
    - Every software module should have ony one reason to change
    Example: 
    - 3-layer architecture: 
        1.1 API: Handle request from client
        1.2 Application: Process business logic 
        1.3 Data access layer:
            1.3.1) Entities:  POCO class (Plain old C# object) is normal class, no attribute describing 
            
                Example:
                - A POCO
                    public class Person
                    {
                        public string Name { get; set; }

                        public int Age { get; set; }
                    }

                - isn't POCO
                    public class PersonComponent : System.ComponentModel.Component
                    {
                        [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
                        public string Name { get; set; }

                        public int Age { get; set; }
                    }
            
            1.3.2) Infrastructure: Communicate with database
    
    2) Open/ Closed Principle (OCP)
    - Software entities (modules, classes, functions) should be open for extension but closed for modification.
    
        + "Open for extension" means that the module's behavious can be extended. When the requirements of the application change, you can extended the module with new behavious that adapt to those change.
        
        + "Closed for modification" means the source code of such a module is inviolate when you extend the module's behavious.
        You shouldn't refactor and modify the existing code for the module until bugs are detected. The reason is the source code has already passed the unit testing, so changing it can effect other existing functionalities.
        