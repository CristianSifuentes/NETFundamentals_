# .NET Fundamentals Course

> Learn how .NET transforms your C# code into real applications: from compilation into Intermediate Language (IL), through the CLR and JIT compiler, to managed memory and the architectural decisions that separate a working app from a robust one.

## Table of Contents

| # | Lesson | Technical Focus | Status |
|---:|---|---|---|
| 01 | [How the .NET engine runs your C# code](#01-how-the-net-engine-runs-your-c-code) | Compilation, IL, CLR, JIT, and native execution | Available |
| 02 | To be defined | .NET platform fundamentals | Coming soon |
| 03 | To be defined | Modern C# and developer productivity | Coming soon |
| 04 | To be defined | CLI, SDK, and professional workflow | Coming soon |
| 05 | To be defined | Project and solution structure | Coming soon |
| 06 | To be defined | Types, memory, and execution model | Coming soon |
| 07 | To be defined | Object-oriented programming in C# | Coming soon |
| 08 | To be defined | Interfaces, abstractions, and contracts | Coming soon |
| 09 | To be defined | Collections, generics, and LINQ | Coming soon |
| 10 | To be defined | Error handling and exceptions | Coming soon |
| 11 | To be defined | Files, streams, and serialization | Coming soon |
| 12 | To be defined | JSON and application configuration | Coming soon |
| 13 | To be defined | Automated testing | Coming soon |
| 14 | To be defined | Debugging and diagnostics | Coming soon |
| 15 | To be defined | Garbage Collection and performance | Coming soon |
| 16 | To be defined | Async, await, and concurrency | Coming soon |
| 17 | To be defined | Dependency injection | Coming soon |
| 18 | To be defined | Logging and observability | Coming soon |
| 19 | To be defined | CLI application architecture | Coming soon |
| 20 | To be defined | Validation and console user experience | Coming soon |
| 21 | To be defined | Packaging and distribution | Coming soon |
| 22 | To be defined | Microsoft and .NET best practices | Coming soon |
| 23 | To be defined | Basic security and secret management | Coming soon |
| 24 | To be defined | Persistence and data access | Coming soon |
| 25 | To be defined | Refactoring and maintainability | Coming soon |
| 26 | To be defined | Capstone project | Coming soon |
| 27 | To be defined | Wrap-up, resources, and next steps | Coming soon |

## 01. How the .NET engine runs your C# code

Understanding what happens behind the scenes when you write C# code is essential for building efficient, maintainable, and high-performance applications. .NET does not execute the text you write directly: it transforms it, optimizes it, and adapts it to the system where the application is running.

### Summary

When you develop an application in C#, your code goes through an execution flow managed by the .NET platform. First, the compiler transforms the source code into **Intermediate Language (IL)**. Then, the **Common Language Runtime (CLR)** takes that IL and converts it into native machine code through **Just-In-Time (JIT)** compilation.

This process allows .NET applications to be cross-platform, secure, and optimized for the actual hardware they run on.

```text
C# code -> Compiler -> IL -> CLR -> JIT -> Native code -> Execution
```

### What happens when you write C# code

Every line of C# you write is part of a larger process:

- The source code is compiled into IL, a processor-independent intermediate language.
- The CLR loads assemblies and manages execution.
- The JIT compiler translates IL into native instructions right before execution.
- The runtime manages memory, security, exceptions, and process resources.

This architecture allows the same codebase to run on Windows, Linux, or macOS with a consistent developer experience.

### Why understanding compilation matters

Mastering this flow helps you make better engineering decisions:

- Identify performance bottlenecks.
- Debug complex errors with more clarity.
- Write code with a stronger awareness of memory and CPU cost.
- Design cleaner applications from the beginning.
- Better understand the behavior of tools such as `dotnet build`, `dotnet run`, and `dotnet publish`.

### The role of the CLR

The **Common Language Runtime** is the execution heart of .NET. Its main responsibilities include:

- Managing object memory.
- Running the Garbage Collector.
- Compiling IL into native code through JIT.
- Handling exceptions.
- Loading assemblies.
- Enforcing type and security rules.

Thanks to the CLR, C# combines high-level productivity with optimized execution.

### How to build fast applications with .NET

The starting point is understanding that correct syntax is not enough. A strong .NET developer knows how the runtime interprets their decisions: which objects are created, when memory is allocated, how code executes, and what impact each abstraction has.

C# provides a modern and expressive syntax, but its real power appears when you use it together with the .NET platform: robust libraries, compilation tools, advanced diagnostics, automated testing, and a runtime capable of managing critical performance concerns.

### Key ideas

- .NET converts C# into IL before the application runs.
- The CLR manages program execution.
- The JIT compiler transforms IL into optimized native code.
- Understanding the runtime improves your ability to debug, optimize, and design software.
- Great .NET applications come from strong engineering decisions, not just correct syntax.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| C# | A modern, strongly typed, object-oriented language built for the .NET platform. |
| .NET | A development platform for building cross-platform applications. |
| IL | The intermediate language generated by the C# compiler. |
| CLR | The runtime that executes and manages .NET applications. |
| JIT | The compiler that converts IL into machine code during execution. |
| Garbage Collection | The automatic memory management system used by .NET. |

## Repository Goal

This repository supports the .NET fundamentals course with notes, examples, and hands-on practice focused on building real software directly from the terminal without depending on an IDE.

## Learning Path

1. Understand how the .NET platform works.
2. Master the professional workflow with the SDK and CLI.
3. Write clean, expressive, and maintainable C#.
4. Apply testing, diagnostics, and best practices.
5. Build a command-line tool that is ready to evolve.

## Requirements

- Installed .NET SDK.
- Terminal or console of choice.
- Code editor.
- Curiosity to understand what the runtime does when nobody is watching.

## Useful Commands

```bash
dotnet --version
dotnet new console
dotnet build
dotnet run
dotnet test
```

## License

This project is available under the license included in [LICENSE](LICENSE).
