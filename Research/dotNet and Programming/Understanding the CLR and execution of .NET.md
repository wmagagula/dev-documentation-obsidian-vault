.Net is a CLR - common language runtime environment 
- an agent that manages code at execution time, providing core services: memory management, thread management, remoting, code execution and code safety verification, compilation (breaking down programs from high level to low level machine code).

- The runtime automatically takes care of managing the resources of reference objects and releasing them when they are no longer needed; resolves two of the common app errors, memory leaks (where there is no memory available for other tasks to be performed due to it not being released from the heap, since it has been incorrectly managed by a computer program -- performance is significantly reduced, causing application failure) 
- The runtime enforces code robustness by implementing a strict type and code verification infrastructure called the Common Type System (CTS)

A compiler is a computer program that translates computer code (written in one language) -- into another language (target)
- Normally this translation is from high level programming languages to a lower-level (assembly, machine, object) to create an executable program

Bytecode
- An intermediate language that requires a runtime program for execution (.Net and Java fall into this category) -- every language on the .NET platform all compile first to this intermediate language. -- similar to Java
- are compact numeric codes, constants, and references (normally numeric addresses) that encode the result of [compiler](https://en.wikipedia.org/wiki/Compiler "Compiler") parsing and performing [semantic analysis](https://en.wikipedia.org/wiki/Semantic_analysis_(compilers) "Semantic analysis (compilers)") of things like type, scope, and nesting depths of program objects.

C# compilation process
1. C# (.cs file) -> C# compiler -> Intermediate language (exe file -- bytecode)
2. Intermediate language code runs inside Common Language Runtime which has the JIT compiler running converting the IL code into native code, the byte code is compiled from any language that is supported on the .NET platform.

Assemblies in the CLR
- These are the building blocks of .NET apps
- An assembly is just precompiled .NET code which can be run by the CLR
	- It is a single unit of deployment (it can be transported to any environment that contains the CLR and it will be executed correctly there)
	- Is a collection of types and resources that are built to work together and form a logical unit of functionality
	- They provide the common language runtime with the information it needs to be aware of type implementations.
	- Has varies types of assemblies (DLL (dynamic link library) -- cannot be invoked by itself, it needs a host which has an address space, Exe -- runs in its own memory space)
	


Just In Time compilation:
 A feature called (JIT) compiling enables all managed code to run in the native machine language of the system on which it's executing. Meanwhile, the memory manager removes the possibilities of fragmented memory and increases memory locality-of-reference to further increase performance.

