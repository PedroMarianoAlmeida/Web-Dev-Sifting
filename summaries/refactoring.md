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

| Name                | How to Identify                                                                                                                                                                           |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Long Method         | More than 10 lines (general rule) <br> Has comment inside (if requires explanations, should be in another method with a clear name) <br> Has complex conditional (if-then/else or switch) |
| Large Class         | Many fields/methods/lines of code                                                                                                                                                         |
| Primitive Code      | Doesn't use objects and classes when should                                                                                                                                               |
| Long Parameter List | More than three or four parameters for a method                                                                                                                                           |
| Data Clumps         | Different parts of the code with identical groups of variables                                                                                                                            |

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

-Excessive coupling between classes or excessive delegation

| Name                     | How to Identify                                                     |
| ------------------------ | ------------------------------------------------------------------- |
| Feature Envy             | A method accesses the data of another object more than its own data |
| Inappropriate Intimacy   | One class uses the internal fields and methods of another class     |
| Incomplete Library Class | Library stop meeting user needs                                     |
| Message Chains           | A series of calls resembling `$a->b()->c()->d()`                    |
| Middle Man               | A class performs only one action, delegating work to another class  |

### Refactoring Techniques

I stopped at https://refactoring.guru/refactoring/techniques

## Sources of information

- <https://refactoring.guru/refactoring>
