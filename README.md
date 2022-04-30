# Practices

### Access Level 
open > public > internal > fileprivate > private > final
-------------------------------------
#### Open 
Open means that you can access open classes and class members from any source file in the defining module or any module that imports that module. You can subclass an open class or override an open class member both within their defining module and any module that imports the class.

#### Public
Public is literally the same thing as open but with a subtle difference. You can only subclass a class or ovverride it’s function only from the same module. Now before we go head let’s try to understand what is a module? So your app definitely uses UIKit for example. So your app is a module that uses a module called UIKit. So in terms of public you can only subclass or ovverride functions from UIKit from UIKit! Not from your app. No panic UIKit has it all as open.

#### Internal 
Internal is default access and allows use of a function or property from any source file within the defining module but not from outside the module. So all function and properties within your app that not marked with a compiler keyword is by default marked as internal.

#### Fileprivate 
Fileprivate allows use of a function or property only within the defining source file. So the swift compiler says that the property is NOT private and that it is internal BUT you can only use it if you find your self within the same file.

#### Private 
Private is pretty simple and it allows the use of function and properties only from the enclosing declaration. Which when translated makes more sense because it keeps everything at scope level. If you want to keep some implementation details away from the public you can mark it with the private keyword.


#### Final 
Final. the final keyword is not an access level but you can add it to any of the access levels other than open to prevent subclassing or overriding. There is a potential performance improvement from this as the compiler can avoid dynamic dispatch though you can allow the compiler to infer this if you use [whole module optimization](https://www.swift.org/blog/whole-module-optimizations/)
