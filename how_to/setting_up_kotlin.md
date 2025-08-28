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

Next, make sure you've selected  `Kotlin` as your language  and `Add sample code` should be checked.  Your JDK may look different from what is shown here, that's probably fine (but let me know if you run into issues).  For Build System, you can select any of them but IntelliJ seems to be the simplest in my experience.  See below for a screenshot of the new project dialog.

![A screenshot of the IntelliJ IDE showing the selection of Kotlin as the programming language](/images/new_project.png).

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