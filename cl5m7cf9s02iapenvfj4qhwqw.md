## TypeScript vs JavaScript: What's the difference?

On the off chance that you're New Developer, you might have caught wind of TypeScript, a somewhat new programming language that has acquired ubiquity since its delivery in 2012 by Microsoft.

Curiously, TypeScript isn't really an independent programming language. All things being equal, TypeScript is viewed as a superset of JavaScript.

You can imagine a superset of a programming language as an expansion that presents new highlights and grows the capacities of that language. As such, any program written in JavaScript will likewise work in TypeScript.

In this way, in the event that you definitely know JavaScript, learning TypeScript will come decently normally to you.

In this article, we'll be going over a fast summary of what TypeScript is, the reason you ought to utilize it, and a portion of the key distinctions that make it stand apart from JavaScript.


![Screenshot 2022-07-15 at 1.47.39 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657873076479/JXKaUeHDR.png align="left")

## What is JavaScript?

JavaScript ES6 (otherwise called ECMAScript 6) is a client-side, cross-stage, model based prearranging language made by Brendan Eich.

JavaScript is utilized widely in front-end web advancement to assist with building dynamic, intelligent web applications. JavaScript is progressively composed, meaning all type checking occurs during assemblage. Progressively composed dialects focus on engineer effectiveness, empowering them to compose less code to finish their tasks.

Powerfully composed dialects likewise will generally be more adaptable, however offer code that is ordinarily less upgraded in light of the fact that it should be run first to see whether any bugs are available.

JavaScript likewise runs straightforwardly in the internet browser, so no extra assets are expected to execute JavaScript code. Notwithstanding, it can in any case be overpowering to troubleshoot an outpouring of blunders at the same time rather than en route.

>Note: Other instances of progressively composed dialects incorporate Python, PHP, Perl, and Ruby.

Since its beginning in 1995, JavaScript has gone through various cycles to work on its usefulness and make programming improvements more straightforward. Presently, it could be utilized to make intuitive games!

Plain JavaScript got going as an extremely straightforward language intended to be implanted as short bits of code on a site page. This is on the grounds that, at that point, a couple of dozen lines of code were each of the internet browsers could truly deal with without becoming unusably slow.

Presently, current programs are equipped for running JavaScript applications with countless lines of code.

JavaScript likewise profits by having a huge, energetic local area, broad documentation, and a lot of libraries and systems. Moreover, JavaScript upholds numerous client-side APIs that can diminish how much code a product designer requirements to compose. Hence, JavaScript is a well-known decision for most improvement groups.

That being said, JavaScript wasn't initially implied for use in enormous activities. Thus, despite the fact that little ventures could be dependably repaired, endeavoring to troubleshoot a huge task in JavaScript could be a dreary, tedious cycle.

>Note: You may not consider JavaScript being an article-situated programming language, yet it really has incredible help for OOP!




## What is TypeScript?

TypeScript is an open-source programming language yet got going as an inward item at Microsoft in 2010. The typeScript was made openly accessible on GitHub[2] in late 2012.

Since TypeScript is viewed as a severe superset of ECMAScript 2015, any JavaScript program can be viewed as a TypeScript program too.

Dissimilar to JavaScript, TypeScript is a statically composed programming language. As a static kind checker TypeScript will review the way of behaving of specific factors before you run your program. This is the case in any event when you proclaim factors without determining their sort. In these circumstances, TypeScript can consequently appoint types to pronounced factors. This is known as type surmising and is an underlying capacity of different dialects like Kotlin, and Scala.

When a variable sort is relegated, TypeScript will implement it all through the code, which can further develop consistency, and assist with investigating possible mistakes before gathering time. The compromise for acquiring this additional help is losing a portion of the adaptability that JavaScript engineers are familiar with.

>Note: Statically-composed dialects incorporate Java, C, and C++. With static composing, the software engineer should indicate the information kind of each and every variable being announced.

## The typeScript was based on 11 plan objectives:

Microsoft recognized 11 key objectives that would drive the advancement of TypeScript.

- Statically recognize expected mistakes
- Give a method for organizing bigger collections of code
- Try not to increment program runtimes
- Arrange to spotless, unmistakable JavaScript
- Produce a language that is composable and simple to reason about
- Remain completely viable with current and future forms of JavaScript
- Save the runtime conduct of all JavaScript code
- Try not to add articulation-level punctuation
- Make TypeScript reliable, and completely erasable
- Be a cross-stage improvement instrument
- Language changes shouldn't break past adaptations of TypeScript

## Advantages of TypeScript
TypeScript provides two strong advantages over JavaScript:

**TypeScript is transpiled into JavaScript:** TypeScript modifies and replaces its own code with functioning JavaScript at compilation time, allowing advanced ECMAScript features to be used by older browsers that normally do not support them

**TypeScript can enforce static typing:** Static typing catches potential issues earlier in the development lifecycle by assigning data types to all declared variables

> Note: A polyfill is a code snippet (usually written in JavaScript) that attempts to mimic the methods of a newer feature. Polyfilling allows older browsers to support new features that are normally not supported.
A transpiler converts the source code of one language to the source code of another. In this case, methods written in TypeScript are transpiled into JavaScript so that it can run in JavaScript environments.

The TypeScript compiler is also highly configurable. There are many options for regulating different aspects of type checking and compilation. The stricter the checks, the more errors can be caught by the TypeScript compiler.

The most common TypeScript error is related to type assignability. The main goal of the type checker is to ensure that values are provided with the correct types.
Additional features

**Compatibility:** TypeScript supports virtually all JavaScript frameworks and libraries, including:

**React:** A single-page application (SPA) that uses a virtual DOM to improve memory and performance
Vue: Written in TypeScript, easy to integrate into applications progressively
Angular: Great for quick prototyping, easy testing, and optimizes server performance
Syntactic sugar: Enforcing strict types makes code easier to read because you don’t have to think about what type a variable is

### Extensive IDE support:

- Visual Studio Code
- Eclipse
- Atom
- WebStorm
- …and more!

## Disadvantages of TypeScript
There are a few drawbacks to using TypeScript, but it’s up to you to weigh them against the advantages and see if it’s right for you.

Here are a few drawbacks to consider:

**Compilation time:** TypeScript programs have longer execution speeds compared to ones written in JavaScript

**Learning curve:** TypeScript is a bit more complex than JavaScript and will require time to get used to

**Type mismatches:** Because TypeScript code is transpiled into JavaScript at runtime, you may end up with unusual errors and mismatched types

**Less flexibility:** Variables and parameters are less flexible in TypeScript

## Should I learn TypeScript?
If you’re new to web development and plan on working on smaller projects, then JavaScript is the ideal place to start.

If you already know JavaScript, then your decision will ultimately depend on whether or not certain TypeScript features appeal to you as a software developer. Depending on the context (and your priorities), it can definitely be more advantageous to use JavaScript over TypeScript sometimes.

For example, one of the most notable drawbacks of a compiled language like TypeScript is the extra amount of time it takes to execute. If keeping the compilation time brief is a high priority, then JavaScript would be the best choice.

If you care more about being able to read the code you write than how long it takes to compile, then TypeScript would have a clear advantage.

> Note: One thing to keep in mind is that TypeScript developers typically receive higher compensation on average because there are fewer of them than JavaScript developers. Regardless, it never hurts to have another feather in your cap!

## Installation

> Via npm package

First, make sure you have an IDE, the Node.js Package Manager (npm), and the TypeScript compiler. Node.js provides an environment where your TypeScript package can run.

Next, open your command prompt or a terminal and enter the following:

> npm install -g typescript

If it was installed correctly, you should be able to check which version you have with tsc -v.

Now, you can use the following command to install TypeScript into your local project as a dependency.


> npm install typescript --save-dev


 ### Via Microsoft Visual Studio Code


First, make sure you have Visual Studio installed, along with the ASP.NET web development workload.

Next:

- Open a new project in Visual Studio
- Right-click your project node in the Solution Explorer
- Click Manage NuGet Packages
- In the Browse tab, search for Microsoft.TypeScript.MSBuild
- Click Install

 In the event that your project does not support Nuget, you can also install the TypeScript extension in Visual Studio by going to Extensions > **Manage Extensions.**


