# .NET Fundamentals Course

> Learn how .NET transforms your C# code into real applications: from compilation into Intermediate Language (IL), through the CLR and JIT compiler, to managed memory and the architectural decisions that separate a working app from a robust one.

## Table of Contents

| # | Lesson | Technical Focus | Status |
|---:|---|---|---|
| 01 | [How the .NET engine runs your C# code](#01-how-the-net-engine-runs-your-c-code) | Compilation, IL, CLR, JIT, and native execution | Available |
| 02 | [How .NET runs code across three operating systems](#02-how-net-runs-code-across-three-operating-systems) | Cross-platform execution, ecosystem components, IL, JIT, Native AOT, and adoption | Available |
| 03 | [Creating a console project in C#](#03-creating-a-console-project-in-c) | Console projects, `dotnet new`, `dotnet run`, syntax errors, comments, and string interpolation | Available |
| 04 | [.NET CLI commands for organizing projects](#04-net-cli-commands-for-organizing-projects) | CLI commands, project structure, `.csproj` metadata, build output, and execution order | Available |
| 05 | [`bin` and `obj` folders in .NET: what they are and when to ignore them](#05-bin-and-obj-folders-in-net-what-they-are-and-when-to-ignore-them) | Build artifacts, `.gitignore`, Git workflow, GitHub setup, and `.gitkeep` | Available |
| 06 | [Module checkpoint: quiz and base project](#06-module-checkpoint-quiz-and-base-project) | Module review, .NET ecosystem quiz, code ordering, namespaces, CLI commands, and inventory project checklist | Available |
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

## 04. .NET CLI commands for organizing projects

Knowing the essential .NET CLI commands and organizing a project from the beginning makes a real difference between code that merely works and software that can grow safely. In this lesson, we focus on the commands, folders, and project metadata every C# developer should understand.

### Summary

The .NET CLI is the main way to interact with the .NET ecosystem from the terminal. It can create projects, list templates, compile code, run applications, inspect the installed SDK, and support a clean development workflow without requiring an IDE.

A professional project also needs structure. As the codebase grows, folders such as `src`, `test`, and `docs` help separate production code, automated tests, and documentation.

### Essential .NET CLI commands

Before writing code, it is useful to confirm which SDK and runtime environment are available:

| Command | Purpose |
|---|---|
| `dotnet --version` | Shows the installed .NET SDK version. |
| `dotnet --info` | Displays detailed information about the SDK, runtimes, operating system, and architecture. |
| `dotnet new list` | Lists the available project templates. |

.NET templates are predefined project structures generated by the CLI. They give you the right starting files for a specific kind of application.

| Template | Purpose |
|---|---|
| `console` | Creates a terminal-based application. |
| `classlib` | Creates a reusable class library. |
| `webapi` | Creates a REST API project. |
| `blazor` | Creates a web UI project with Blazor. |
| `maui` | Creates a cross-platform app for mobile and desktop scenarios. |

### Build vs run

Two commands are especially important and easy to confuse:

| Command | What it does |
|---|---|
| `dotnet build` | Compiles the project and generates output files, but does not execute the application. |
| `dotnet run` | Builds the project if needed and then runs the application. |

Use `dotnet build` when you want to verify that the code compiles successfully without launching the program.

```bash
dotnet build
```

After a successful build, .NET writes compiled output into the `bin` folder. In a console project, this can include a `.dll` file under a path similar to:

```text
bin/Debug/<target-framework>/InventoryApp.dll
```

The exact target framework folder depends on the version configured in the project file.

### Recommended project structure

A project can work while still being hard to maintain. A cleaner structure separates responsibilities early:

```text
repository-root/
  src/
    InventoryApp/
      InventoryApp.csproj
      Program.cs
  test/
  docs/
  README.md
```

Common folders include:

| Folder | Purpose |
|---|---|
| `src` | Stores production source code. |
| `test` | Stores automated tests. |
| `docs` | Stores project documentation. |

This structure keeps the repository easier to navigate as more projects, tests, and documentation are added.

### Project metadata in the `.csproj` file

The `.csproj` file is the heart of a .NET project. Inside a `PropertyGroup`, you can define metadata that affects compilation, naming, versioning, and documentation.

Example:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
  <TargetFramework>net10.0</TargetFramework>
  <AssemblyName>InventoryApp</AssemblyName>
  <RootNamespace>InventoryApp</RootNamespace>
  <Version>1.0.0.0</Version>
  <Description>Inventory management console application.</Description>
</PropertyGroup>
```

Important properties:

| Property | Purpose |
|---|---|
| `AssemblyName` | Defines the name of the generated assembly or executable output. |
| `RootNamespace` | Defines the root namespace used to organize code. |
| `Version` | Defines the project version. |
| `Description` | Provides a short description of the project. |

A namespace works like a folder for code. It helps avoid class name conflicts when a project grows or when multiple libraries are used together.

### Reading project metadata from code

Project metadata can also be inspected at runtime with reflection. The `System.Reflection` namespace provides APIs for reading assembly information from the running application.

Example:

```csharp
using System.Reflection;

Assembly assembly = Assembly.GetExecutingAssembly();
Version? version = assembly.GetName().Version;

Console.WriteLine($"Application version: {version}");
```

If the `.csproj` contains a version such as `1.0.0.0`, the application can read and print that value when it runs.

The version must use a valid numeric format. Replacing version numbers with letters will cause the project to fail during build or execution because .NET expects structured version values.

### Why instruction order matters in C#

C# executes statements in order. That means each line depends on what was declared or imported before it.

A typical flow is:

1. Import the required libraries with `using`.
2. Declare variables by calling the methods you need.
3. Print or use the final result.

For example:

```csharp
using System.Reflection;

Assembly assembly = Assembly.GetExecutingAssembly();
Version? version = assembly.GetName().Version;

Console.WriteLine($"Application version: {version}");
```

If you try to use `assembly` before declaring it, the compiler will report an error. In programming, order is part of correctness.

### Key ideas

- The .NET CLI lets you inspect, create, build, and run projects from the terminal.
- `dotnet --version`, `dotnet --info`, and `dotnet new list` help verify your environment.
- `dotnet build` compiles without running the application.
- `dotnet run` compiles and executes the application.
- A clean repository structure usually separates `src`, `test`, and `docs`.
- The `.csproj` file stores important project metadata.
- Reflection can read assembly metadata at runtime.
- C# instructions must be ordered correctly because later lines depend on earlier declarations.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| CLI | Command Line Interface, used to interact with .NET from the terminal. |
| Template | A predefined project structure generated by `dotnet new`. |
| `bin` | Folder containing compiled build output. |
| `obj` | Folder containing intermediate build files. |
| Assembly | A compiled .NET unit, such as a `.dll` or executable. |
| Namespace | A logical container for organizing code and avoiding naming conflicts. |
| Reflection | A .NET capability for inspecting metadata about code at runtime. |
| Semantic versioning | A structured numeric versioning style used to communicate software changes. |

## 05. `bin` and `obj` folders in .NET: what they are and when to ignore them

When you build or run a .NET project, the framework generates folders that many beginners do not fully understand at first. Knowing what they contain, why they are generated, and when to ignore them is part of building a clean professional workflow.

This lesson also introduces the basic Git and GitHub flow needed to protect your code and share it safely.

### Summary

.NET generates `bin` and `obj` automatically during the build process. These folders are useful locally, but they usually do not belong in source control because they can be regenerated by any developer who has the project and the .NET SDK installed.

Git should track your source code, project files, documentation, and configuration. It should not track compiled output, temporary build files, editor noise, or operating system artifacts.

### What the `bin` folder contains

The `bin` folder stores binary output generated by the build process. This is where .NET places compiled files that are ready to run or be used by the runtime.

In a console project, you may see files such as:

```text
bin/Debug/<target-framework>/InventoryApp.dll
```

A `.dll` file means **Dynamic Link Library**. In .NET, it is a compiled assembly that contains executable code and metadata. It can be loaded by the runtime and, in some scenarios, shared across multiple applications.

### What the `obj` folder contains

The `obj` folder stores intermediate build files. These are temporary files used internally by the .NET build system while compiling the project.

You should not edit files inside `obj` manually. They are implementation details of the build process and can change whenever you build, clean, restore, or run the project.

### What happens if you delete `bin` and `obj`

If you delete both folders and run the project again, .NET will regenerate them automatically:

```bash
dotnet run
```

That is why these folders are not essential inside the repository. Anyone who clones the project can recreate them with normal .NET CLI commands.

### Ignoring generated files with `.gitignore`

The `.gitignore` file tells Git which files and folders should not be tracked.

For .NET projects, it should ignore generated build artifacts such as:

```gitignore
bin/
obj/
```

A practical `.gitignore` can include several categories:

| Category | Examples |
|---|---|
| Build artifacts | `bin/`, `obj/` |
| Editor files | `.vs/`, `.vscode/` when local-only settings should not be shared |
| Temporary files | `*.tmp`, `*.log` |
| Operating system files | `.DS_Store`, `Thumbs.db` |

The goal is to keep the repository focused on files that matter for building, understanding, and maintaining the project.

### Basic Git workflow for a .NET project

After configuring `.gitignore`, you can initialize a local repository and start tracking the project:

```bash
git init
git status
git add .
git commit -m "Initial project structure and gitignore configuration"
```

Command overview:

| Command | Purpose |
|---|---|
| `git init` | Creates a new local Git repository. |
| `git status` | Shows which files are tracked, modified, staged, or untracked. |
| `git add .` | Adds current changes to the staging area. |
| `git commit -m "message"` | Creates a snapshot of the staged changes. |

Commit messages should be descriptive. A good message explains the purpose of the change, not just that something changed.

### Publishing the project to GitHub

Keeping the code only on your computer is risky. If the machine fails, the work can be lost. GitHub gives you a remote copy of the repository and makes collaboration possible.

For the first push:

```bash
git branch -M main
git remote add origin <repository-url>
git push -u origin main
```

Command overview:

| Command | Purpose |
|---|---|
| `git branch -M main` | Renames or sets the main branch to `main`. |
| `git remote add origin <repository-url>` | Connects the local repository to a remote GitHub repository. |
| `git push -u origin main` | Pushes the branch and sets the upstream tracking relationship. |

When creating the repository on GitHub, avoid adding a README or `.gitignore` there if you already created them locally. That helps prevent unnecessary merge conflicts during the first push.

### What `.gitkeep` is for

Git does not track empty folders. If you want an empty folder to appear in the repository, you can place a small placeholder file inside it.

A common convention is:

```text
models/.gitkeep
```

`.gitkeep` is not an official Git feature. It is simply a community convention used to keep otherwise empty folders in source control.

### Simplifying later pushes

After the first push with:

```bash
git push -u origin main
```

future pushes to the same branch can usually be done with:

```bash
git push
```

The regular workflow becomes:

```bash
git add .
git commit -m "Describe the progress clearly"
git push
```

In professional environments, teams usually avoid pushing every change directly to `main`. A healthier workflow is to create a separate branch, open a pull request, ask for review, and merge only after the code is approved.

### Key ideas

- `bin` contains compiled output.
- `obj` contains intermediate build files.
- Both folders are generated automatically by .NET.
- Generated build folders usually belong in `.gitignore`.
- Git tracks meaningful source files, not local build artifacts.
- `git init`, `git add`, `git commit`, and `git push` are the foundation of the Git workflow.
- `git push -u origin main` sets the upstream branch for easier future pushes.
- `.gitkeep` is a convention for keeping empty folders in a repository.
- Professional teams usually work with branches and pull requests instead of committing directly to `main`.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| `bin` | Folder where .NET places compiled output. |
| `obj` | Folder where .NET places intermediate build files. |
| DLL | Dynamic Link Library, a compiled assembly that can contain executable .NET code. |
| `.gitignore` | File that tells Git which files and folders to ignore. |
| Staging area | The set of changes prepared for the next commit. |
| Commit | A snapshot of changes stored in Git history. |
| Remote | A repository hosted elsewhere, such as GitHub. |
| Upstream branch | The remote branch linked to a local branch for push and pull operations. |
| `.gitkeep` | Placeholder file commonly used to keep an otherwise empty folder in Git. |
| Pull request | A request to review and merge changes from one branch into another. |

## 06. Module checkpoint: quiz and base project

Testing what you have learned is one of the most effective ways to consolidate software development knowledge. This checkpoint closes the first module with a short quiz, a code-ordering exercise, and the initial setup for the inventory base project.

The goal is not only to remember commands, but to confirm that you understand the .NET ecosystem, the CLI, generated folders, project structure, and the execution flow from C# to machine code.

### Summary

This checkpoint reviews the most important ideas from the previous lessons:

- How C# becomes executable code through IL, CLR, and native machine code.
- The difference between `dotnet build` and `dotnet run`.
- Why `bin` and `obj` should be ignored by Git.
- How namespaces usually reflect project folder structure.
- How to create a console project with the .NET CLI.
- How to organize a simple `Program.cs` file in a readable and valid order.

### Checkpoint quiz

Try to answer each question before reading the answer. Active recall is stronger than passively reviewing notes.

#### 1. What is Intermediate Language?

**Question:** What does IL mean in the .NET execution process?

**Answer:** IL means **Intermediate Language**. It is the platform-neutral code generated by the C# compiler before the CLR executes the program.

The flow is:

```text
C# -> IL -> CLR -> Machine code
```

Understanding this chain helps you know what happens internally when a .NET program is compiled and executed.

#### 2. What is the difference between `dotnet build` and `dotnet run`?

**Answer:** `dotnet build` only compiles the project and generates build output. It does not execute the application.

`dotnet run` compiles the project if needed and then runs the application.

| Command | Behavior |
|---|---|
| `dotnet build` | Compiles only. |
| `dotnet run` | Compiles and executes. |

Use `dotnet build` when you want to verify that the code compiles without launching the program.

#### 3. Which folders should not be committed to Git?

**Answer:** `bin` and `obj`.

These folders are generated automatically during the build process. They can be recreated at any time with:

```bash
dotnet build
```

They should be included in `.gitignore`:

```gitignore
bin/
obj/
```

Committing generated folders adds unnecessary files and can create avoidable conflicts.

#### 4. How should namespaces reflect folder structure?

By convention, namespaces should usually follow the project name and folder path.

For example, if a file is located at:

```text
src/models/Product.cs
```

And the project is named `InventoryApp`, a reasonable namespace would be:

```csharp
namespace InventoryApp.Models;
```

A namespace acts as a logical container for code. It helps keep classes organized and prevents naming conflicts as the project grows.

#### 5. How do you create a named console project with the CLI?

**Answer:**

```bash
dotnet new console -n MyApp
```

Command breakdown:

| Part | Meaning |
|---|---|
| `dotnet` | Runs the .NET CLI. |
| `new` | Creates a new project from a template. |
| `console` | Uses the console application template. |
| `-n MyApp` | Sets the project name to `MyApp`. |

Getting three or more answers correct means you have a solid foundation for moving forward. If you missed more than two, review the earlier lessons before adding more project functionality.

### Code-ordering exercise

The practical exercise asks you to reconstruct a valid `Program.cs` from unordered lines.

A good order is:

1. `using` directives.
2. Comments, when they add useful context.
3. Variable declarations and method calls in logical order.
4. Console output or final behavior.

Example:

```csharp
using System.Reflection;

// Read assembly metadata from the running application.
Assembly assembly = Assembly.GetExecutingAssembly();
Version? version = assembly.GetName().Version;

Console.WriteLine($"Inventory application version: {version}");
```

The important detail is that the assembly must be retrieved before its version can be read. C# executes statements in order, so using a variable before declaring it causes a compiler error.

### Inventory base project

The final checkpoint task is to create the base inventory project using everything from the first module.

Suggested checklist:

```text
[ ] Create the console project with dotnet new console -n InventoryApp
[ ] Move the project into a clean src folder
[ ] Confirm the project runs with dotnet run
[ ] Add a .gitignore file for bin and obj
[ ] Configure basic .csproj metadata
[ ] Print the application name and version in Program.cs
[ ] Initialize Git with git init
[ ] Create the first descriptive commit
[ ] Push the project to GitHub
```

This creates a clean base before adding real inventory features in later modules.

### Key ideas

- Checkpoints help confirm understanding before moving forward.
- IL is the intermediate code generated before runtime execution.
- `dotnet build` compiles; `dotnet run` compiles and executes.
- `bin` and `obj` are generated folders and should be ignored by Git.
- Namespaces should usually reflect the project and folder structure.
- `dotnet new console -n MyApp` creates a named console application.
- `Program.cs` should be ordered so each line depends only on declarations that already exist.
- A strong base project makes future features easier to add.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| Checkpoint | A review point used to validate knowledge before continuing. |
| Active recall | A learning technique where you try to retrieve the answer before seeing it. |
| Namespace convention | A naming pattern where namespaces follow project and folder structure. |
| Base project | The initial clean version of an application before adding major features. |
| Code ordering | The practice of placing code in an order that is readable and valid for compilation. |
| Checklist | A structured list used to verify that required tasks are complete. |

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
