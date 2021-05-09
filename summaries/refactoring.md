# Refactoring

## Theory

### Clean Code Features

- Obvious or other programmers
- Doesn’t contain duplication
- Contains a minimal number of classes and other moving parts
- Passes all tests
- Easier and cheaper to maintain

### Technical Debt

- Write a not clean code to advance fast, but eventually this is slowing down the project until pay the debt (clean the code)

### When to reactor

- Rule of Three

  - First time: Just get it done
  - Second time: cringe at having to repeat but do the same thing anyway.
  - Third time: Start refactoring

- When adding a feature
- When fixing a bug
- During a code review

### Resulted after refactoring

- A cleaner code (if the code stays unclear, you lost time doing it)
- Without new features (features is one thing and refactoring is another, do not mix these two in the same modification)
- All existing test must pass (maybe you need to refactor the test too)

### Code Smells

#### Bloaters

- Big code/method/class that is hard work with

| Name                | How to Identify                                                                                                                                                                           | Possible Techniques |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- |
| Long Method         | More than 10 lines (general rule) <br> Has comment inside (if requires explanations, should be in another method with a clear name) <br> Has complex conditional (if-then/else or switch) |
| Large Class         | Many fields/methods/lines of code                                                                                                                                                         |                     |
| Primitive Code      | Doesn't use objects and classes when should                                                                                                                                               |                     |
| Long Parameter List | More than three or four parameters for a method                                                                                                                                           |                     |
| Data Clumps         | Different parts of the code with identical groups of variables                                                                                                                            |                     |

#### Object Orientation Abusers

- Incomplete or incorrect application of object-oriented programming principles

| Name                                          | How to Identify                                                                       |
| --------------------------------------------- | ------------------------------------------------------------------------------------- |
| Alternative Classes with Different Interfaces | Two classes perform identical functions but have different method names               |
| Refused Bequest                               | Subclass that uses only some of the methods and properties inherited from its parents |
| Switch Statements                             | Complex switch operator or sequence of if statements                                  |
| Temporary Filed                               | Data in object fields almost always empty                                             |

#### Change Preventers

- To change something in one place in your code, you have to make many changes in other places too

| Name                             | How to Identify                                                                                               |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Divergent Change\*               | You find yourself having to change many unrelated methods when you make changes to a class                    |
| Parallel Inheritance Hierarchies | Whenever you create a subclass for a class, you find yourself needing to create a subclass for another class. |
| Shotgun Surgery\*                | Making any modifications requires that you make many small changes to many different classes                  |

\* _Shotgun Surgery resembles Divergent Change but is actually the opposite smell. Divergent Change is when many changes are made to a single class. Shotgun Surgery refers to when a single change is made to multiple classes simultaneously_.

#### Dispensable

| Name                   | How to Identify                                                                                             |
| ---------------------- | ----------------------------------------------------------------------------------------------------------- |
| Comments               | Allowed: Explaining why something is being implemented in a particular way or explaining complex algorithms |
| Duplicate Code         | Two code fragments look almost identical                                                                    |
| Data Class             | class that contains only fields and crude methods for accessing them (getters and setters)                  |
| Dead Code              | A variable, parameter, field, method or class is no longer used (usually because it’s obsolete).            |
| Lazy Class             | Class doesn’t do enough to earn your attention                                                              |
| Speculative Generality | There’s an unused class, method, field or parameter                                                         |

#### Couplers

- Excessive coupling between classes or excessive delegation

| Name                     | How to Identify                                                     |
| ------------------------ | ------------------------------------------------------------------- |
| Feature Envy             | A method accesses the data of another object more than its own data |
| Inappropriate Intimacy   | One class uses the internal fields and methods of another class     |
| Incomplete Library Class | Library stop meeting user needs                                     |
| Message Chains           | A series of calls resembling `$a->b()->c()->d()`                    |
| Middle Man               | A class performs only one action, delegating work to another class  |

### Refactoring Techniques

#### Composing Methods

| Name                              | Problem                                                                                                                 | Solution                                                                                                                                                                               | Implementation                                               |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| Extract Method                    | You have a code fragment that can be grouped together.                                                                  | Move this code to a separate new method (or function) and replace the old code with a call to the method.                                                                              | <https://refactoring.guru/extract-method>                    |
| Inline Method                     | Method body is more obvious than the method itself                                                                      | Replace calls to the method with the method’s content and delete the method itself                                                                                                     | <https://refactoring.guru/inline-method>                     |
| Extract Variable                  | You have an expression that’s hard to understand                                                                        | Place the result of the expression or its parts in separate variables that are self-explanatory                                                                                        | <https://refactoring.guru/extract-variable>                  |
| Inline Temp                       | temporary variable that’s assigned the result of a simple expression and nothing more                                   | Replace the references to the variable with the expression itself                                                                                                                      | <https://refactoring.guru/inline-temp>                       |
| Replace Temp with Query           | You place the result of an expression in a local variable for later use in your code                                    | Move the entire expression to a separate method and return the result from it. Query the method instead of using a variable. Incorporate the new method in other methods, if necessary | <https://refactoring.guru/replace-temp-with-query>           |
| Split Temporary Variable          | You have a local variable that’s used to store various intermediate values inside a method (except for cycle variables) | Use different variables for different values. Each variable should be responsible for only one particular thing.                                                                       | <https://refactoring.guru/split-temporary-variable>          |
| Remove Assignments to Parameters  | Some value is assigned to a parameter inside method’s body.                                                             | Use a local variable instead of a parameter.                                                                                                                                           | <https://refactoring.guru/remove-assignments-to-parameters>  |
| Replace Method with Method Object | You have a long method in which the local variables are so intertwined that you can’t apply _Extract Method_.           | Transform the method into a separate class so that the local variables become fields of the class. Then you can split the method into several methods within the same class.           | <https://refactoring.guru/replace-method-with-method-object> |
| Substitute Algorithm              | So you want to replace an existing algorithm with a new one?                                                            | Replace the body of the method that implements the algorithm with a new algorithm.                                                                                                     | <https://refactoring.guru/substitute-algorithm>              |

#### Moving Features between Objects

| Name                      | Problem                                                                                                                | Solution                                                                                                                                                                                                                            | Implementation                                       |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------- |
| Move Method               | A method is used more in another class than in its own class                                                           | Create a new method in the class that uses the method the most, then move code from the old method to there. Turn the code of the original method into a reference to the new method in the other class or else remove it entirely. | <https://refactoring.guru/move-method>               |
| Move Field                | A field is used more in another class than in its own class.                                                           | Create a field in a new class and redirect all users of the old field to it.                                                                                                                                                        | <https://refactoring.guru/move-field>                |
| Extract Class             | When one class does the work of two, awkwardness results.                                                              | Instead, create a new class and place the fields and methods responsible for the relevant functionality in it.                                                                                                                      | <https://refactoring.guru/extract-class>             |
| Inline Class              | A class does almost nothing and isn’t responsible for anything, and no additional responsibilities are planned for it. | Move all features from the class to another one.                                                                                                                                                                                    | <https://refactoring.guru/inline-class>              |
| Hide Delegate             | The client gets object B from a field or method of object А. Then the client calls a method of object B                | Create a new method in class A that delegates the call to object B. Now the client doesn’t know about, or depend on, class B.                                                                                                       | <https://refactoring.guru/hide-delegate>             |
| Remove Middle Man         | A class has too many methods that simply delegate to other objects.                                                    | Delete these methods and force the client to call the end methods directly.                                                                                                                                                         | <https://refactoring.guru/remove-middle-man>         |
| Introduce Foreign Method  | A utility class doesn’t contain the method that you need and you can’t add the method to the class.                    | Add the method to a client class and pass an object of the utility class to it as an argument.                                                                                                                                      | <https://refactoring.guru/introduce-foreign-method>  |
| Introduce Local Extension | A utility class doesn’t contain some methods that you need. But you can’t add these methods to the class.              | Create a new class containing the methods and make it either the child or wrapper of the utility class.                                                                                                                             | <https://refactoring.guru/introduce-local-extension> |

#### Organizing Data

Go back here: https://refactoring.guru/refactoring/techniques

## Sources of information

- <https://refactoring.guru/refactoring>
