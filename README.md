# Portfolio

I have been coding avidly since 8th grade, and being in a lockdown during COVID gave me plenty more time to pursue this interest. Since then, it has changed the way I approach problems logically, and the skills with which I have to cooperate and communicate effectively.

## Languages

I have learned a plethora of languages since I started coding, to varying degrees of fluency. The following are languages which I believe myself compentent in:

- Rust
- Python
- x86/x86_64 Assembly (Intel syntax)
- C/CUDA C
- Java
- Javascript/Typescript
- Zig

## Projects

The following projects are things which I would like to exhibit in order to display either my learning progress or the depth with which I have learned various languages.

### Rust

- ### Bingushack
    - Bingushack is the name of a dll injection-based [Minecraft Java](https://www.minecraft.net/) utility mod developed by myself over the course of several years. There are 3 versions, 2 of which are now public.
    - #### Bingushack v1
        - This version of the utility mod was primarily a learning experience where I gained knowledge of how Windows processes worked behind the scenes and were able to be manipulated externally.
        - [bingushack v1 repository](https://github.com/bingushack/bingushack)
    - #### Bingushack v2
        - This version of the utility mod was previously private, and was actually quite powerful. Using my knowledge from the previous iteration of this project, I was able to structure it in an ergonomic way and make the code easily extensible for new features.
        - Using Rust's [procedural macro system](https://doc.rust-lang.org/reference/procedural-macros.html), I could streamline the development and maintenance of the entire project.
        - [bingushack v2 repository](https://github.com/majorsopa/bingushack_v2)
    - ### How it works
        - The way the public versions are run is by extending the target process' allocated memory and writing the library bytes into the extra space. This can be done by using a program like [ProcessHacker](https://github.com/fengjixuchui/ProcessHacker-2) or a custom tool such as the [injector I wrote for this](https://github.com/bingushack/bingushack-injector).
        - After the dll is written to the target memory, the DllMain function is automatically called by Windows. This is the entrypoint to the program.
        - From there the execution path varies, but in general the program would use [JNI](https://docs.oracle.com/en/java/javase/17/docs/specs/jni/index.html) and [JVMTI](https://docs.oracle.com/en/java/javase/17/docs/specs/jvmti.html) to do a variety of things with Minecraft, such as call Java methods, get Java fields, and instrument Java classes- all at runtime.