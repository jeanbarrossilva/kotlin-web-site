---
type: tutorial
layout: tutorial
title:  "Hello Kotlin/Native using Command Line Compiler"
description: "A look at how to compile Kotlin/Native applications using the command line compiler"
authors: 
  - Hadi Hariri
date: 2020-01-15
---

<!--- To become a How-To. Need to change type to new "HowTo" --->


## Obtaining the Compiler

The Kotlin/Native compiler is available for macOS, Linux, and Windows. It is available as a command line tool and ships as part of the standard Kotlin distribution and can be downloaded from [https://kotlinlang.org]. It supports
different targets including iOS (arm32, arm64, simulator x86_64), Windows (mingw32 and x86_64),
Linux (x86_64, arm64, MIPS), macOS (x86_64), Raspberry PI, SMT32, WASM. For the full list of targets please see the [Kotlin/Native overview](/docs/reference/native-overview.html). 

While cross-platform compilation is possible, which means using one platform to compile for a different one, 
in this case we'll be targeting the same platform we're compiling on.  

While the output of the compiler does not have any dependencies or virtual machine requirements,
the compiler itself requires [Java 1.8 or higher runtime](https://jdk.java.net/11/).

## Creating Hello Kotlin/Native

The application will print "Hello Kotlin/Native" on the standard output. In a working directory of choice, create a file named
`hello.kt` and enter the following contents:

<div class="sample" markdown="1" theme="idea" data-highlight-only>

```kotlin
fun main() {
  println("Hello Kotlin/Native!")
}
```
</div>

## Compiling the code from the console 

To compile the application use the [downloaded](https://github.com/JetBrains/kotlin/releases)
compiler to execute the following command:

```bash
kotlinc-native hello.kt -o hello
```

This should generate a `hello.kexe` (Linux and macOS) or `hello.exe` (Windows) binary file

While compilation from the console seems to be easy and clear, it
does not scale well for larger projects with hundreds of files and libraries. For real-world projects it is recommended
to use a [build system](pages/docs/tutorials/native/using-gradle.md) and [IDE](pages/docs/tutorials/native/using-intellij-idea.md).