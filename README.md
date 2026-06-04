# .NET Fundamentals Course

> Learn how .NET transforms your C# code into real applications: from compilation into Intermediate Language (IL), through the CLR and JIT compiler, to managed memory and the architectural decisions that separate a working app from a robust one.

## Table of Contents

| # | Lesson | Technical Focus | Status |
|---:|---|---|---|
| 01 | [How the .NET engine runs your C# code](#01-how-the-net-engine-runs-your-c-code) | Compilation, IL, CLR, JIT, and native execution | Available |
| 02 | [How .NET runs code across three operating systems](#02-how-net-runs-code-across-three-operating-systems) | Cross-platform execution, ecosystem components, IL, JIT, Native AOT, and adoption | Available |
| 03 | [Creating a console project in C#](#03-creating-a-console-project-in-c) | Console projects, `dotnet new`, `dotnet run`, syntax errors, comments, and string interpolation | Available |
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

## 02. How .NET runs code across three operating systems

One of the strongest promises of .NET is simple but powerful: write your code once and run it on Windows, Linux, and macOS without changing the application logic. That promise is possible because .NET is more than a language. It is a full development platform with a runtime, libraries, tooling, project templates, compilers, and deployment models designed for modern software.

Understanding this architecture helps you choose the right tool for each job and avoid a common beginner mistake: mixing up .NET, C#, ASP.NET Core, and Visual Studio as if they were the same thing.

### Summary

.NET started as a Windows-only platform and evolved into a cross-platform, open-source ecosystem. Today, it supports web applications, APIs, desktop apps, mobile apps, cloud services, games, machine learning, background workers, and command-line tools.

The key idea is that C# code is compiled into **Intermediate Language (IL)** instead of being compiled directly for one processor or operating system. At runtime, the **CLR** and **JIT compiler** translate that IL into native machine code for the system where the application is running.

```text
One C# codebase -> IL -> CLR on Windows/Linux/macOS -> Native execution
```

### .NET, C#, ASP.NET Core, and Visual Studio

These names often appear together, but they have different roles:

| Name | Role |
|---|---|
| .NET | The full development platform: runtime, libraries, SDK, tools, and application models. |
| C# | The main programming language used to write instructions for .NET applications. |
| ASP.NET Core | A specialized framework inside .NET for building web apps, APIs, and services. |
| Visual Studio | A professional IDE that helps you write, debug, test, and manage .NET projects. |

You can write C# without Visual Studio. You can use .NET without ASP.NET Core. You can also build .NET applications from the terminal with the SDK and the `dotnet` CLI.

### The core components of .NET

.NET is built on three major foundations:

- **CLR (Common Language Runtime):** the execution engine that runs your code, manages memory, handles security, and coordinates execution threads.
- **BCL (Base Class Library):** a large set of prebuilt APIs for files, strings, collections, networking, HTTP requests, dates, JSON, databases, cryptography, and more.
- **SDK (Software Development Kit):** the compiler, command-line tools, templates, build system, and project creation workflow.

Together, these pieces give you a productive environment for building real applications without reinventing basic infrastructure every time.

### Languages supported by .NET

.NET supports multiple languages, but they are not equally common for new projects:

| Language | Best fit |
|---|---|
| C# | The primary language for most modern .NET development. |
| F# | Functional programming, data-heavy workloads, and specialized domain modeling. |
| Visual Basic | Mostly used for maintaining older business applications. |

If you are starting today, **C# is the default choice**. It has the largest ecosystem, strongest community support, and broadest demand in professional .NET roles.

### IL and JIT compilation

When you compile C# code, it does not immediately become processor-specific instructions. Instead, the compiler produces **Intermediate Language (IL)**. You can think of IL as a platform-neutral representation of your program.

When the application runs, the CLR reads that IL and the JIT compiler translates it into native machine code method by method, right when the code is needed. Because JIT compilation happens on the actual machine running the application, .NET can optimize execution for that specific hardware.

This model is one reason .NET can support multiple operating systems while still producing efficient native execution.

### Native AOT

JIT compilation has a small startup cost because some code is compiled when the application begins running. For most web, desktop, and business applications, that cost is minor. But startup time matters more in scenarios such as:

- Cloud microservices that need very fast cold starts.
- Serverless workloads.
- Command-line tools that should open instantly.
- Small utilities distributed as standalone executables.

**Native AOT (Ahead-of-Time)**, available in modern .NET, compiles the application directly into native machine code before deployment. The trade-off is important: you can get faster startup and a self-contained executable, but you may lose some runtime flexibility and end up with a larger final binary.

### Evolution of .NET

.NET has changed significantly over time:

| Era | What changed |
|---|---|
| .NET Framework | Released in 2002 as a Windows-only development platform. |
| .NET Core | Rebuilt as open source and cross-platform, with support for Windows, Linux, and macOS. |
| .NET 5 and later | Unified the platform under the single name `.NET`. |

Modern .NET releases follow a predictable support model:

- **LTS (Long-Term Support):** even-numbered versions with three years of support.
- **STS (Standard-Term Support):** odd-numbered versions with shorter support windows.

For production systems, especially in enterprise environments, LTS versions are usually the safest choice.

### .NET in the real world

.NET is used by large-scale companies and products because it is mature, performant, and well supported:

- Stack Overflow has historically relied on C# and .NET to handle massive web traffic.
- Microsoft Teams uses .NET across many APIs and services.
- Many Fortune 500 companies use .NET for internal systems, cloud services, and business applications.
- Unity uses C# as its main scripting language for game development.
- .NET MAUI allows teams to build mobile and desktop apps from a shared codebase.
- ML.NET brings machine learning workflows into the .NET ecosystem.

The platform is valuable because it covers many software domains with one consistent language, runtime, and tooling ecosystem.

### Key ideas

- .NET is the platform; C# is the main language; ASP.NET Core is for web; Visual Studio is an IDE.
- The CLR, BCL, and SDK are core building blocks of the .NET ecosystem.
- C# is compiled into IL, then translated to native code by the JIT compiler.
- Native AOT can improve startup time by compiling to native code before deployment.
- Modern .NET is open source, cross-platform, and widely used in professional software engineering.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| ASP.NET Core | The .NET framework for building web applications, APIs, and services. |
| BCL | The Base Class Library: reusable APIs included with .NET. |
| SDK | The tools required to build, run, test, and publish .NET applications. |
| Native AOT | A deployment model that compiles .NET code to native machine code ahead of time. |
| LTS | Long-Term Support release, recommended for production stability. |
| STS | Standard-Term Support release, useful for adopting newer features sooner. |

## 03. Creating a console project in C#

Practicing what you learn is one of the most important steps in becoming a better developer. In this lesson, we start building an inventory project from scratch using C#, the terminal, and Visual Studio Code as the main tools.

Every command and every line of code has a specific purpose. Understanding those small details early will make the rest of the course much easier to follow.

### Summary

A console application is one of the simplest ways to start working with .NET. It gives you a small, focused project where you can learn the build process, write C# code, run the program, and see compiler feedback immediately.

The basic workflow looks like this:

```bash
dotnet new console -n InventoryApp
cd InventoryApp
dotnet run
```

### Creating the console project

The starting point is the terminal. To create a new console application, use:

```bash
dotnet new console
```

This command creates the base structure of a .NET console application. If you want to create the project with a specific name, use:

```bash
dotnet new console -n InventoryApp
```

Then move into the project folder:

```bash
cd InventoryApp
```

When you list the files, you should see two important items:

| File | Purpose |
|---|---|
| `InventoryApp.csproj` | The project configuration file. It defines the target framework and project settings. |
| `Program.cs` | The source file where the application code starts. |

When you open the project in Visual Studio Code, you may also see `bin` and `obj` folders after building or running the project. These folders are generated by the build process and should not be edited manually.

### Running the application

The default `Program.cs` file usually includes a line like this:

```csharp
Console.WriteLine("Hello, World!");
```

This instruction prints text to the console. To compile and run the project, execute:

```bash
dotnet run
```

The `dotnet run` command builds the project and then runs it if compilation succeeds.

### Why semicolons matter in C#

In C#, most statements must end with a semicolon:

```csharp
Console.WriteLine("Hello, World!");
```

If you remove the semicolon, the compiler will stop the build and report a syntax error. This is a useful early lesson: C# is strict about statement structure, and compiler errors are there to help you fix problems before the application runs.

### Save before running

After fixing an error, the program may still fail if the file was not saved. The compiler reads the file from disk, not the unsaved editor state.

Before running the application again, save your changes:

- Windows/Linux: `Ctrl+S`
- macOS: `Cmd+S`

Then run:

```bash
dotnet run
```

This habit will save you from a surprisingly common beginner issue: correcting the code visually but running the previous saved version.

### Comments in C#

Comments are notes for humans. The compiler ignores them.

Single-line comments start with `//`:

```csharp
// This line is ignored by the compiler.
Console.WriteLine("Inventory application started.");
```

Use comments to explain why something exists, clarify intent, or leave helpful context for future readers. Avoid comments that only repeat what the code already says.

### String interpolation

String interpolation lets you place variables or expressions directly inside a string. To use it, add `$` before the opening quote and place values inside `{}`:

```csharp
Console.WriteLine($"Operating system: {Environment.OSVersion}");
Console.WriteLine($".NET version: {Environment.Version}");
```

In this example:

| Expression | Meaning |
|---|---|
| `Environment.OSVersion` | Returns information about the operating system. |
| `Environment.Version` | Returns the version of the .NET runtime currently running the application. |

After saving and running the project, the console displays information about the platform and .NET version. This confirms that the project can execute successfully in your local environment.

### Basic dotnet CLI commands

These are the commands practiced in this lesson:

| Command | Purpose |
|---|---|
| `dotnet new console` | Creates a new console project. |
| `dotnet new console -n InventoryApp` | Creates a new console project with a specific name. |
| `cd InventoryApp` | Moves into the project folder. |
| `dotnet run` | Builds and runs the application. |

### Key ideas

- A console project is a great starting point for learning C# and .NET.
- `Program.cs` contains the application entry code.
- The `.csproj` file stores project configuration.
- `dotnet run` compiles and executes the application.
- Missing semicolons produce compilation errors.
- Saving files before running is part of a reliable development workflow.
- Comments document code for developers, not for the compiler.
- String interpolation makes output clearer and easier to read.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| Console application | A program that runs in the terminal and interacts through text input and output. |
| `.csproj` | The C# project file that stores build and configuration settings. |
| `Program.cs` | The default source file where a simple C# application begins. |
| Compiler error | A problem detected before the application can run. |
| Statement | A complete instruction in C#, usually ending with a semicolon. |
| Comment | Text ignored by the compiler and used to document code. |
| String interpolation | A C# feature for embedding variables or expressions inside strings. |

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
