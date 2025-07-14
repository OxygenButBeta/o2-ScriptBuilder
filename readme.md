# 🛠️ o2 Script Builder

`o2 Script Builder` is a **C# utility** designed to help you **dynamically generate C# script files** with ease. Whether you're scaffolding code or automating script creation, this tool simplifies the process of creating classes with customizable namespaces, access modifiers, base classes, interfaces, methods, fields, attributes, and more.

---

## ✨ Features

- 📦 **Namespace Support** — Define custom namespaces for your classes.  
- 🔐 **Access Modifiers** — Control class visibility (`public`, `internal`, `private`, etc.).  
- 🧬 **Inheritance** — Set base classes for your generated classes.  
- 🔗 **Interfaces** — Add multiple interfaces effortlessly.  
- 📝 **Methods & Fields** — Easily add fields and methods, with support for parameters and attributes.  
- 🎨 **Attributes** — Attach custom attributes to classes, methods, and fields.  
- 💬 **Comments** — Automatically add class-level comments for documentation.  
- ➕ **Appended Code** — Append additional custom code snippets or structures.

---

## ⚙️ Installation

Simply add the `o2 Script Builder` class files directly into your project — no external dependencies required!  

---

## 🚀 Usage Example

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

methodBuilder
    .AddAttribute("__DynamicallyInvokable", "")
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

// You can then save the generated script to a file or process it further.
