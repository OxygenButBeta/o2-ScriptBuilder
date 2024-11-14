# o2 Script Builder

`o2 Script Builder` is a C# utility designed to help you dynamically generate C# script files. It allows you to easily create classes with customizable features such as namespaces, access modifiers, base classes, interfaces, methods, fields, and attributes. This tool is ideal for scenarios like code generation or scaffolding.

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
    var methodBuilder = new MethodBuilder()
        {
            AccessModifier = AccessModifier._public,
            Name = "MyMethod",
            ReturnType = typeof(int),
            Body = "Console.WriteLine(\"Hello World\");",
            ExpressionBody = false,
            MethodType = MethodType._instance
        };

        methodBuilder.AddAttribute("__DynamicallyInvokable", "")
            .AddParameter("int", "myParam")
            .AddParameter("string", "myStringParam")
            .AddOptionalParameter("int", "myOptionalParam", "-1");


        var scriptBuilder = new ScriptBuilder("MyGeneratedClass")
            .SetBaseClass<MonoBehaviour>()
            .AddInterface<IBuildable>()
            .AddUsing("System")
            .AddUsing("UnityEngine")
            .AddField(new FieldBuilder("myField", "int"))
            .AddMethod(methodBuilder)
            .Build();

        // Save the script to a file or something..

