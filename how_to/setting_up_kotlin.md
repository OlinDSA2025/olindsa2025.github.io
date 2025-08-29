---
title: Getting Set With Kotlin
toc_sticky: true
---

## Install IntelliJ IDE

We'll be working with the [Kotlin language](https://kotlinlang.org/) (more information and history of the language available [through Wikipedia](https://en.wikipedia.org/wiki/Kotlin_(programming_language)).  The best way to get Kotlin for your computer it install the IntelliJ IDE by JetBrains.  While you can use other IDEs with Kotlin (e.g., VS Code), we strongly recommend you stick IntellIJ (as that is the official IDE for Kotlin).  You can get a free license for Jetbrains since you are part of an academic institution.

The [Getting Started page](https://kotlinlang.org/docs/getting-started.html) on the Kotlin website is the place to go to get started on your journey.  As you go through the instructions, make sure to click on the link that says ``IntelliJ IDE``.

You should also take advantage of the fact that students can get free access to IntelliJ Ultimate.  This page has some [information on how to get started with accessing these student benefits](https://www.jetbrains.com/academy/student-pack/).

## Hello World

Let's work together to create our first Kotlin Program.  Open up IntellJ, select `File` then `New` then `Project`.

Next, make sure you've selected  `Kotlin` as your language  and `Add sample code` should be checked.  Your JDK may look different from what is shown here, that's probably fine (but let me know if you run into issues).  For `Build System`, you can select any of them but Maven seems to work well in my experience).  See below for a screenshot of the new project dialog.

![A screenshot of the IntelliJ IDE showing the selection of Kotlin as the programming language](/images/new_project.png)

After you click `Create`, a window will open up with your new project.  It should look something like this.

![A screenshot of the IntelliJ IDE showing the default project code](/images/configured_project.png).

To run this program, click the arrow button near the `Current File` drop down.  You should get output that looks like this.

```
"/Applications/IntelliJ IDEA.app/Contents/jbr/Contents/Home/bin/java" -javaagent:/Applications/IntelliJ IDEA.app/Contents/lib/idea_rt.jar=61644 -Dfile.encoding=UTF-8 -Dsun.stdout.encoding=UTF-8 -Dsun.stderr.encoding=UTF-8 -classpath /Users/pruvolo/Downloads/HelloWorld/out/production/HelloWorld:/Users/pruvolo/.m2/repository/org/jetbrains/kotlin/kotlin-stdlib/2.2.0/kotlin-stdlib-2.2.0.jar:/Users/pruvolo/.m2/repository/org/jetbrains/annotations/13.0/annotations-13.0.jar MainKt
Hello, Kotlin!
i = 1
i = 2
i = 3
i = 4
i = 5

Process finished with exit code 0
```
You might be wondering what the red circle is for.  This is a breakpoint that would stop execution of your program if you were to run it under the debugger.  To test this out, click the icon of the bug (right next to the arrow).  IntelliJ will now look like this.

![The IntelliJ debugger stopped a breakpoint](/images/debugger.png)

Note that the values of the local variables are shown along with the line of code we are executing.  You can continue execution of the program using the ``resume program`` button.  For a more indepth look at the debugger, consult [the IntelliJ documentation on debugging](https://www.jetbrains.com/help/idea/debugging-code.html).

## Adding a Dependency on a Library

The process for adding a dependency on a third party library (e.g., to add some functionality not present in the Kotlin standard library) will depend on the build system.  Here is an example of how to add a dependency for the `Maven` build system (as selected in the previous section).  This should also work for `Gradle` as well.

> Before getting started, configure IntelliJ to automatically download documentation and source for any imported dependencies.  You can do this by going to `Settings` -> `Build, Execution, & Deployment` -> `Build Tools` -> `Maven` -> `Importing` and then checking Automatically download `Sources`, `Documentation`, and `Annotations`.

You can approach this in two ways.  First, you can do an ordinary Google search to find your dependency.  For example, if I want to do linear algebra things in Kotlin, I could search `Linear algebra kotlin library'.  From this list, I can usually find some instructions on how to add the library as a dependency.  Alternatively, you can search for the dependency you want to add using the official [Maven Search engine](https://search.maven.org/?eh=) or, if you want a more user-friendly experience, a community-managed [Maven Search Engine Alternative](https://mvnrepository.com/).  If I type in Linear Algebra to the site above, I get the following output.

![The search output from mvnrepository.com](/images/maven_search.png)

Next, I can pick the library I want by clicking on it and choosing a version.  Let's choose the EJML Simple Library and select the latest version (`0.44`).  There will be a selector to choose the build system you are using.  In our example of using Maven build system we can add the dependency by selecting `Maven` from the tabbed selector, copying the XML fragment (which should look like the following), and pasting it into the `<dependencies></dependencies>` section of `pom.xml`.

```xml
<!-- https://mvnrepository.com/artifact/org.ejml/ejml-simple -->
<dependency>
    <groupId>org.ejml</groupId>
    <artifactId>ejml-simple</artifactId>
    <version>0.44.0</version>
</dependency>
```

You will need to click the `Reload` button to complete the process.

To work with our dependency, let's modify our code.  If we know a type in the imported module we want to use, we can type it and the editor will automatically suggest the appropriate class to import.  Go ahead and add the following lines to the top of main 
```kotlin
val q = SimpleMatrix(3, 3)
q[0,0] = 3.0
print(q)
```

Initially, the word `SimpleMatrix` will be red since it is not imported.  You can right-click on it and select `Context Actions` and choose `Import SimpleMatrix`.  This will add the appropriate import at the top of your code.

What does this code actually do?  Let's access the documentation.  If you click on SimpleMatrix, you should see a pop-up with documentation of what that command does (in this case it creates a matrix with all 0's).  You can further explore the documentation by interacting with the links in the documentation snippet.

Some useful keyboard shortcuts for interacting with the documentation and discovering how external libraries work is as follows.

* Search Everywhere: Shift Shift 
* Quick Doc (automatically show documentation in a sidebar): macOS F1 (or Ctrl+J), Win/Linux Ctrl+Q 
* Go to Declaration / Implementation: ⌘B / ⌥⌘B (Win/Linux Ctrl+B / Ctrl+Alt+B)
* Show Usages: ⌥⌘F7 (Win/Linux Alt+F7)
* Parameter Info: ⌘P (Win/Linux Ctrl+P)
* Navigate Class / Symbol: ⌘O / ⌥⌘O (Win/Linux Ctrl+N / Ctrl+Alt+Shift+N)

## A Note about Variation in Setup

If you would like to configure your workflow differently to these steps, that is totally fine.  I leave it to you to make this decision, and I'll do my best to support you should you run into road blocks.