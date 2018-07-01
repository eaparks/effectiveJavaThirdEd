# effectiveJavaThirdEd
Trying out Items in Josh Bloch's book


## Item 1 - Consider static factory methods instead of constructors
    (not same as Factory Method from GOF pattern book)
    Plus: these methods have names unlike constructors and are thus self documenting
    Plus: not required to create a new object when invoked, unlike constructors; can help with performance
    Plus: these methods can return subtypes
    Plus: return type can vary from call to call as a fnc of input params
    Plus: class of return type need not exist when factory method written. => service provider framework. e.g., jdbc api
            service provider framework provides these:
                1. a svc interface
                        eg, jdbc: Connection
                2. provider registration api
                        eg, jdbc: DriverManager.registerDriver
                3. svc access api; clients can specify criteria or they can get default with no criteria
                        eg, jdbc: DriverManager.getConnection
                4. (optional) svc provider interface - describes factory object that produces instances of svc interface
                        eg, jdbc: Driver
    Minus: classes without public of protected constructors can't be subclassed
    Minus: hard for programmers to find; mitigate with good names:
            from, of, valueOf, instance, getInstance, create, newInstance, get<Type>, new<Type>
            
## Item 2 - Consider a builder when faced with many constructor parameters

