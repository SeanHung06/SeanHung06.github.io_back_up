---
layout: post
title: Go Notes
description: This is a note for while Learning golang-getting-started in Coursera
---

**[Coursera/GoLang](https://www.coursera.org/learn/golang-getting-started)**



    This is a note for while Learning golang-getting-started in Coursera

### Compilation:

* Translate instructions once before running the code → C , C++ , Java(Partially) 
* Translation occurs only once → Saves Time

### Interpretation:

* Translate instructions while code is executed -> Python , Java 
* Translation occurs every execution and Requires an interpreter

### Garbage Collection:
* Typically done by interpreters but Go is complied language 
* Automatic memory management → compromise between Interpretation and compilation 
* Manually memory management → Memory Leak→ which is there are more and more memory that is not being use

### Go Language — Weakly objected oriented language 
* Organize your code through encapsulation(封裝)
* Group together data and functions which are related
* Go doesn't use the term Class → **Instead uses structs with associated methods**

### Simplified implementation of classes 
* No inheritance
* No constructors
* No generics

### Concurrency in Go
* Go includes concurrency primitives
* Goroutines represent concurrent tasks
* Channels are used to communicate between tasks
* Select enables task synchronization
* Concurrency primitives are efficient and easy to use
