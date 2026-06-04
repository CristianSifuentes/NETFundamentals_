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
| 07 | [How arguments work in C#](#07-how-arguments-work-in-c) | Command-line arguments, `args`, `switch`, stdin, stdout, interactive mode, functions, and exit codes | Available |
| 08 | [Safe conversion with `TryParse` in C#](#08-safe-conversion-with-tryparse-in-c) | Data types, user input, `Parse` vs `TryParse`, `out`, decimals, inventory calculations, and ternary expressions | Available |
| 09 | [`null` in C#: validating user input](#09-null-in-c-validating-user-input) | Null safety, nullable strings, `Trim`, `ToLowerInvariant`, default values, loops, and inventory commands | Available |
| 10 | [Exit codes and null handling in C#](#10-exit-codes-and-null-handling-in-c) | STDIN, STDOUT, exit codes, CLI arguments, primitive types, `decimal`, `TryParse`, and null-safe operators | Available |
| 11 | [Anatomy of a method in C#](#11-anatomy-of-a-method-in-c) | Return types, method names, parameters, method bodies, `void`, scope, `return`, and command processing | Available |
| 12 | [Classes, enums, and records in C#](#12-classes-enums-and-records-in-c) | Domain modeling, classes, properties, calculated properties, enums, records, immutability, and value comparison | Available |
| 13 | [Guard clauses: early validation in C#](#13-guard-clauses-early-validation-in-c) | Encapsulation, guard clauses, fail fast, private fields, property setters, refactoring, and Factory pattern | Available |
| 14 | [Checkpoint: validation, Factory, and enums](#14-checkpoint-validation-factory-and-enums) | Module review, `void`, enums, exceptions, records, classes, Factory pattern, and domain model validation | Available |
| 15 | [`List`, `Dictionary`, and `HashSet` in C#](#15-list-dictionary-and-hashset-in-c) | Collections, ordering, fast lookup, uniqueness, interfaces, repositories, and `IProductRepository` | Available |
| 16 | [LINQ for filtering, grouping, and calculating in C#](#16-linq-for-filtering-grouping-and-calculating-in-c) | In-memory repositories, LINQ queries, filtering, projection, ordering, grouping, aggregation, and inventory metrics | Available |
| 17 | To be defined | Dependency injection | Coming soon |
| 18 | [How `FileManager` works in C#](#18-how-filemanager-works-in-c) | File I/O, `System.IO`, `File`, `Directory`, `Path`, line-based operations, directory creation, and search patterns | Available |
| 19 | [JSON serialization in .NET: saving and restoring objects](#19-json-serialization-in-net-saving-and-restoring-objects) | `System.Text.Json`, serialization, deserialization, JSON options, enum converters, backups, and persistence | Available |
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

## 07. How arguments work in C#

Turning a static program into an interactive one is a major step toward building real tools. In this lesson, the inventory console app starts accepting command-line arguments, reading user input, writing output clearly, and returning proper exit codes for scripts and automation.

### Summary

Command-line programs receive information from the terminal in two main ways:

- Through **arguments**, passed after the command.
- Through **standard input**, typed by the user while the program is running.

C# console applications can process both. Arguments arrive in the `args` array, while interactive input can be read with `Console.ReadLine()`.

### Command-line arguments in .NET

When you run a program from the terminal, you can pass extra information after the command. That extra information is called command-line arguments.

With `dotnet run`, use `--` to separate arguments meant for the .NET CLI from arguments meant for your application:

```bash
dotnet run -- add laptop 500
```

Everything before `--` belongs to `dotnet`. Everything after `--` is passed to your program through `args`.

In this example:

| Index | Value |
|---|---|
| `args[0]` | `add` |
| `args[1]` | `laptop` |
| `args[2]` | `500` |

`args` is an array of strings. Each space-separated value becomes an item in that array.

### Processing arguments with `switch`

A common pattern is to check whether the program received arguments and then evaluate the first argument as the command:

```csharp
if (args.Length > 0)
{
    switch (args[0].ToLowerInvariant())
    {
        case "--help":
            ShowHelp();
            Environment.Exit(0);
            break;

        case "--version":
            Console.WriteLine("InventoryApp version 1.0.0");
            Environment.Exit(0);
            break;

        default:
            Console.WriteLine($"Unknown command: {args[0]}");
            Console.WriteLine("Use --help to see available commands.");
            Environment.Exit(2);
            break;
    }
}
```

This structure scales well. Every new command can become another `case` inside the `switch`.

### Why exit codes matter

An exit code is a number returned by a program to the operating system when it finishes. Scripts and automation tools use exit codes to decide whether the next step should continue.

Common exit codes:

| Exit code | Meaning |
|---:|---|
| `0` | Success. Everything completed correctly. |
| `1` | General error. Something failed. |
| `2` | Incorrect usage. The arguments or command are invalid. |

If the user passes an unknown command, the correct exit code is usually `2`, because the program was used incorrectly. Returning the right code helps other programs understand what happened.

### stdin and stdout

Console applications communicate through standard streams:

| Stream | Meaning | C# API |
|---|---|---|
| stdin | Standard input: what the user types. | `Console.ReadLine()` |
| stdout | Standard output: what the program prints. | `Console.WriteLine()` or `Console.Write()` |

`Console.WriteLine()` prints text and moves to the next line.

```csharp
Console.WriteLine("Inventory system ready.");
```

`Console.Write()` prints text without moving to the next line. It is useful for prompts:

```csharp
Console.Write("Enter a command: ");
```

### Building interactive mode

If the program receives no arguments, it can enter interactive mode. In this mode, the user types commands while the program is already running.

Example:

```csharp
ShowBanner();

while (true)
{
    Console.Write("Enter a command (or exit to quit): ");
    string? input = Console.ReadLine();

    if (string.IsNullOrWhiteSpace(input) ||
        input.ToLowerInvariant() == "exit")
    {
        Console.WriteLine("Goodbye.");
        Environment.Exit(0);
    }

    Console.WriteLine($"You typed: {input}");
}
```

The variable is declared as `string?` because `Console.ReadLine()` can return `null`. The question mark tells the compiler that null is an expected possibility.

### Organizing repeated output with functions

If the program prints the same banner in multiple places, extract that logic into a function:

```csharp
static void ShowBanner()
{
    Console.WriteLine("Inventory Management System");
    Console.WriteLine("Version: 1.0.0");
    Console.WriteLine($".NET runtime: {Environment.Version}");
    Console.WriteLine();
}
```

This avoids duplication and reduces coupling. When presentation logic lives in one place, it is easier to update and harder to accidentally make inconsistent.

### A simple command structure

A small but useful console program can support both direct commands and interactive use:

```csharp
if (args.Length > 0)
{
    switch (args[0].ToLowerInvariant())
    {
        case "--help":
            ShowHelp();
            return;

        case "--version":
            Console.WriteLine("InventoryApp version 1.0.0");
            return;

        default:
            Console.WriteLine($"Unknown command: {args[0]}");
            Environment.Exit(2);
            return;
    }
}

RunInteractiveMode();
```

This gives the app two paths:

- Direct command mode when arguments are provided.
- Interactive mode when no arguments are provided.

### Key ideas

- Command-line arguments let users send data when launching the program.
- With `dotnet run`, `--` separates .NET CLI arguments from application arguments.
- `args` is a string array containing the application arguments.
- A `switch` statement is a clean way to route commands.
- Exit codes communicate success, failure, or incorrect usage to the operating system.
- `Console.ReadLine()` reads stdin.
- `Console.WriteLine()` and `Console.Write()` write to stdout.
- `string?` is appropriate when a value can be null.
- Extracting repeated output into functions reduces duplication and coupling.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| Argument | A value passed to a program from the command line. |
| `args` | The string array containing command-line arguments in a C# program. |
| `switch` | A control statement used to choose behavior based on a value. |
| stdin | Standard input, usually text entered by the user. |
| stdout | Standard output, usually text printed by the program. |
| Exit code | A number returned by a program to describe how it finished. |
| Interactive mode | A mode where the program keeps running and waits for user input. |
| Nullable reference | A reference value marked with `?` to show that it may be null. |
| Coupling | A design problem where pieces of code depend too heavily on each other. |

## 08. Safe conversion with `TryParse` in C#

Working with numbers, prices, and quantities in C# requires understanding data types and safe conversion. Everything the user types into the console arrives as text, so converting that input correctly is the difference between a reliable program and one that crashes as soon as the user enters something unexpected.

### Summary

C# is a strongly typed language. Every variable has a specific type, and that type defines what kind of value the variable can store.

When input comes from the console, it starts as a `string`. If the program needs to calculate with that input, the string must be converted into a numeric type such as `int` or `decimal`. For user input, the safest approach is `TryParse`.

### Fundamental data types in C#

These are some of the most common types used in console applications:

| Type | Purpose | Example |
|---|---|---|
| `int` | Whole numbers, such as quantities or counts. | `5` |
| `decimal` | Money or precise decimal values. | `25.99M` |
| `string` | Text. | `"Laptop"` |
| `bool` | Logical values. | `true` or `false` |

For `decimal` literals, add `M` at the end:

```csharp
decimal price = 25.99M;
```

Without `M`, C# treats the number as a `double` by default. That can produce a compiler error when assigning to a `decimal`. For money, `decimal` is usually preferred because it provides better precision for financial values.

### Reading user input

Console input is read with `Console.ReadLine()`:

```csharp
Console.Write("Enter a quantity: ");
string? quantityInput = Console.ReadLine();
```

The result is `string?` because `Console.ReadLine()` can return `null`. Before doing numeric operations, the input must be converted.

### Converting input with `TryParse`

Use `int.TryParse` to convert text into an integer safely:

```csharp
Console.Write("Enter a quantity: ");
string? quantityInput = Console.ReadLine();

if (int.TryParse(quantityInput, out int quantity))
{
    Console.WriteLine($"Quantity: {quantity}");
}
else
{
    Console.WriteLine("Invalid quantity. Please enter a whole number.");
}
```

The `out` keyword lets `TryParse` create and fill the converted variable in one step.

If conversion succeeds:

- `TryParse` returns `true`.
- The `quantity` variable contains the converted number.

If conversion fails:

- `TryParse` returns `false`.
- The program continues running without throwing an exception.

### `Parse` vs `TryParse`

The difference is critical:

| Method | Behavior with invalid input |
|---|---|
| `int.Parse("ABC")` | Throws an exception and can stop the program. |
| `int.TryParse("ABC", out int result)` | Returns `false` and lets the program continue. |

Rule of thumb: **use `TryParse` whenever the value comes from the user**. User input should never be trusted to match exactly what the program expects.

### Converting prices with `decimal.TryParse`

The same pattern works for monetary values:

```csharp
Console.Write("Enter a price: ");
string? priceInput = Console.ReadLine();

if (decimal.TryParse(priceInput, out decimal price))
{
    Console.WriteLine($"Price: {price}");
}
else
{
    Console.WriteLine("Invalid price. Please enter a numeric value.");
}
```

Use `decimal` for prices because money requires predictable decimal precision.

### Calculating total inventory value

Once the quantity and price are safely converted, the calculation is direct:

```csharp
Console.Write("Enter a quantity: ");
string? quantityInput = Console.ReadLine();

Console.Write("Enter a price: ");
string? priceInput = Console.ReadLine();

if (int.TryParse(quantityInput, out int quantity) &&
    decimal.TryParse(priceInput, out decimal price))
{
    decimal totalValue = quantity * price;
    Console.WriteLine();
    Console.WriteLine($"Total inventory value: {totalValue}");
}
else
{
    Console.WriteLine();
    Console.WriteLine("Invalid input. Quantity and price must be numeric.");
}
```

Example:

```text
Quantity: 5
Price: 25
Total inventory value: 125
```

Adding blank lines with `Console.WriteLine()` can make console output easier to read, especially inside conditional branches.

### Ternary operator

The ternary operator is a compact `if/else` expression:

```csharp
string message = quantity > 0
    ? "Quantity is valid."
    : "Quantity must be greater than zero.";
```

It follows this structure:

```text
condition ? valueIfTrue : valueIfFalse
```

Use it for simple conditional assignments. If the logic becomes hard to read, use a regular `if/else` block instead.

### Key ideas

- C# variables always have a defined type.
- Console input arrives as text, usually `string?`.
- Numeric input must be converted before calculations.
- `Parse` can throw exceptions when input is invalid.
- `TryParse` returns `true` or `false` and keeps the program stable.
- Use `int` for quantities and `decimal` for money.
- Add `M` to decimal literals, such as `25.99M`.
- `out` allows `TryParse` to return the converted value.
- The ternary operator is useful for short conditional assignments.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| Strong typing | A language rule where each variable has a specific type. |
| `int` | A numeric type for whole numbers. |
| `decimal` | A numeric type for precise decimal values, commonly used for money. |
| `string` | A type for text values. |
| `bool` | A type for `true` or `false` values. |
| `Parse` | A conversion method that throws an exception when conversion fails. |
| `TryParse` | A conversion method that returns `true` or `false` instead of throwing for invalid input. |
| `out` | A keyword that allows a method to assign a value to a variable passed by reference. |
| Ternary operator | A compact conditional expression written as `condition ? trueValue : falseValue`. |

## 09. `null` in C#: validating user input

`null` has caused more bugs and runtime failures than almost any other concept in programming. Tony Hoare, who introduced null references in 1965, later called it his "billion-dollar mistake." In C#, understanding nullability is essential for writing robust code that behaves predictably when user input is missing, empty, or unexpected.

### Summary

Console applications must assume that user input can be invalid. The user might type extra spaces, use different casing, press Enter without typing anything, or produce a `null` value in some input scenarios.

C# helps you model that uncertainty with nullable reference types such as `string?`. Once a value is nullable, the code should validate it before using it.

### Why `null` matters

`null` means "no value." That sounds simple, but it becomes dangerous when code assumes a value exists and tries to use it anyway.

For example:

```csharp
string? input = Console.ReadLine();
int length = input.Length;
```

This is unsafe because `input` might be `null`. If it is, accessing `.Length` can fail.

A safer approach is:

```csharp
string? input = Console.ReadLine();
int length = input?.Length ?? 0;

Console.WriteLine($"Input length: {length}");
```

This uses two important operators:

| Operator | Meaning |
|---|---|
| `?.` | Null-conditional operator. Accesses a member only if the value is not null. |
| `??` | Null-coalescing operator. Provides a fallback value when the left side is null. |

If `input` is `null`, the length becomes `0` instead of crashing the program.

### Cleaning user input with `Trim` and `ToLowerInvariant`

Before comparing user input, normalize it:

| Method | Purpose |
|---|---|
| `Trim()` | Removes whitespace at the beginning and end of the text. |
| `ToLowerInvariant()` | Converts text to lowercase in a culture-stable way. |

Example:

```csharp
string? input = Console.ReadLine();

string command = string.IsNullOrEmpty(input)
    ? "exit"
    : input.Trim().ToLowerInvariant();
```

This code does three things:

- Checks whether the input is `null` or empty.
- Uses `"exit"` as a safe default when no value is provided.
- Trims and lowercases valid input before comparing it.

For user commands, normalization prevents `" LIST "`, `"List"`, and `"list"` from being treated as different commands.

### `IsNullOrEmpty` vs `IsNullOrWhiteSpace`

C# provides two useful validation methods:

| Method | Checks |
|---|---|
| `string.IsNullOrEmpty(value)` | `null` or `""` only. |
| `string.IsNullOrWhiteSpace(value)` | `null`, `""`, or text made only of spaces. |

For console commands, `IsNullOrWhiteSpace` is often the better choice:

```csharp
string command = string.IsNullOrWhiteSpace(input)
    ? "exit"
    : input.Trim().ToLowerInvariant();
```

This treats an empty line and a line with only spaces the same way.

### Applying null safety to the inventory project

The inventory app can support a small set of commands:

| Command | Behavior |
|---|---|
| `list` | Shows current inventory products. |
| `add` | Starts the flow to add a product. |
| `search` | Searches for existing products. |
| `exit` | Ends the program. |

The program can stay active while a boolean variable remains `true`:

```csharp
bool isRunning = true;
int productCount = 0;

while (isRunning)
{
    Console.Write("Enter a command (list, add, search, exit): ");
    string? input = Console.ReadLine();

    string command = string.IsNullOrWhiteSpace(input)
        ? "exit"
        : input.Trim().ToLowerInvariant();

    switch (command)
    {
        case "exit":
            isRunning = false;
            Console.WriteLine("Goodbye.");
            break;

        case "list":
            Console.WriteLine($"Products available: {productCount}");
            break;

        case "add":
            Console.WriteLine("Add product flow coming soon.");
            break;

        case "search":
            Console.WriteLine("Search product flow coming soon.");
            break;

        default:
            Console.WriteLine("Command not recognized. Available commands: list, add, search, exit.");
            break;
    }
}
```

This flow gives the application predictable behavior even when the user presses Enter without typing anything. In that case, the command becomes `"exit"` and the program ends cleanly.

### How the `switch` handles commands

The `switch` statement evaluates the normalized command:

- If the command is `"exit"`, the loop stops and the app prints a goodbye message.
- If the command is `"list"`, the app shows how many products are available.
- If the command is `"add"` or `"search"`, the app can call future inventory features.
- If the command is unknown, the `default` case explains what commands are available.

Because the input was normalized before the `switch`, the cases stay clean and easy to read.

### Testing the behavior

Try these inputs:

| User input | Normalized command | Result |
|---|---|---|
| `exit` | `exit` | Ends the program. |
| `list` | `list` | Shows product count. |
| ` LIST ` | `list` | Shows product count. |
| empty input | `exit` | Ends the program safely. |
| `unknown` | `unknown` | Shows command-not-recognized message. |

The key result is that invalid or missing input no longer surprises the program.

### Key ideas

- `null` means a variable has no value.
- Nullable reference types such as `string?` make possible null values explicit.
- `Console.ReadLine()` can return `null`.
- Use `?.` and `??` to safely handle missing values.
- Use `Trim()` to remove extra spaces from user input.
- Use `ToLowerInvariant()` to normalize commands before comparison.
- Use `string.IsNullOrWhiteSpace()` when blank input should be treated as missing.
- A default command such as `"exit"` can make empty input safe and predictable.
- Normalize input before passing it to a `switch`.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| `null` | A value that represents no value. |
| Nullable reference type | A reference type marked with `?`, such as `string?`, to show it may be null. |
| Null-conditional operator | `?.`, used to access members only when the value is not null. |
| Null-coalescing operator | `??`, used to provide a fallback value when something is null. |
| `Trim()` | Removes whitespace from the start and end of a string. |
| `ToLowerInvariant()` | Converts text to lowercase using culture-independent rules. |
| `IsNullOrEmpty()` | Checks whether a string is null or empty. |
| `IsNullOrWhiteSpace()` | Checks whether a string is null, empty, or only whitespace. |
| Normalization | The process of converting input into a consistent format before processing it. |

## 10. Exit codes and null handling in C#

Mastering user input, primitive data types, command-line arguments, and null-safe code is essential for building reliable C# applications. This lesson consolidates the core ideas needed to make a command-line project behave predictably in real environments.

### Summary

A console application communicates with the operating system through input, output, and completion status:

- **STDIN** receives user input.
- **STDOUT** prints program output.
- **Exit codes** tell the operating system whether the program finished successfully or failed.

Together with safe parsing and null handling, these concepts make your CLI tools easier to automate, test, and maintain.

### STDIN, STDOUT, and exit codes

When a C# console program runs, it communicates through standard channels:

| Channel | Meaning | C# example |
|---|---|---|
| STDIN | Standard input. Text entered by the user or piped from another process. | `Console.ReadLine()` |
| STDOUT | Standard output. Text printed by the program. | `Console.WriteLine()` |
| Exit code | Numeric status returned when the program ends. | `Environment.Exit(0)` |

Exit code conventions:

| Exit code | Meaning |
|---:|---|
| `0` | Successful execution. |
| `1` | General error. |
| `2` | Incorrect usage, such as invalid arguments. |

These codes are important because scripts and automation tools can use them to decide whether the next step should continue.

### Command-line arguments with `dotnet run`

When running a project with `dotnet run`, use `--` to separate arguments for the .NET CLI from arguments for your application:

```bash
dotnet run -- add laptop
```

In this example, the application receives:

| Index | Value |
|---|---|
| `args[0]` | `add` |
| `args[1]` | `laptop` |

The double dash is only a separator. It is not included in the `args` array.

This distinction matters when designing CLI applications because your code should process only the arguments intended for the program.

### Primitive types for the inventory project

The most important primitive types in this module are:

| Type | Use case |
|---|---|
| `int` | Whole numbers, such as quantities or counts. |
| `decimal` | Money and exact base-10 calculations. |
| `string` | Text, names, commands, and descriptions. |
| `bool` | True/false values, such as loop control flags. |

Example:

```csharp
int quantity = 5;
decimal price = 25.99M;
string productName = "Laptop";
bool isRunning = true;
```

### Why `decimal` is the right type for money

For product prices, prefer `decimal` instead of `double` or `float`.

`double` and `float` use binary floating-point representation. That can introduce rounding errors in financial calculations. `decimal` is designed for base-10 precision, which makes it a better fit for money.

```csharp
decimal unitPrice = 19.99M;
decimal total = unitPrice * 3;

Console.WriteLine($"Total: {total}");
```

The `M` suffix tells the compiler that the literal is a `decimal`.

### Safe string-to-number conversion

User input arrives as text. To convert it safely, use `TryParse`:

```csharp
Console.Write("Enter quantity: ");
string? input = Console.ReadLine();

if (int.TryParse(input, out var quantity))
{
    Console.WriteLine($"Quantity: {quantity}");
}
else
{
    Console.WriteLine("Invalid quantity.");
    Environment.Exit(2);
}
```

`TryParse` is safer than `Parse` or `Convert.ToInt32` for user input because it does not throw an exception when conversion fails. Instead, it returns `false`.

### Avoiding null reference exceptions

Null reference exceptions happen when code tries to use a value that does not exist. C# provides operators that make defensive code shorter and clearer.

#### Null-coalescing operator

The `??` operator returns the left value when it is not null. Otherwise, it returns the fallback value on the right.

```csharp
string? inputName = Console.ReadLine();
string name = inputName ?? "anonymous";
```

If `inputName` is `null`, `name` becomes `"anonymous"`.

#### Null-conditional operator

The `?.` operator accesses a property or method only if the value is not null.

```csharp
string? input = Console.ReadLine();
int length = input?.Length ?? 0;

Console.WriteLine($"Length: {length}");
```

If `input` is `null`, `.Length` is not accessed and the fallback value `0` is used.

### Current `Program.cs` structure

At this point, the console project can follow a clean structure:

```text
Program.cs
  1. System variables and metadata
  2. Startup banner
  3. Argument handling: --help and --version
  4. Future variables or placeholders
  5. User input with null-safe validation
  6. Helper functions such as ShowBanner and ShowHelp
```

Example outline:

```csharp
ShowBanner();

if (args.Length > 0)
{
    switch (args[0].ToLowerInvariant())
    {
        case "--help":
            ShowHelp();
            Environment.Exit(0);
            break;

        case "--version":
            Console.WriteLine("InventoryApp version 1.0.0");
            Environment.Exit(0);
            break;

        default:
            Console.WriteLine("Invalid usage. Use --help.");
            Environment.Exit(2);
            break;
    }
}

Console.Write("Enter your name: ");
string? input = Console.ReadLine();
string name = input?.Trim() ?? "anonymous";

Console.WriteLine($"Hello, {name}.");

static void ShowBanner()
{
    Console.WriteLine("Inventory Management System");
}

static void ShowHelp()
{
    Console.WriteLine("Available commands: --help, --version");
}
```

This organization keeps the application readable as it grows. The top-level flow remains easy to follow, while helper functions keep repeated behavior in one place.

### Key ideas

- STDIN is input coming into the program.
- STDOUT is output printed by the program.
- Exit codes communicate the final status of the process.
- `dotnet run -- add laptop` passes `add` and `laptop` to `args`.
- `int`, `decimal`, `string`, and `bool` are essential primitive types for this project.
- Use `decimal` for money because it avoids binary floating-point surprises.
- Use `TryParse` for user input because invalid values should not crash the app.
- Use `??` to provide fallback values when something is null.
- Use `?.` to safely access members only when an object exists.
- A clean `Program.cs` structure makes the project easier to maintain.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| STDIN | Standard input received by the program. |
| STDOUT | Standard output printed by the program. |
| Exit code | A numeric status returned to the operating system when the program ends. |
| Primitive type | A basic built-in type such as `int`, `decimal`, `string`, or `bool`. |
| Floating point | A numeric representation used by `float` and `double`, useful but not ideal for money. |
| `decimal` | A precise base-10 numeric type commonly used for financial values. |
| `TryParse` | A safe conversion method that returns `true` or `false`. |
| Null reference exception | An error caused by trying to use a value that is null. |
| `??` | Null-coalescing operator for fallback values. |
| `?.` | Null-conditional operator for safe member access. |

## 11. Anatomy of a method in C#

When a file like `Program.cs` starts growing without control, with every piece of logic mixed into one place, it is time to separate responsibilities. Methods are the fundamental tool for doing that in C#: named blocks of code that perform a specific task and can be reused whenever needed.

Understanding method anatomy, return behavior, parameters, and variable scope helps you write programs that are cleaner, safer, and easier to maintain.

### Summary

A method is a named unit of behavior. Instead of keeping all logic in the main program flow, you can extract focused actions into methods such as `ShowMenu`, `ReadInput`, `ProcessCommand`, `ListProducts`, `AddProduct`, and `SearchProduct`.

This makes the application easier to read because each method has one clear responsibility.

### The four parts of a method

Every C# method has four essential parts:

| Part | Purpose |
|---|---|
| Return type | Defines what kind of value the method gives back, such as `int`, `bool`, `string`, or `void`. |
| Method name | Describes what the method does. |
| Parameters | Values the method receives to do its work. |
| Body | The block of instructions inside `{ }`. |

Example:

```csharp
static string Greet(string name)
{
    return $"Hello, {name}";
}
```

In this method:

- `string` is the return type.
- `Greet` is the method name.
- `string name` is the parameter.
- The code inside `{ }` is the method body.

Calling it:

```csharp
string message = Greet("Juan");
Console.WriteLine(message);
```

Produces:

```text
Hello, Juan
```

### `void` methods

When a method starts with `void`, it does not return a value. Its purpose is to perform an action.

Example:

```csharp
static void ShowMenu()
{
    Console.WriteLine("Available commands:");
    Console.WriteLine("list   - Show inventory products");
    Console.WriteLine("add    - Add a product");
    Console.WriteLine("search - Search for a product");
    Console.WriteLine("exit   - Close the application");
}
```

`ShowMenu` only prints information. It does not need to send a value back to the caller, so `void` is the right return type.

### Extracting methods with clear responsibility

A practical inventory app can split the main behavior into focused methods:

| Method | Responsibility | Return type |
|---|---|---|
| `ShowMenu` | Prints available commands. | `void` |
| `ReadInput` | Reads and normalizes user input. | `string` |
| `ProcessCommand` | Routes the command to the right action. | `bool` |
| `ListProducts` | Prints inventory totals. | `void` |
| `AddProduct` | Placeholder for adding products later. | `void` |
| `SearchProduct` | Placeholder for searching products later. | `void` |

The main loop becomes much easier to understand:

```csharp
ShowBanner();

bool keepRunning = true;

while (keepRunning)
{
    ShowMenu();
    string command = ReadInput();
    keepRunning = ProcessCommand(command);
}
```

This reads almost like plain English: show the menu, read input, process the command, and keep running while needed.

### Reading input with a return value

`ReadInput` should return a `string` because its job is to capture what the user typed and give it back to the caller.

```csharp
static string ReadInput()
{
    Console.Write("Enter a command: ");
    string? input = Console.ReadLine();

    return string.IsNullOrWhiteSpace(input)
        ? "exit"
        : input.Trim().ToLowerInvariant();
}
```

The method returns a clean command:

- Empty input becomes `"exit"`.
- Extra spaces are removed.
- Text is converted to lowercase.

### Processing commands with `switch`

`ProcessCommand` receives the command as a parameter. It can return `bool` to tell the main loop whether the application should continue.

```csharp
static bool ProcessCommand(string command)
{
    switch (command)
    {
        case "exit":
            Console.WriteLine("Goodbye.");
            return false;

        case "list":
            ListProducts();
            return true;

        case "add":
            AddProduct();
            return true;

        case "search":
            SearchProduct();
            return true;

        default:
            Console.WriteLine("Command not recognized.");
            return true;
    }
}
```

Returning `false` for `exit` lets the loop stop without relying on `Environment.Exit`. That makes the code easier to test and reason about.

### Listing products

At this stage, the method can print placeholder inventory information:

```csharp
static void ListProducts()
{
    int productCount = 0;
    decimal totalValue = 0M;

    Console.WriteLine($"Products in inventory: {productCount}");
    Console.WriteLine($"Total inventory value: {totalValue}");
}
```

Later, this method can evolve to read real product data from collections, files, or databases.

### Placeholder methods

Placeholder methods let you design the structure before the full behavior exists:

```csharp
static void AddProduct()
{
    Console.WriteLine("Add product flow will be implemented later.");
}

static void SearchProduct()
{
    Console.WriteLine("Search product flow will be implemented later.");
}
```

This keeps the command structure ready for future modules.

### Variable scope

Scope defines where a variable exists and where it can be used. Variables declared inside a method belong only to that method.

Example:

```csharp
static void MethodA()
{
    int localNumber = 5;
}

static void MethodB()
{
    Console.WriteLine(localNumber); // Compiler error
}
```

`localNumber` exists only inside `MethodA`. `MethodB` cannot access it.

This protects data from accidental changes and keeps methods independent.

### Sharing values with `return`

If another method needs a value, return it explicitly:

```csharp
static int MethodA()
{
    int localNumber = 5;
    return localNumber;
}

static void MethodB()
{
    int localNumberB = MethodA();
    Console.WriteLine(localNumberB);
}
```

Now the value travels in a controlled way through the method return.

### Method order and readability

C# top-level programs often read naturally from top to bottom:

1. Start the program flow.
2. Call methods that describe the main behavior.
3. Define helper methods below.

For a method that calculates inventory value, the structure is:

```csharp
static decimal CalculateInventoryValue(int quantity, decimal price)
{
    return quantity * price;
}
```

The order is:

1. Method signature.
2. Opening brace.
3. Method body.
4. Closing brace.

### Key ideas

- Methods separate responsibilities and keep `Program.cs` easier to maintain.
- A method has a return type, name, parameters, and body.
- `void` means the method performs an action but does not return a value.
- Parameters let methods receive data.
- `return` sends a value back to the caller.
- Scope controls where variables exist.
- Local variables are only available inside the method where they are declared.
- Returning values is the safe way to share data between methods.
- Small focused methods make command-line applications easier to grow.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| Method | A named block of code that performs a specific task. |
| Return type | The type of value a method returns. |
| `void` | A return type meaning the method returns no value. |
| Parameter | A value passed into a method so it can do its work. |
| Method body | The instructions inside a method's braces. |
| `return` | A keyword used to send a value back to the caller. |
| Scope | The region of code where a variable exists and can be accessed. |
| Local variable | A variable declared inside a method or block. |
| Responsibility | The specific job a method or piece of code should handle. |

## 12. Classes, enums, and records in C#

As a project grows, managing disconnected variables becomes impractical. Robust software groups related data into well-defined structures. In C#, classes, enums, and records help model real concepts clearly and safely.

In the inventory project, these tools can represent products, product categories, product states, and suppliers.

### Summary

A product is not just a name, a price, or a quantity by itself. It is a group of related values that belong together. Instead of scattering those values across separate variables, C# lets you model them with a `class`.

Enums help restrict values to a known set, such as product categories or product status. Records are useful for data that should not change after creation, such as supplier information.

### What a class is

A class is a blueprint for creating objects. It defines what data an object has and, when needed, what behavior it provides.

Instead of writing separate variables like this:

```csharp
string name = "Laptop";
decimal price = 1200M;
int quantity = 5;
```

You can group those values into a `Product` class:

```csharp
public class Product
{
    public int Id { get; set; }
    public string Name { get; set; } = string.Empty;
    public string Description { get; set; } = string.Empty;
    public decimal Price { get; set; }
    public int Quantity { get; set; }
    public DateTime RegisteredAt { get; set; }
    public ProductCategory Category { get; set; }
    public ProductStatus Status { get; set; }

    public decimal TotalValue => Price * Quantity;

    public override string ToString()
    {
        return $"{Id} - {Name} | {Category} | {Status} | Qty: {Quantity} | Total: {TotalValue}";
    }
}
```

This gives the product one unified structure that is easier to pass around, validate, print, and extend.

### Properties, `get`, and `set`

Properties expose data on a class:

```csharp
public string Name { get; set; } = string.Empty;
```

`get` reads the value. `set` changes the value.

Not every property needs both. Some properties are calculated from other values:

```csharp
public decimal TotalValue => Price * Quantity;
```

`TotalValue` does not store a separate value. It calculates the result whenever it is accessed. This keeps the value accurate even when `Price` or `Quantity` changes.

### Overriding `ToString`

`ToString()` defines how an object is represented as text. By using `override`, you can customize the output:

```csharp
public override string ToString()
{
    return $"{Name} - {Price:C} x {Quantity}";
}
```

This is useful when printing products in the console.

### Using `DateTime`

`DateTime` represents dates and times in C#:

```csharp
public DateTime RegisteredAt { get; set; } = DateTime.Now;
```

For an inventory product, it can store when the product was registered. As the project grows, it is worth learning how `DateTime`, time zones, and formatting work because dates are common sources of subtle bugs.

### Modeling fixed values with enums

An enum is a named set of constants. It is useful when a value must come from a known list.

Example product category:

```csharp
public enum ProductCategory
{
    Electronics,
    Home,
    Clothing,
    Food,
    Tools,
    Office,
    Other
}
```

Example product status:

```csharp
public enum ProductStatus
{
    Active,
    Inactive,
    Discontinued
}
```

Enums are safer than plain strings because the compiler validates the values.

With strings, this mistake is accepted:

```csharp
string category = "electrnics";
```

With enums, invalid values are caught earlier:

```csharp
ProductCategory category = ProductCategory.Electronics;
```

To access an enum value, use dot notation:

```csharp
ProductCategory category = ProductCategory.Home;
ProductStatus status = ProductStatus.Active;
```

### XML comments

As a project grows, XML comments can document public types and members:

```csharp
/// <summary>
/// Represents a product stored in the inventory.
/// </summary>
public class Product
{
}
```

This improves readability and can be used by tooling to generate documentation or show helpful descriptions in editors.

### When to use records

Some data should not change after it is created. For that kind of data, records are a strong fit.

Example supplier:

```csharp
public record Supplier(
    int Id,
    string Name,
    string Email,
    string Phone
);
```

Records are concise and designed for immutable data models.

### Class vs record

The main differences are mutability and comparison behavior:

| Type | Best for | Default comparison |
|---|---|---|
| `class` | Data that can change over time. | Reference comparison. |
| `record` | Data that represents a stable value. | Value comparison. |

A `Product` works well as a class because its price, quantity, category, or status may change.

A `Supplier` works well as a record because supplier identity data is often treated as a stable value once created.

Example of value comparison with records:

```csharp
Supplier first = new(1, "Acme", "contact@acme.com", "555-0100");
Supplier second = new(1, "Acme", "contact@acme.com", "555-0100");

Console.WriteLine(first == second); // True
```

With regular classes, two different instances are usually considered different unless they reference the same object or custom equality is implemented.

### Suggested model folder

A clean inventory project can organize models like this:

```text
src/
  InventoryApp/
    Models/
      Product.cs
      ProductCategory.cs
      ProductStatus.cs
      Supplier.cs
```

This keeps domain types easy to find and makes the project structure match the concepts in the application.

### Key ideas

- A class is a blueprint for creating objects.
- Classes group related data and behavior into one structure.
- `get` reads a property value; `set` updates it.
- Calculated properties can use expression syntax such as `=> Price * Quantity`.
- `DateTime` represents date and time values.
- Enums define a fixed set of valid values.
- Enums are safer than strings for categories and states.
- Records are useful for data that should remain stable after creation.
- Classes compare by reference by default; records compare by value by default.
- Organizing models in a dedicated folder keeps the project easier to maintain.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| Class | A blueprint for creating objects with data and behavior. |
| Object | An instance created from a class. |
| Property | A member that exposes data on a class or record. |
| `get` | Reads a property value. |
| `set` | Updates a property value. |
| Calculated property | A property whose value is derived from other values. |
| `DateTime` | A C# type for representing date and time. |
| Enum | A named set of constant values. |
| Record | A data-focused type with value-based equality. |
| Immutability | The idea that data should not change after creation. |
| Reference comparison | Checks whether two variables point to the same object in memory. |
| Value comparison | Checks whether two values contain the same data. |

## 13. Guard clauses: early validation in C#

Protecting the data that enters your system is one of the most important decisions in object-oriented programming. When class properties accept any value without restrictions, bugs appear in unexpected places.

Guard clauses, the fail-fast principle, private fields, and the Factory pattern help make the `Product` model safer and more predictable.

### Summary

A vulnerable class lets any part of the program assign invalid values:

- Empty product names.
- Negative prices.
- Negative quantities.
- Inconsistent state created from different parts of the code.

The goal is to reject invalid data immediately, before it gets stored inside the object.

### Why public properties without validation are risky

This is easy to write, but too permissive:

```csharp
public class Product
{
    public string Name { get; set; } = string.Empty;
    public decimal Price { get; set; }
    public int Quantity { get; set; }
}
```

Any part of the code can do this:

```csharp
Product product = new();
product.Name = "";
product.Price = -100M;
product.Quantity = -5;
```

The compiler accepts it, but the object now contains invalid business data.

### Refactoring the model

Refactoring means improving the internal structure of code without changing its intended external behavior.

For the `Product` class, useful refactoring steps include:

- Convert fields to private fields.
- Add validation inside property setters.
- Remove unused properties such as `Description` if the application does not need them yet.
- Remove unused overrides such as `ToString()` when they add noise without current value.

Less unused code means fewer distractions and fewer maintenance points.

### What a guard clause is

A guard clause is a validation placed at the beginning of a method, constructor, or setter. It rejects invalid data immediately.

Example:

```csharp
if (value <= 0)
{
    throw new ArgumentOutOfRangeException(nameof(value), "Price must be greater than zero.");
}
```

The pattern is:

1. Validate the condition.
2. Throw an exception if the condition fails.
3. Assign or continue only when the value is valid.

This follows the **fail-fast** principle: fail early, fail clearly.

### Validating before doing work

Validation should happen before business logic runs.

Poor flow:

```text
Run many business steps
Calculate values
Update state
Validate at the end
```

Better flow:

```text
Validate first
Stop immediately if invalid
Run business logic only with valid data
```

If a payment amount, product price, or quantity is invalid, the program should reject it before doing unnecessary work.

### Applying guard clauses to `Product`

A safer `Product` class can use private fields and validated setters:

```csharp
public class Product
{
    private string _name = string.Empty;
    private decimal _price;
    private int _quantity;

    public int Id { get; set; }

    public string Name
    {
        get => _name;
        set
        {
            if (string.IsNullOrWhiteSpace(value))
            {
                throw new ArgumentException("Product name cannot be empty.", nameof(value));
            }

            _name = value.Trim();
        }
    }

    public decimal Price
    {
        get => _price;
        set
        {
            if (value <= 0)
            {
                throw new ArgumentOutOfRangeException(nameof(value), "Price must be greater than zero.");
            }

            _price = value;
        }
    }

    public int Quantity
    {
        get => _quantity;
        set
        {
            if (value < 0)
            {
                throw new ArgumentOutOfRangeException(nameof(value), "Quantity cannot be negative.");
            }

            _quantity = value;
        }
    }

    public ProductCategory Category { get; set; } = ProductCategory.Other;

    public decimal TotalValue => Price * Quantity;
}
```

Now the class protects itself. If another part of the program tries to assign invalid data, the setter rejects it immediately.

### Why private fields help

Private fields prevent external code from bypassing validation:

```csharp
private decimal _price;
```

External code cannot assign `_price` directly. It must go through the `Price` property, which contains the guard clause.

This is encapsulation: the class controls how its internal data is changed.

### Factory pattern

The Factory pattern centralizes object creation. Instead of spreading construction logic across the app, a factory puts creation, validation, and ID generation in one place.

A factory can live in a folder such as:

```text
src/
  InventoryApp/
    Factories/
      ProductFactory.cs
```

Example:

```csharp
public static class ProductFactory
{
    private static int _nextId = 1;

    public static Product Create(
        string name,
        decimal price,
        int quantity,
        ProductCategory category = ProductCategory.Other)
    {
        if (string.IsNullOrWhiteSpace(name))
        {
            throw new ArgumentException("Product name is required.", nameof(name));
        }

        if (price <= 0)
        {
            throw new ArgumentOutOfRangeException(nameof(price), "Price must be greater than zero.");
        }

        if (quantity < 0)
        {
            throw new ArgumentOutOfRangeException(nameof(quantity), "Quantity cannot be negative.");
        }

        return new Product
        {
            Id = _nextId++,
            Name = name,
            Price = price,
            Quantity = quantity,
            Category = category
        };
    }
}
```

`ProductFactory` is static because it does not need object instances. It simply provides shared creation behavior.

### Factory methods for business scenarios

Factories can expose different methods for different business rules.

Example:

```csharp
public static Product CreateWithStock(
    string name,
    decimal price,
    int quantity,
    ProductCategory category = ProductCategory.Other)
{
    if (quantity <= 0)
    {
        throw new ArgumentOutOfRangeException(nameof(quantity), "Stock must be greater than zero.");
    }

    return Create(name, price, quantity, category);
}
```

`CreateWithStock` adds one extra rule and then delegates the shared creation logic to `Create`.

This keeps validation reusable and avoids duplicating construction code.

### Choosing the right exception

Common validation exceptions:

| Exception | Use when |
|---|---|
| `ArgumentException` | A parameter is invalid in a general way. |
| `ArgumentNullException` | A required parameter is `null`. |
| `ArgumentOutOfRangeException` | A numeric value is outside the allowed range. |

Throwing clear exceptions helps developers understand what failed and where.

### Key ideas

- Public setters without validation can create invalid objects.
- Guard clauses reject invalid data immediately.
- Fail fast means errors should appear early and clearly.
- Private fields prevent external code from bypassing validation.
- Validated setters protect object state.
- Refactoring improves structure without changing intended behavior.
- Factories centralize object creation and validation.
- Static factories can generate IDs and enforce consistent rules.
- Factory methods can delegate to each other to avoid duplicate logic.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| Guard clause | Early validation that stops execution when data is invalid. |
| Fail fast | A principle where invalid states are rejected as soon as possible. |
| Encapsulation | Keeping internal data protected and exposing controlled access. |
| Private field | A field that can only be accessed inside its class. |
| Setter validation | Validation logic inside a property `set` block. |
| Refactoring | Improving code structure without changing intended behavior. |
| Factory pattern | A pattern that centralizes object creation logic. |
| Static class | A class that cannot be instantiated and contains shared members. |
| `ArgumentException` | Exception for invalid argument values. |
| `ArgumentOutOfRangeException` | Exception for values outside an allowed range. |

## 14. Checkpoint: validation, Factory, and enums

After several lessons building a complete domain model, this checkpoint reviews the ideas that make the inventory project more robust: method extraction, classes, records, enums, validation, guard clauses, and the Factory pattern.

The goal is not to pass a formal test. The goal is to confirm that the code compiles, protects invalid data from entering the system, and communicates intent clearly.

### Summary

This checkpoint focuses on five core questions:

- What does `void` mean?
- Why use enums for fixed values?
- What happens when an exception is thrown?
- When should a record be used instead of a class?
- How does a Factory centralize object creation?

Together, these concepts form the foundation of a safer C# domain model.

### 1. What does `void` mean in C#?

`void` means that a method does not return a value.

Example:

```csharp
static void ShowMenu()
{
    Console.WriteLine("Available commands:");
    Console.WriteLine("list");
    Console.WriteLine("add");
    Console.WriteLine("search");
    Console.WriteLine("exit");
}
```

The method performs an action by printing text, but it does not send a value back to the caller.

Compare it with a method that returns a value:

```csharp
static decimal CalculateTotal(decimal price, int quantity)
{
    return price * quantity;
}
```

`CalculateTotal` returns a `decimal`, so the caller can store or use the result.

### 2. Why use enums for fixed values?

Use an enum when a value must belong to a known, fixed set of options.

Example:

```csharp
public enum ProductCategory
{
    Electronics,
    Clothing,
    Home,
    Other
}
```

Enums are useful for values such as product categories or product states because the compiler validates them.

This is safer than strings:

```csharp
string category = "eletronics"; // Typo accepted
```

With enums:

```csharp
ProductCategory category = ProductCategory.Electronics;
```

Invalid enum names are caught at compile time.

### 3. What happens with `throw new ArgumentException()`?

`throw new ArgumentException()` creates and throws an exception. The current flow stops immediately unless the exception is handled.

Example:

```csharp
if (string.IsNullOrWhiteSpace(name))
{
    throw new ArgumentException("Product name is required.", nameof(name));
}
```

Guard clauses use `throw` to reject invalid data early. They do not ignore the error, return `null`, or simply print a message. They stop the invalid value before it spreads through the system.

### 4. When should you choose `record` instead of `class`?

Use a `record` for data that should behave like an immutable value.

Example:

```csharp
public record Supplier(
    int Id,
    string Name,
    string Email,
    string Phone
);
```

Use a `class` for data that changes during its lifecycle.

Example:

```csharp
public class Product
{
    public int Id { get; set; }
    public string Name { get; set; } = string.Empty;
    public decimal Price { get; set; }
    public int Quantity { get; set; }
}
```

General guideline:

| Type | Use when |
|---|---|
| `record` | The data is created once and should remain stable. |
| `class` | The data can change over time. |

A supplier is a good record candidate because its identity data is usually stable. A product is a good class candidate because price, quantity, and status can change.

### 5. How does a Factory centralize object creation?

The Factory pattern puts object creation in one place.

For the inventory project, `ProductFactory.Create` can handle:

- Product validation.
- Automatic ID generation.
- Default values such as `ProductCategory.Other`.
- Consistent object construction.

Example:

```csharp
Product product = ProductFactory.Create(
    name: "Laptop",
    price: 1200M,
    quantity: 3,
    category: ProductCategory.Electronics
);
```

This keeps creation logic out of random parts of the codebase.

### Practical challenge

Order the steps for creating a product with the Factory:

```text
A. Use the created product.
B. Add the required using/import so the code can access ProductFactory.
C. Call the Create method.
```

Correct order:

```text
B -> C -> A
```

First, the code needs access to `ProductFactory`. Then it can call `Create`. Finally, it can use the resulting product.

Example:

```csharp
using InventoryApp.Factories;

Product product = ProductFactory.Create(
    "Laptop",
    1200M,
    3,
    ProductCategory.Electronics
);

Console.WriteLine(product.Name);
```

### Checkpoint checklist

Use this checklist to validate your progress:

```text
[ ] Methods with actions use void when they do not return values
[ ] Methods that calculate or read data return the correct type
[ ] Product categories and states use enums instead of raw strings
[ ] Invalid constructor or setter values are rejected with exceptions
[ ] Stable data uses records when appropriate
[ ] Mutable domain entities use classes
[ ] Product creation is centralized in ProductFactory
[ ] The project compiles without errors
[ ] The model prevents invalid product data
```

### Key ideas

- `void` means a method performs an action but returns no value.
- Enums protect fixed values from typos and invalid strings.
- `throw new ArgumentException()` stops invalid flow immediately.
- Records are best for stable value-like data.
- Classes are best for mutable domain objects.
- Factories centralize creation, validation, and ID generation.
- The real checkpoint is whether the code compiles and the model protects its data.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| `void` | A method return type that means no value is returned. |
| Enum | A fixed set of named values validated by the compiler. |
| Exception | An error object that interrupts normal execution flow. |
| `throw` | A keyword used to raise an exception. |
| Record | A data-focused type that works well for stable values. |
| Class | A type used to model objects that can hold state and behavior. |
| Factory | A pattern that centralizes object creation. |
| Domain model | The code representation of business concepts and rules. |
| Validation | The process of rejecting invalid data before it enters the system. |

## 15. `List`, `Dictionary`, and `HashSet` in C#

Once products are created with a Factory, the next question is where to store them. C# collections provide different ways to organize objects depending on what the program needs: order, fast lookup, or uniqueness.

Choosing the right collection early makes the code easier to understand and more efficient as the inventory project grows.

### Summary

C# provides several collection types, but three are especially important at this stage:

- `List<T>` stores ordered items and allows access by index.
- `Dictionary<TKey, TValue>` stores key-value pairs for fast lookup.
- `HashSet<T>` stores unique values and prevents duplicates.

The inventory project can also introduce an interface, `IProductRepository`, to define how product storage should behave without locking the rest of the application to one implementation.

### `List<T>`

A `List<T>` works like a row of items. Each element has a position: `0`, `1`, `2`, and so on.

Use a list when order matters.

```csharp
List<Product> products = new();

products.Add(ProductFactory.Create("Laptop", 1200M, 3, ProductCategory.Electronics));
products.Add(ProductFactory.Create("Mouse", 25M, 10, ProductCategory.Electronics));

Product firstProduct = products[0];
Console.WriteLine(firstProduct.Name);
```

Important traits:

| Trait | Meaning |
|---|---|
| Ordered | Items keep insertion order. |
| Index-based | You can access items by position. |
| Allows duplicates | The same value can appear more than once. |

Example use cases:

- Showing the latest products.
- Keeping a sales history in chronological order.
- Displaying items in the same order they were added.

### `Dictionary<TKey, TValue>`

A `Dictionary<TKey, TValue>` works like a phone book: a key points to a value.

Use a dictionary when you need fast lookup by an identifier.

```csharp
Dictionary<int, Product> productsById = new();

Product laptop = ProductFactory.Create("Laptop", 1200M, 3, ProductCategory.Electronics);

productsById.Add(laptop.Id, laptop);

Product found = productsById[laptop.Id];
Console.WriteLine(found.Name);
```

Important traits:

| Trait | Meaning |
|---|---|
| Key-value storage | Each value is accessed through a key. |
| Fast lookup | Ideal when searching by ID. |
| Unique keys | A key can only exist once. |

Simple example:

```csharp
Dictionary<string, int> ages = new();

ages.Add("Ana", 25);
ages.Add("Luis", 30);

Console.WriteLine(ages["Ana"]);
```

For an inventory system, a dictionary is a strong fit when products are frequently searched by ID.

### `HashSet<T>`

A `HashSet<T>` stores unique values. If you try to add the same value twice, the duplicate is ignored.

Use a hash set when uniqueness matters.

```csharp
HashSet<string> colors = new();

colors.Add("red");
colors.Add("blue");
colors.Add("red");

Console.WriteLine(colors.Count); // 2
```

Important traits:

| Trait | Meaning |
|---|---|
| Unique values | Duplicates are not stored. |
| Fast membership checks | Useful for checking whether a value already exists. |
| No index access | It is not designed for position-based access. |

Example use cases:

- Unique product categories.
- Product IDs that should not repeat.
- Tags or labels where duplicates add no value.

### Choosing the right collection

| Scenario | Best collection |
|---|---|
| Store products and display them in insertion order. | `List<Product>` |
| Find products by ID frequently. | `Dictionary<int, Product>` |
| Store unique inventory categories. | `HashSet<ProductCategory>` |
| Keep sales history chronologically. | `List<Sale>` |
| Prevent repeated identifiers. | `HashSet<int>` |

The best collection depends on how the data will be used.

### Creating a list correctly

The collection must be created before calling `.Add()`:

```csharp
List<Product> products = new List<Product>();
products.Add(ProductFactory.Create("Keyboard", 80M, 4, ProductCategory.Electronics));
```

Modern C# can use target-typed `new`:

```csharp
List<Product> products = new();
products.Add(ProductFactory.Create("Keyboard", 80M, 4, ProductCategory.Electronics));
```

This will not work because the list was never instantiated:

```csharp
List<Product> products;
products.Add(ProductFactory.Create("Keyboard", 80M, 4, ProductCategory.Electronics)); // Error
```

Create first. Add second.

### What an interface is

An interface is a contract. It defines what something can do, but not how it does it.

For product storage, an interface lets the application depend on behavior instead of a specific collection type. Later, the implementation can change from an in-memory dictionary to a file, database, or API without rewriting the rest of the program.

By convention, C# interface names start with an uppercase `I`.

### Creating `IProductRepository`

A clean project can place repository contracts in a folder like this:

```text
src/
  InventoryApp/
    Repositories/
      IProductRepository.cs
```

Example interface:

```csharp
public interface IProductRepository
{
    void Add(Product product);
    Product? GetById(int id);
    IEnumerable<int> GetAllIds();
    IEnumerable<Product> GetAll();
    bool Update(Product product);
    bool Delete(int id);
    int Count { get; }
}
```

This interface defines what a product repository must support:

| Member | Purpose |
|---|---|
| `Add` | Adds a product to the repository. |
| `GetById` | Retrieves one product by ID. |
| `GetAllIds` | Returns all product IDs. |
| `GetAll` | Returns all products. |
| `Update` | Updates an existing product and returns whether it succeeded. |
| `Delete` | Removes a product by ID and returns whether it succeeded. |
| `Count` | Read-only property that exposes how many products exist. |

`Count` only has `get`, so external code can read it but cannot assign it directly.

### Why repositories help

A repository separates storage details from business logic.

Without a repository, product storage decisions spread across the program. With a repository, the rest of the application can simply ask for product operations:

```csharp
repository.Add(product);
Product? found = repository.GetById(product.Id);
bool removed = repository.Delete(product.Id);
```

The application does not need to know whether the repository uses a `Dictionary`, a file, or a database internally.

### Key ideas

- `List<T>` is ordered and supports index access.
- `List<T>` allows duplicate values.
- `Dictionary<TKey, TValue>` stores key-value pairs.
- `Dictionary<TKey, TValue>` is ideal for fast lookup by ID.
- `HashSet<T>` stores unique values only.
- Choose collections based on how data is accessed.
- A collection must be instantiated before calling `.Add()`.
- An interface defines a contract without implementation details.
- `IProductRepository` describes what product storage must do.
- A repository makes it easier to change storage implementation later.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| Collection | A type that stores multiple values or objects. |
| `List<T>` | An ordered collection with index-based access. |
| Index | A numeric position inside a list. |
| `Dictionary<TKey, TValue>` | A collection that maps keys to values. |
| Key-value pair | A relationship where a key identifies a value. |
| `HashSet<T>` | A collection that stores unique values. |
| Duplicate | A repeated value. |
| Interface | A contract that defines required members without implementation. |
| Repository | A component that manages storage and retrieval of domain objects. |
| Read-only property | A property with `get` but no external `set`. |

## 16. LINQ for filtering, grouping, and calculating in C#

Working with collections becomes much more expressive when you stop manually controlling every loop and start declaring what result you want. That is what LINQ, or Language Integrated Query, brings to C#.

In the inventory project, LINQ can solve real repository needs: searching, filtering, ordering, grouping, and calculating business metrics.

### Summary

LINQ lets you query in-memory collections using readable operators such as `Where`, `Select`, `Any`, `OrderBy`, `GroupBy`, `Sum`, `Average`, and `MaxBy`.

Instead of writing a manual loop for every search, you describe the condition or transformation you need.

```csharp
IEnumerable<Product> electronics = products
    .Where(product => product.Category == ProductCategory.Electronics);
```

The pattern is:

```text
Data source -> LINQ operator -> condition or selector -> result
```

### Implementing an in-memory repository

The starting point is `IProductRepository`, the contract that defines available product operations. An in-memory implementation can store products in a private list while the project does not yet use a database.

```csharp
public class InMemoryProductRepository : IProductRepository
{
    private readonly List<Product> _products = new();
    private int _nextId = 1;

    public int Count => _products.Count;

    public void Add(Product product)
    {
        product.Id = _nextId++;
        _products.Add(product);
    }
}
```

`Add` does not return a value because it modifies the internal collection.

### Getting one product with `FirstOrDefault`

`FirstOrDefault` returns the first item that matches a condition. If no item matches, it returns `null`.

```csharp
public Product? GetById(int id)
{
    return _products.FirstOrDefault(product => product.Id == id);
}
```

The return type is `Product?` because the product might not exist.

### Returning all products safely

The repository should protect its internal list from external modification.

```csharp
public IEnumerable<Product> GetAll()
{
    return _products.AsReadOnly();
}
```

`AsReadOnly` prevents callers from modifying the internal list directly. Returning `IEnumerable<Product>` keeps the method flexible and avoids exposing unnecessary implementation details.

### Updating products without replacing references

To update a product, first find the existing object. Then update its properties.

```csharp
public bool Update(Product product)
{
    Product? existing = GetById(product.Id);

    if (existing is null)
    {
        return false;
    }

    existing.Name = product.Name;
    existing.Price = product.Price;
    existing.Quantity = product.Quantity;
    existing.Category = product.Category;
    existing.Status = product.Status;

    return true;
}
```

This preserves the existing object reference and updates its state.

### Deleting products

`Remove` deletes the first matching object from the list:

```csharp
public bool Delete(int id)
{
    Product? existing = GetById(id);

    if (existing is null)
    {
        return false;
    }

    return _products.Remove(existing);
}
```

Returning `bool` tells the caller whether a product was actually removed.

### Filtering with `Where`

`Where` filters a collection. It is similar to `WHERE` in SQL.

Search by category:

```csharp
public IEnumerable<Product> SearchByCategory(ProductCategory category)
{
    return _products.Where(product => product.Category == category);
}
```

Search by name:

```csharp
public IEnumerable<Product> SearchByName(string text)
{
    return _products.Where(product =>
        product.Name.Contains(text, StringComparison.OrdinalIgnoreCase));
}
```

Search by price range:

```csharp
public IEnumerable<Product> SearchByPriceRange(decimal min, decimal max)
{
    return _products.Where(product =>
        product.Price >= min && product.Price <= max);
}
```

The common pattern is always source, condition, filtered result.

### Transforming results with `Select`

`Select` changes the shape of the result.

For example, to return only product names:

```csharp
public IEnumerable<string> GetNames()
{
    return _products.Select(product => product.Name);
}
```

This is like selecting one column instead of returning the full object.

### Checking conditions with `Any`

`Any` answers a yes/no question.

```csharp
public bool HasLowStock()
{
    return _products.Any(product => product.Quantity < 5);
}
```

`Any` is efficient because it stops as soon as it finds the first matching item.

### Ordering and limiting results

`OrderBy` sorts values in ascending order:

```csharp
public IEnumerable<Product> GetOrderedByPrice()
{
    return _products.OrderBy(product => product.Price);
}
```

`OrderByDescending` sorts in descending order, and `Take` limits the result:

```csharp
public IEnumerable<Product> GetMostExpensive(int count)
{
    return _products
        .OrderByDescending(product => product.Price)
        .Take(count);
}
```

This pattern is useful for top-ten lists, best sellers, or dashboard summaries.

### Grouping with `GroupBy`

`GroupBy` creates groups that share a key.

```csharp
public IEnumerable<IGrouping<ProductCategory, Product>> GroupByCategory()
{
    return _products.GroupBy(product => product.Category);
}
```

Each group has:

- A `Key`, such as `ProductCategory.Electronics`.
- The products that belong to that key.

### Counting by category with `ToDictionary`

You can convert grouped data into a dictionary:

```csharp
public Dictionary<ProductCategory, int> CountByCategory()
{
    return _products
        .GroupBy(product => product.Category)
        .ToDictionary(group => group.Key, group => group.Count());
}
```

The result maps each category to the number of products in that category.

### Aggregations: `Sum`, `Average`, and `MaxBy`

Use `Sum` to calculate total inventory value:

```csharp
public decimal GetTotalInventoryValue()
{
    return _products.Sum(product => product.Price * product.Quantity);
}
```

Use `Average` to calculate average price, but protect against empty lists:

```csharp
public decimal GetAveragePrice()
{
    if (!_products.Any())
    {
        return 0M;
    }

    return _products.Average(product => product.Price);
}
```

Use `MaxBy` to get the full product with the highest price:

```csharp
public Product? GetMostExpensiveProduct()
{
    return _products.MaxBy(product => product.Price);
}
```

The return type is nullable because the list could be empty.

### Chaining LINQ operators

LINQ becomes powerful when operators are combined.

Example: calculate inventory value by category.

```csharp
public Dictionary<ProductCategory, decimal> GetValueByCategory()
{
    return _products
        .GroupBy(product => product.Category)
        .ToDictionary(
            group => group.Key,
            group => group.Sum(product => product.Price * product.Quantity));
}
```

This groups products by category and calculates the total value inside each group.

### Low-stock queries with default parameters

Default parameters make methods flexible:

```csharp
public IEnumerable<Product> GetLowStock(int threshold = 5)
{
    return _products.Where(product => product.Quantity < threshold);
}
```

If the caller does not provide a threshold, the method uses `5`. If another rule is needed, the caller can pass a different value.

```csharp
IEnumerable<Product> defaultLowStock = repository.GetLowStock();
IEnumerable<Product> criticalStock = repository.GetLowStock(2);
```

### Key ideas

- LINQ lets you describe what data you want instead of manually looping through everything.
- `FirstOrDefault` returns a matching item or `null`.
- `AsReadOnly` protects internal lists from external modification.
- `Where` filters data.
- `Select` transforms data.
- `Any` checks whether at least one item matches a condition.
- `OrderBy`, `OrderByDescending`, and `Take` sort and limit results.
- `GroupBy` organizes data by a shared key.
- `ToDictionary` converts grouped results into key-value pairs.
- `Sum`, `Average`, and `MaxBy` calculate useful inventory metrics.
- Default parameters make query methods more flexible.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| LINQ | Language Integrated Query, a C# feature for querying collections. |
| Lambda expression | A compact function expression such as `product => product.Price > 100`. |
| `Where` | Filters a collection by condition. |
| `Select` | Projects each item into a new shape or value. |
| `Any` | Returns `true` if at least one item matches. |
| `OrderBy` | Sorts values in ascending order. |
| `OrderByDescending` | Sorts values in descending order. |
| `Take` | Limits how many items are returned. |
| `GroupBy` | Groups items by a shared key. |
| `ToDictionary` | Converts data into a dictionary. |
| Aggregation | A calculation over a collection, such as sum, average, or maximum. |
| `IEnumerable<T>` | A sequence that can be iterated over. |

## 18. How `FileManager` works in C#

Reading and writing files is an essential skill in professional C# applications. Configuration files, audit logs, exports, imports, and local persistence all depend on reliable file handling.

In this lesson, the project introduces a `FileManager` class that centralizes file operations with `System.IO`.

### Summary

When file operations are scattered throughout the application, duplication grows and maintenance becomes harder. A `FileManager` class keeps all file-related logic in one place.

This follows a simple design idea: `Program.cs` should consume file operations, while `FileManager` should execute them.

The main `System.IO` types used are:

| Type | Purpose |
|---|---|
| `File` | Handles file operations such as read, write, append, delete, and exists checks. |
| `Directory` | Handles folders and subdirectories. |
| `Path` | Helps build and normalize paths across operating systems. |

### Why centralize file logic

Centralizing file operations gives the project several benefits:

- Less duplicated code.
- Easier maintenance.
- One place to change if storage rules evolve.
- Cleaner `Program.cs`.
- A clearer separation of responsibilities.

This supports the Single Responsibility Principle: each class should have one main reason to change.

### Creating a `FileManager`

A clean project can place infrastructure code in a dedicated folder:

```text
src/
  InventoryApp/
    Infrastructure/
      FileManager.cs
```

Example class outline:

```csharp
namespace InventoryApp.Infrastructure;

public class FileManager
{
    public void Write(string path, string content)
    {
        File.WriteAllText(path, content);
    }

    public string Read(string path)
    {
        return File.ReadAllText(path);
    }
}
```

`FileManager` exposes simple methods while `System.IO` performs the actual file operations.

### Writing files with `WriteAllText`

`File.WriteAllText` writes content to a file.

```csharp
public void Write(string path, string content)
{
    File.WriteAllText(path, content);
}
```

Behavior:

- If the file does not exist, it creates it.
- If the file already exists, it overwrites the existing content.
- It opens, writes, and closes the file automatically.

This is useful for simple save operations where the full file content should be replaced.

### Reading files with `ReadAllText`

`File.ReadAllText` reads the entire file as one string:

```csharp
public string Read(string path)
{
    return File.ReadAllText(path);
}
```

This is simple and effective for small or medium files. If the file does not exist, it throws `FileNotFoundException`.

For very large files, prefer line-by-line processing to avoid loading everything into memory at once.

### Appending content

`File.AppendAllText` adds content at the end of an existing file without deleting previous content:

```csharp
public void Append(string path, string content)
{
    File.AppendAllText(path, content);
}
```

This is useful for:

- Application logs.
- Audit records.
- Activity history.
- Incremental text output.

### Checking whether a file exists

`File.Exists` returns `true` or `false` without opening the file:

```csharp
public bool Exists(string path)
{
    return File.Exists(path);
}
```

Use this before reading a file when missing files are expected:

```csharp
if (fileManager.Exists("inventory.txt"))
{
    string content = fileManager.Read("inventory.txt");
    Console.WriteLine(content);
}
```

### Deleting files

`File.Delete` removes a file:

```csharp
public void Delete(string path)
{
    File.Delete(path);
}
```

If the file does not exist, `File.Delete` does not throw an exception. It can still fail for other reasons, such as insufficient permissions.

### Reading and writing lines

Sometimes a file should be treated as lines instead of one large text block.

`File.ReadAllLines` returns an array where each element is one line:

```csharp
public string[] ReadLines(string path)
{
    return File.ReadAllLines(path);
}
```

`File.WriteAllLines` receives a collection and writes each item as its own line:

```csharp
public void WriteLines(string path, IEnumerable<string> lines)
{
    File.WriteAllLines(path, lines);
}
```

Example:

```csharp
string[] products =
{
    "Laptop",
    "Mouse",
    "Keyboard"
};

fileManager.WriteLines("products.txt", products);
```

This creates a file where each product appears on a separate line.

### Creating directories

`Directory.CreateDirectory` creates a folder:

```csharp
public void CreateDirectory(string path)
{
    Directory.CreateDirectory(path);
}
```

Behavior:

- If the folder already exists, it does not throw.
- If parent folders do not exist, it creates them too.

For example, creating `data/inventory` also creates `data` if needed.

### Searching files by pattern

`Directory.GetFiles` returns files that match a search pattern:

```csharp
public string[] GetFiles(string directoryPath, string searchPattern)
{
    return Directory.GetFiles(directoryPath, searchPattern);
}
```

Examples of search patterns:

| Pattern | Meaning |
|---|---|
| `*.txt` | All text files. |
| `*.json` | All JSON files. |
| `inventory-*` | Files whose names start with `inventory-`. |

The `*` character means "match anything."

### Using `FileManager` from `Program.cs`

Example:

```csharp
using InventoryApp.Infrastructure;

FileManager fileManager = new();

fileManager.Write("inventory.txt", "Inventory updated");

string content = fileManager.Read("inventory.txt");
Console.WriteLine(content);
```

This confirms that writing and reading work through one centralized abstraction.

### Complete `FileManager` example

```csharp
namespace InventoryApp.Infrastructure;

public class FileManager
{
    public void Write(string path, string content)
    {
        File.WriteAllText(path, content);
    }

    public string Read(string path)
    {
        return File.ReadAllText(path);
    }

    public void Append(string path, string content)
    {
        File.AppendAllText(path, content);
    }

    public bool Exists(string path)
    {
        return File.Exists(path);
    }

    public void Delete(string path)
    {
        File.Delete(path);
    }

    public string[] ReadLines(string path)
    {
        return File.ReadAllLines(path);
    }

    public void WriteLines(string path, IEnumerable<string> lines)
    {
        File.WriteAllLines(path, lines);
    }

    public void CreateDirectory(string path)
    {
        Directory.CreateDirectory(path);
    }

    public string[] GetFiles(string directoryPath, string searchPattern)
    {
        return Directory.GetFiles(directoryPath, searchPattern);
    }
}
```

This class now supports writing, reading, appending, checking existence, deleting, line-based work, directory creation, and pattern-based search.

### Key ideas

- File operations should be centralized instead of scattered across the app.
- `System.IO.File` handles file-level operations.
- `System.IO.Directory` handles folder operations.
- `System.IO.Path` helps with cross-platform path handling.
- `WriteAllText` creates or overwrites a file.
- `ReadAllText` reads a full file as a string.
- `AppendAllText` adds content without deleting existing text.
- `ReadAllLines` returns a line array.
- `WriteAllLines` writes each item as a separate line.
- `CreateDirectory` is safe to call even if the directory already exists.
- `GetFiles` can search with patterns such as `*.txt` or `*.json`.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| `System.IO` | .NET namespace for file and directory operations. |
| `File` | Static class for working with files. |
| `Directory` | Static class for working with folders. |
| `Path` | Static class for building and normalizing file paths. |
| `WriteAllText` | Writes a full string to a file, replacing existing content. |
| `ReadAllText` | Reads an entire file as a string. |
| `AppendAllText` | Adds text to the end of a file. |
| `ReadAllLines` | Reads a file into an array of lines. |
| `WriteAllLines` | Writes a collection as separate lines. |
| Search pattern | A file-matching expression such as `*.txt`. |
| Persistence | Saving data so it remains available after the program ends. |

## 19. JSON serialization in .NET: saving and restoring objects

Converting in-memory objects into persistent files, and then restoring them without losing information, is a core skill in modern applications. In .NET, `System.Text.Json` provides a native, fast, and complete solution for working with JSON.

JSON is widely used for APIs, configuration files, local storage, logs, integrations, and communication between systems.

### Summary

Serialization means converting an object that exists in memory into text that can be stored on disk.

Deserialization is the opposite process: reading that text and reconstructing the original object in memory.

```text
Object in memory -> JSON text -> File on disk
File on disk -> JSON text -> Object in memory
```

For the inventory project, JSON persistence lets the application save products and load them again the next time the program runs.

### Why use `System.Text.Json`

`System.Text.Json` is built into modern .NET. That means the project can serialize and deserialize JSON without adding external dependencies.

Benefits:

- Native .NET support.
- Good performance.
- Strong integration with C# types.
- Configurable naming policies.
- Support for enum converters.
- Works well for files, APIs, and DTOs.

### Creating `JsonInventoryStorage`

The storage class belongs in the infrastructure layer because it deals with persistence details:

```text
src/
  InventoryApp/
    Infrastructure/
      JsonInventoryStorage.cs
```

Its responsibility is focused: save and load inventory data as JSON, while delegating raw file operations to `FileManager`.

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;

namespace InventoryApp.Infrastructure;

public class JsonInventoryStorage
{
    private readonly FileManager _fileManager;
    private readonly JsonSerializerOptions _options;

    public JsonInventoryStorage()
    {
        _fileManager = new FileManager();
        _options = CreateOptions();
    }
}
```

The class uses two private read-only fields:

| Field | Purpose |
|---|---|
| `_fileManager` | Reads and writes JSON files. |
| `_options` | Stores JSON serialization settings. |

A constructor does not return a value and must have the same name as the class.

### Configuring serialization options

`JsonSerializerOptions` controls how JSON is produced and read.

```csharp
private static JsonSerializerOptions CreateOptions()
{
    JsonSerializerOptions options = new()
    {
        WriteIndented = true,
        PropertyNamingPolicy = JsonNamingPolicy.CamelCase
    };

    options.Converters.Add(new JsonStringEnumConverter());

    return options;
}
```

Important settings:

| Option | Purpose |
|---|---|
| `WriteIndented = true` | Formats JSON with indentation and line breaks for readability. |
| `PropertyNamingPolicy = JsonNamingPolicy.CamelCase` | Writes property names using camel case. |
| `JsonStringEnumConverter` | Serializes enum values as strings instead of numbers. |

Without `JsonStringEnumConverter`, enum values are written as numbers. With it, values such as `ProductStatus.Active` appear as readable text like `"active"` or `"Active"`, depending on configuration.

### Saving products

The `Save` method converts a list of products into JSON and writes it to a file:

```csharp
public void Save(IEnumerable<Product> products, string path)
{
    string json = JsonSerializer.Serialize(products, _options);
    _fileManager.Write(path, json);
}
```

Flow:

1. Receive products in memory.
2. Serialize them into JSON text.
3. Write the JSON to the destination path.

Example output:

```json
[
  {
    "id": 1,
    "name": "Laptop",
    "price": 1200,
    "quantity": 3,
    "category": "Electronics",
    "status": "Active"
  }
]
```

### Loading products

The `Load` method reads JSON from a file and converts it back into products:

```csharp
public List<Product> Load(string path)
{
    if (!_fileManager.Exists(path))
    {
        return new List<Product>();
    }

    string json = _fileManager.Read(path);

    return JsonSerializer.Deserialize<List<Product>>(json, _options)
        ?? new List<Product>();
}
```

Important details:

- If the file does not exist, the method returns an empty list.
- If deserialization returns `null`, the method also returns an empty list.
- The caller receives usable product data instead of raw JSON text.

### Creating backups

Before overwriting important data, a storage class can create a backup file.

```csharp
public string? CreateBackup(string path)
{
    if (!_fileManager.Exists(path))
    {
        return null;
    }

    string? directory = Path.GetDirectoryName(path);
    string fileName = Path.GetFileNameWithoutExtension(path);
    string extension = Path.GetExtension(path);
    string timestamp = DateTime.Now.ToString("yyyyMMdd-HHmmss");

    string backupFileName = $"{fileName}.backup.{timestamp}{extension}";
    string backupPath = string.IsNullOrWhiteSpace(directory)
        ? backupFileName
        : Path.Combine(directory, backupFileName);

    File.Copy(path, backupPath);

    return backupPath;
}
```

Backup flow:

1. Check whether the original file exists.
2. Extract directory, file name, and extension.
3. Generate a timestamp.
4. Build a backup path.
5. Copy the original file.
6. Return the backup path.

If the source file does not exist, returning `null` is reasonable because there is nothing to back up.

### Why use `Path`

`Path` helps build file paths safely across operating systems.

```csharp
string backupPath = Path.Combine(directory, backupFileName);
```

This is better than manually concatenating strings because Windows, Linux, and macOS use path separators differently.

### Testing JSON storage from `Program.cs`

Example:

```csharp
using InventoryApp.Infrastructure;

JsonInventoryStorage storage = new();

List<Product> products = new()
{
    new Product
    {
        Id = 1,
        Name = "Laptop",
        Price = 1200M,
        Quantity = 3,
        Category = ProductCategory.Electronics,
        Status = ProductStatus.Active,
        RegisteredAt = DateTime.Now
    },
    new Product
    {
        Id = 2,
        Name = "T-Shirt",
        Price = 19.99M,
        Quantity = 50,
        Category = ProductCategory.Clothing,
        Status = ProductStatus.Active,
        RegisteredAt = DateTime.Now
    }
};

string path = "inventory_test.json";

storage.CreateBackup(path);
storage.Save(products, path);

List<Product> restored = storage.Load(path);

foreach (Product product in restored)
{
    Console.WriteLine($"{product.Id} - {product.Name} - {product.Price} - {product.Quantity}");
}
```

This test confirms that products can be saved, restored, and displayed again.

### What happens when the model changes

JSON persistence is flexible. If the C# model later adds a property that does not exist in an older JSON file, deserialization usually does not fail. The new property receives its default value.

Example:

```csharp
public string Color { get; set; } = string.Empty;
```

If older JSON files do not include `color`, the property becomes `string.Empty` when loaded.

This makes JSON useful while a project is evolving, but it also means you should think carefully about defaults and migration rules as the application grows.

### Complete storage example

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;

namespace InventoryApp.Infrastructure;

public class JsonInventoryStorage
{
    private readonly FileManager _fileManager;
    private readonly JsonSerializerOptions _options;

    public JsonInventoryStorage()
    {
        _fileManager = new FileManager();
        _options = CreateOptions();
    }

    public void Save(IEnumerable<Product> products, string path)
    {
        string json = JsonSerializer.Serialize(products, _options);
        _fileManager.Write(path, json);
    }

    public List<Product> Load(string path)
    {
        if (!_fileManager.Exists(path))
        {
            return new List<Product>();
        }

        string json = _fileManager.Read(path);

        return JsonSerializer.Deserialize<List<Product>>(json, _options)
            ?? new List<Product>();
    }

    public string? CreateBackup(string path)
    {
        if (!_fileManager.Exists(path))
        {
            return null;
        }

        string? directory = Path.GetDirectoryName(path);
        string fileName = Path.GetFileNameWithoutExtension(path);
        string extension = Path.GetExtension(path);
        string timestamp = DateTime.Now.ToString("yyyyMMdd-HHmmss");

        string backupFileName = $"{fileName}.backup.{timestamp}{extension}";
        string backupPath = string.IsNullOrWhiteSpace(directory)
            ? backupFileName
            : Path.Combine(directory, backupFileName);

        File.Copy(path, backupPath);

        return backupPath;
    }

    private static JsonSerializerOptions CreateOptions()
    {
        JsonSerializerOptions options = new()
        {
            WriteIndented = true,
            PropertyNamingPolicy = JsonNamingPolicy.CamelCase
        };

        options.Converters.Add(new JsonStringEnumConverter());

        return options;
    }
}
```

### Key ideas

- Serialization converts objects into text that can be stored.
- Deserialization reconstructs objects from stored text.
- `System.Text.Json` is the native JSON library in modern .NET.
- `JsonSerializerOptions` controls formatting and naming behavior.
- `WriteIndented` makes JSON readable.
- `JsonNamingPolicy.CamelCase` writes property names in camel case.
- `JsonStringEnumConverter` stores enums as readable strings.
- `FileManager` can handle low-level file reads and writes.
- Backups protect data before overwriting files.
- `Path.Combine` is safer than manual path concatenation.
- Older JSON can still load when new model properties have default values.

### Essential vocabulary

| Concept | Meaning |
|---|---|
| Serialization | Converting an in-memory object into text or bytes. |
| Deserialization | Reconstructing an object from stored text or bytes. |
| JSON | A text format commonly used for data exchange and persistence. |
| `System.Text.Json` | .NET namespace for JSON serialization and deserialization. |
| `JsonSerializer` | Type used to serialize and deserialize JSON. |
| `JsonSerializerOptions` | Configuration object for JSON behavior. |
| `WriteIndented` | Option that formats JSON for readability. |
| Camel case | Naming style where the first word starts lowercase, such as `productName`. |
| `JsonStringEnumConverter` | Converter that writes enums as strings instead of numbers. |
| Backup | A copy of a file created before changing or overwriting it. |

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
