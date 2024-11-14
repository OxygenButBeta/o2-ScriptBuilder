# o2ScriptBuilder

`o2ScriptBuilder` is a C# utility designed to help you dynamically generate C# script files. It allows you to easily create classes with customizable features such as namespaces, access modifiers, base classes, interfaces, methods, fields, and attributes. This tool is ideal for scenarios like code generation or scaffolding.

## Features

- **Namespace Support**: Define the namespace for your class.
- **Access Modifiers**: Set the access level of the class (e.g., public, internal, private).
- **Base Class**: Set a base class for inheritance.
- **Interfaces**: Add interfaces to your class.
- **Methods and Fields**: Easily add methods and fields to the generated class.
- **Attributes**: Attach custom attributes to the class.
- **Comments**: Add class-level comments automatically.
- **Appended Structures**: Attach additional code snippets or structures.

## Installation

To use `o2ScriptBuilder`, simply add the class to your project. There are no external dependencies required.

## Usage Example

```csharp
using o2.Runtime.ScriptGeneration;

var scriptBuilder = new ScriptBuilder("MyGeneratedClass")
    .SetBaseClass<BaseClass>()
    .AddInterface<IMyInterface>()
    .AddUsing("System")
    .AddField(new FieldBuilder("myField", "int"))
    .AddMethod(new MethodBuilder("MyMethod", "void", "Console.WriteLine(\"Hello World\");"))
    .Build();

Console.WriteLine(scriptBuilder);
