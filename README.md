<p align="center">
    <img alt="Android Interview Questions" src="https://raw.githubusercontent.com/amitshekhariitbhu/android-interview-questions/master/assets/banner-android-interview-questions.jpg">
</p>

# Android Interview Questions and Answers

> Android Interview Questions and Answers - Your Cheat Sheet For Android Interview

### Prepared and maintained by [Amit Shekhar](https://github.com/amitshekhariitbhu) - Coder | Teacher | Mentor | Open Source | IIT 2010-14

## About me

Hi, I am Amit Shekhar, Co-Founder @ [Outcome School](https://outcomeschool.com) • IIT 2010-14 • I have taught and mentored many developers, and their efforts landed them high-paying tech jobs, helped many tech companies in solving their unique problems, and created many open-source libraries being used by top companies. I am passionate about sharing knowledge through open-source, blogs, and videos.

You can connect with me on:

- [Twitter](https://twitter.com/amitiitbhu)
- [YouTube](https://www.youtube.com/@amitshekhar)
- [LinkedIn](https://www.linkedin.com/in/amit-shekhar-iitbhu)
- [GitHub](https://github.com/amitshekhariitbhu)

## **Join Outcome School and get high paying tech job: [Outcome School](https://outcomeschool.com)**

## Contents - Android Interview Questions

* [Android Interview Questions and Answers Playlist](#android-interview-questions-and-answers-playlist)
* [Kotlin Coroutines](#kotlin-coroutines)
* [Kotlin Flow API](#kotlin-flow-api)
* [Kotlin](#kotlin)
* [Android](#android)
* [Android Libraries](#android-libraries)
* [Android Architecture](#android-architecture)
* [Design Pattern](#design-pattern)
* [Android System Design](#android-system-design) and check [Android System Design Interviews](https://outcomeschool.com/blog/android-system-design-interviews) 
* [Android Unit Testing](#android-unit-testing)
* [Android Tools And Technologies](#android-tools-and-technologies)
* [Java](#java)
* [Jetpack Compose](#jetpack-compose)
* [Other Topics](#other-topics)
* [Data Structures and Algorithms](#data-structures-and-algorithms) 

### Android Interview Questions and Answers Playlist

- **Question**: What is an inline function in Kotlin?
    - **Answer**: [What is an inline function in Kotlin?](https://www.youtube.com/watch?v=GLLI8h67ryo)
    - Advantage: avoid function call overhead. Faster program execution
    - When to use inline function: when the function code is very small
- **Question**: What is the advantage of using const in Kotlin?
    - **Answer**: [What is the advantage of using const in Kotlin?](https://www.youtube.com/watch?v=3G49ivVxfkU)
    - Inline the variable and thus avoid overhead. Better performance
- **Question**: What is a reified keyword in Kotlin?
    - **Answer**: [What is a reified keyword in Kotlin?](https://www.youtube.com/watch?v=kD2T84FnTck)
    - Ask the compiler to retain the type information of an inline function
- **Question**: Suspending vs Blocking in Kotlin Coroutines
    - **Answer**: [Suspending vs Blocking in Kotlin Coroutines](https://www.youtube.com/watch?v=V2lL_aJp17I)
    - runBlocking: block current thread for waiting. It bridges the non-coroutine world and corouine world
    - Suspend: release the underlying thread for other usages
- **Question**: Launch vs Async in Kotlin Coroutines
    - **Answer**: [Launch vs Async in Kotlin Coroutines](https://www.youtube.com/watch?v=B4AfTPpCU5o)
    - The main difference between async and launch is that launch is used to start a computation that isn't expected to return a specific result. launch returns a Job that represents the coroutine. It is possible to wait until it completes by calling Job.join().
    - async starts a new coroutine and returns a Deferred object. Deferred represents a concept known by other names such as Future or Promise. It stores a computation, but it defers the moment you get the final result; it promises the result sometime in the future.
    - If any exception comes inside the launch block, it crashes the application if we have not handled it.
    - If any exception comes inside the async block, it is stored inside the resulting Deferred and is not delivered anywhere else, it will get silently dropped unless we handle it.
- **Question**: internal visibility modifier in Kotlin
    - **Answer**: [internal visibility modifier in Kotlin](https://www.youtube.com/watch?v=wOHpuf74-cI)
    - intenral: Visible in the same module
    - protected: private + subclasses
- **Question**: open keyword in Kotlin
    - **Answer**: [open keyword in Kotlin](https://www.youtube.com/watch?v=bfpNDWNE6I0
    - open: allow inheritence
    - Java: open by default. Final keyword
    - Kotlin: final by default. Open keywork
- **Question**: lateinit vs lazy in Kotlin
    - **Answer**: [lateinit vs lazy in Kotlin](https://www.youtube.com/watch?v=IU2ZktdM-fo)
    - lateinit:" don not initialize a variable at the time of declaration
    - lazy: create an object inside a class, but that object creation is expensive and that might lead to a delay in the creation of the object that is dependent on that expensive object.
- **Question**: What is Multidex in Android?
    - **Answer**: [What is Multidex in Android?](https://www.youtube.com/watch?v=R0zd8lmHnmE)
    - A configuration that allows Android apps to bypass the 64K method reference limit imposed by DEX format
- **Question**: How does the Android Push Notification system work?
    - **Answer**: [How does the Android Push Notification system work?](https://www.youtube.com/watch?v=810IFG2sWlc)
    - Firebase cloud messaging (FCM).
    - When an app is installed/opened, it registers with FCM (via Google Play Services) to obtain a unque registration token.
    - The app send the token to its application server
    - Server send messages to CFM with token
    - FCM deliver the message to device via persistent connection
    - OS: if the app is in the foreground, then directly pass data to it via onMessageReceived(). Otherwise, show a notifcation in the system tray. 
- **Question**: How does the Kotlin Multiplatform work?
    - **Answer**: [How does the Kotlin Multiplatform work?](https://www.youtube.com/watch?v=nwfNh6Kd5hI
    - Android: code is converted to the Java bytecode that can be executed in the JVM.
    - iOS: Kotlin code -> IR (Intermediate Representation) -> source code (native code executable on iOS)
- **Question**: What is a ViewModel and how is it useful?
    - **Answer**: [What is a ViewModel and how is it useful?](https://www.youtube.com/watch?v=ORtieK5f_zg)
    - Hold the data for UI
    - Handle bussiness logic
    - Process data get from data layer (maybe combine multiple sources)
    - Persist the data during configuration changes
    - Lifecycle awareness: view model is only destroyed when the activity is permanently destroyed: onCleared will be called in this case
    - Alternative solution: use saved instance, but it can only contain small data
- **Question**: Is it possible to force the Garbage Collection in Android?
    - **Answer**: [Is it possible to force Garbage Collection in Android?](https://www.youtube.com/watch?v=fPEjpFKo1-Q)
    - No. Although we can call System.gc() to request the garbage collection, it doesn't mean this request will be exeucted immeidately. JVM will decide when to do it
- **Question**: What is a JvmStatic Annotation in Kotlin?
    - **Answer**: [What is a JvmStatic Annotation in Kotlin?](https://outcomeschool.com/blog/jvmstatic-annotation-in-kotlin)
    - Instruct compiler go generate an additional static method for us
    - For object, that means we don't need to call ObjectClass.INSTANCE.function();
    - For Companion object, that means we don't need to call Class.Companion.function()
- **Question**: init block in Kotlin
    - **Answer**: [init block in Kotlin]([https://www.youtube.com/watch?v=cb3jOFozJns)](https://outcomeschool.com/blog/init-block-in-kotlin)
    - We can't write any code in the primary constructor, but we can do it in secondary constructors.
    - Order: Primary constructor -> init -> secondary constructor
    - Can have muliple constructors. Executed in the same  oder as in the calss body
    - When to use: perform a task during the initialization of an object and we do not have a necessity for a secondary constructor
- **Question**: JvmField Annotation in Kotlin
    - **Answer**: [JvmField Annotation in Kotlin](https://www.youtube.com/watch?v=bx8OZcMbeUE)
    - Instruct the Kotlin compiler not to generate any getter and setter for the field and expose it as a field instead
- **Question**: singleTask launchMode in Android
    - **Answer**: [singleTask launchMode in Android](https://outcomeschool.com/blog/singletask-launchmode-in-android)
    - If the activity doesn't exist, then create a new activity
    - If the activity exists, then go back to the existing instance. That activity will receive the new intent through the onNewIntent() method. Activities after it in the backstack will be destroyed
    - Key benefits: single instance, stack cleanup, consistent state
- **Question**: Difference between == and === in Kotlin
    - **Answer**: [Difference between == and === in Kotlin]([https://outcomeschool.com/blog/structural-and-referential-equality-in-kotlin)])
    - == -> equals in Java, structural equality
    - === -> == in Java, referential equality
- **Question**: JvmOverloads Annotation in Kotlin
    - **Answer**: [JvmOverloads Annotation in Kotlin](https://www.youtube.com/watch?v=fHGsBV9Za8M)
    - Generate overloads for the function or constructor that substitute default parmeter values
- **Question**: Why is it recommended to use only the default constructor to create a Fragment?
    - **Answer**: [Why is it recommended to use only the default constructor to create a Fragment?](https://outcomeschool.com/blog/default-constructor-to-create-a-fragment)
    - Whenever the Android Framework decides to recreate our Fragment, Android calls the no-argument constructor of our Fragment, because Android Framework has no idea what constructors we have created.
    - The recommended way is creating a newInstance function and pass parameter with Bundle and fragment.arguments = bundle. When the system restores a fragment, it will automatically restore our bundle
- **Question**: Why do we need to call setContentView() in onCreate() of Activity class?
    - **Answer**: [Why do we need to call setContentView() in onCreate() of Activity class?](https://www.youtube.com/watch?v=U1aHAt7XC5I)
    - Because onCreate() will be only called once for each creation
- **Question**: When only onDestroy is called for an activity without onPause() and onStop()?
    - **Answer**: [When only onDestroy is called for an activity without onPause() and onStop()?](https://www.youtube.com/watch?v=B2kY_ckZa-g)
    - When we explicity call finish()

### Kotlin Coroutines

Topics you should know in **Kotlin Coroutines** for Android Interview:

* coroutines
  - A framework to manage concurrency in a more performant and simple way with its lightweight thread which is written on top of the actual threading framework to get the most out of it by taking the advantage of cooperative nature of functions.
  - Coroutines and the threads both are multitasking. But the difference is that threads are managed by the OS and coroutines by the users as it can execute a few lines of function by taking advantage of the cooperation.
  - Coroutines are lightweight threads. A lightweight thread means it doesn't map on the native thread, so it doesn't require context switching on the processor, so they are faster.
* suspend
  - Suspen function is a function that can be paused and resumed later without blocking the current thread.
* launch, async-await, withContext
  - launch: fire and forget. Return a Job
  - await: perform a task and return a result. Return a deferred
  - withContext: a suspend function through which we can do a task by providing the Dispathcers on which on which we want the task to be done
  - withContext doesn't create a new coroutine. It only shifts the context of the existing coroutine and it's a suspend functio whereas launch and async create a new coroutine and they are not suspend fucntions
* dispatchers
  - IO: network and disk-related work
  - Default: CPU-intense work
  - Main: UI thread
* scope, context, job
  - scope
      - A holder of a coroutine context
      - Lifecycle management: it controls the lifecycle of coroutines launched in it. If the scope is canceled, all its coroutines and child coroutines are canceled automatically
      - Mandatory for coroutine builder: coroutine builder functions like runBlocking, async, launch are extensions of CoroutineScope
  - context
      - CoroutineContext is an interface in Kotlin's coroutines that helps us define the context or the environment in which a coroutine executes
      - Dispatcher
      - Job
      - CoroutineName
      - Exception handler
  - job
      - A job is an interface in kotlin coroutine library that represents a coroutine's lifecycle. Every coroutine launched in Kotlin returns a job object
      - It's responsible for controlling the coroutine's status, such as whether it's active, completed or cancelled
      - You can cnacel the job, which cancels the associated coroutine's and its children
      - Jobs can have hierachical relationships. Cancelling a parent job cancels all its children 
* lifecycleScope, viewModelScope, GlobalScope
* suspendCoroutine, suspendCancellableCoroutine
      - See this article: https://outcomeschool.com/blog/callback-to-coroutines-in-kotlin
      - onSuccess: continuation.resume(result)
      - onFail: continuation.resumeWithException(throwable)
      - cancel: continutation.invokeOnCancellation
* coroutineScope, supervisorScope
      - coroutineScope: cancelled if any child fails, and then it will cancel all its child coroutines
      - supervisorScope: won't be cancelled when child fails (if it doesn't throw an exception in launch or deferred.await())

Learn the above-mentioned from the following links:

- [Master Kotlin Coroutines](https://outcomeschool.com/blog/kotlin-coroutines)
- [Suspending vs Blocking in Kotlin Coroutines](https://www.youtube.com/watch?v=V2lL_aJp17I)
- [Launch vs Async in Kotlin Coroutines](https://www.youtube.com/watch?v=B4AfTPpCU5o)
- [Dispatchers in Kotlin Coroutines](https://outcomeschool.com/blog/dispatchers-in-kotlin-coroutines)
- [coroutineScope vs supervisorScope](https://outcomeschool.com/blog/coroutinescope-vs-supervisorscope)
- [suspend function in Kotlin Coroutines](https://outcomeschool.com/blog/suspend-function-in-kotlin-coroutines)
- [Kotlin withContext vs Async-await](https://outcomeschool.com/blog/kotlin-withcontext-vs-async-await)
- [CoroutineContext in Kotlin](https://outcomeschool.com/blog/coroutinecontext-in-kotlin)
- [Callback to Coroutines in Kotlin](https://outcomeschool.com/blog/callback-to-coroutines-in-kotlin)
- [Retrofit with Kotlin Coroutines](https://outcomeschool.com/blog/retrofit-with-kotlin-coroutines)
- [Parallel Multiple Network Calls Using Kotlin Coroutines](https://outcomeschool.com/blog/parallel-multiple-network-calls-using-kotlin-coroutines)
- [Room Database with Kotlin Coroutines](https://outcomeschool.com/blog/room-database-with-kotlin-coroutines)
- [Unit Testing ViewModel with Kotlin Coroutines and LiveData](https://outcomeschool.com/blog/unit-testing-viewmodel-with-kotlin-coroutines-and-livedata)

### Kotlin Flow API

Topics you should know in **Kotlin Flow API** for Android Interview:

* Flow Builder, Operator, Collector
      - Flow is not started until we call a terminal operation, e.g collect, reduce (similarly in RxJava, the observable is not executed until we subscribe it)
      - Flow builder: build a flow
      - Operator: e.g map
      - Collector
* flowOn, dispatchers
      - Set the context/dispatcher for the flow to execute, like subscriberOn in RxJava
* Operators such as filter, map, zip, flatMapConcat, retry, debounce, distinctUntilChanged, flatMapLatest
  - zip vs combine:
      - zip: runs when both flows emit a new value
      - combine: runs when any flow emits a new value 
  - retry: set the max retry num and predicate to tell whether we should retry
  - debounce: Returns a flow that mirrors the original flow, but filters out values that are followed by the newer values within the given timeout. The latest value is always emitted.
  - flatMapConcat: Transforms elements emitted by the original flow by applying transform, that returns another flow, and then concatenating and flattening these flows.
  - flatMapLatest:	Cancels previous Flow on new emission
  - buffer: cache intermediate results of a flow
  - conflate: skip intermediate result. Only process the most recent one by dropping emitted values
  - collectLatest: cancel the code in collect block on a new value
* Terminal operators
  - Operatos that actually start the flow by connecting the flow builder, operators with the collector
* Cold Flow vs Hot Flow
  - See https://outcomeschool.com/blog/cold-flow-vs-hot-flow
* StateFlow, SharedFlow, callbackFlow, channelFlow
  - StateFlow and SharedFlow: https://outcomeschool.com/blog/stateflow-and-sharedflow
  - StateFlow = ShareFlow.withInitialValue(initialValue).replay(count = 1).distinctUntilChanged
  - callbackFlow: convert callback (e.g a listener) to a flow
  - channelFlow: a specialized cold flow builder for scenarios requiring concurrent data emission from multiple coroutine, as it allows launching multiple coroutines

Learn the above-mentioned from the following links:

- [Mastering Flow API in Kotlin](https://outcomeschool.com/blog/flow-api-in-kotlin)
- [Creating Flow Using Flow Builder in Kotlin](https://outcomeschool.com/blog/creating-flow-using-flow-builder-in-kotlin)
- [Terminal Operators in Kotlin Flow](https://outcomeschool.com/blog/terminal-operators-in-kotlin-flow)
- [Cold Flow vs Hot Flow](https://outcomeschool.com/blog/cold-flow-vs-hot-flow)
- [StateFlow and SharedFlow](https://outcomeschool.com/blog/stateflow-and-sharedflow)
- [Long-running tasks in parallel with Kotlin Flow](https://outcomeschool.com/blog/long-running-tasks-in-parallel-with-kotlin-flow)
- [Retry Operator in Kotlin Flow](https://outcomeschool.com/blog/retry-operator-in-kotlin-flow)
- [Retrofit with Kotlin Flow](https://outcomeschool.com/blog/retrofit-with-kotlin-flow)
- [Room Database with Kotlin Flow](https://outcomeschool.com/blog/room-database-with-kotlin-flow)
- [Kotlin Flow Zip Operator for Parallel Multiple Network Calls](https://outcomeschool.com/blog/kotlin-flow-zip-operator-parallel-multiple-network-calls)
- [Instant Search Using Kotlin Flow Operators](https://outcomeschool.com/blog/instant-search-using-kotlin-flow-operators)
- [callbackFlow - Callback to Flow API in Kotlin](https://outcomeschool.com/blog/callback-to-flow-api-in-kotlin)
- [Exception Handling in Kotlin Flow](https://outcomeschool.com/blog/exception-handling-in-kotlin-flow)
- [Unit Testing ViewModel with Kotlin Flow and StateFlow](https://outcomeschool.com/blog/unit-testing-viewmodel-with-kotlin-flow-and-stateflow)

### Kotlin

Android Interview Questions and Answers:

* **15 Kotlin Interview Questions and Answers**: [Check the PDF](https://www.linkedin.com/posts/outcomeschool_kotlin-interview-questions-and-answers-activity-7276115620536954880-cFUa)
    - Elvis operator ?: : set default value when dealing with nullable types
    - return a function: ::function
    - Thread.sleep() vs delay():
        - Thread.sleep(): pauses the execution of the current thread for the specified number of milliseconds. It blocks the current tread, which means the thread cannot do any other work while sleeping
        - dleya(): a suspend function so it's non blocking. It pauses the execution of the coroutine without blocking the underlying thread.

* **What is the advantage of using const in Kotlin?** - [Video](https://www.youtube.com/watch?v=3G49ivVxfkU) and [Blog](https://outcomeschool.com/blog/const-in-kotlin)

* **When to use lateinit keyword used in Kotlin?** - [Learn from here](https://outcomeschool.com/blog/lateinit-vs-lazy-in-kotlin)

* **What is inline function in Kotlin?** - [Video](https://www.youtube.com/watch?v=GLLI8h67ryo) and [Blog](https://outcomeschool.com/blog/inline-function-in-kotlin)

* **What are `companion objects` in Kotlin?** - [Learn from here](https://outcomeschool.com/blog/companion-object-in-kotlin)

* **Extension functions** - [Learn from here](https://outcomeschool.com/blog/extension-function-in-kotlin)
    - An extension function in Kotlin allows us to add new functions to existing classes without modifying their source code or extending them
    - Compiler generate a final class with aa static function with the same name and the original class as the first parameter

* **What is a data class in Kotlin?** - [Learn from here](https://outcomeschool.com/blog/data-class-in-kotlin)

* **Remove duplicates from an array in Kotlin** - [Learn from here](https://outcomeschool.com/blog/remove-duplicates-from-an-array-in-kotlin)

* **What is a JvmStatic Annotation in Kotlin?** - [Video](https://www.youtube.com/watch?v=qBBbOhY_pv4) and [Blog](https://outcomeschool.com/blog/jvmstatic-annotation-in-kotlin)

* **What is a JvmField Annotation in Kotlin?** - [Video](https://www.youtube.com/watch?v=bx8OZcMbeUE) and [Blog](https://outcomeschool.com/blog/jvmfield-annotation-in-kotlin)

* **What is a JvmOverloads Annotation in Kotlin?** - [Video](https://www.youtube.com/watch?v=fHGsBV9Za8M) and [Blog](https://outcomeschool.com/blog/jvmoverloads-annotation-in-kotlin)

* **noinline in Kotlin** - [Learn from here](https://outcomeschool.com/blog/noinline-in-kotlin)
    - By default, all lambdas in inline functions are inlined. noinline keyword prevent that
    - Common use case:
        - when we have a large lambda
        - Storing lambda in variable
        - return lambda from functions

* **crossinline in Kotlin** - [Learn from here](https://outcomeschool.com/blog/crossinline-in-kotlin)
    - Disable non-local return

* **scope functions in Kotlin** - [Learn from here](https://kotlinlang.org/docs/scope-functions.html)

* **What is a reified keyword in Kotlin?** - [Learn from here](https://www.youtube.com/watch?v=kD2T84FnTck)
    - ask the compiler to retain the type information of an inline function

* **lateinit vs lazy in Kotlin** - [Learn from here](https://outcomeschool.com/blog/lateinit-vs-lazy-in-kotlin)

* **What is an `init` block in Kotlin?** - [Video](https://www.youtube.com/watch?v=cb3jOFozJns) and [Blog](https://outcomeschool.com/blog/init-block-in-kotlin)

* **Difference between == and === in Kotlin** - [Video](https://www.youtube.com/watch?v=lJtgxT2OIgQ) and [Blog](https://outcomeschool.com/blog/structural-and-referential-equality-in-kotlin)

* **Advantage of using const in Kotlin** - [Learn from here](https://www.youtube.com/watch?v=3G49ivVxfkU)

* **What are higher-order functions in Kotlin?** - Learn from here: [Higher-Order Functions and Lambdas in Kotlin](https://outcomeschool.com/blog/higher-order-functions-and-lambdas-in-kotlin)
    - A higher-order function is a function that takes function as parameters or returns a function

* **Write a function(Higher-Order Function) that returns a function.** - [Check solution here](https://x.com/amitiitbhu/status/1862721662208155800)

* **What are Lambdas in Kotlin** - Learn from here: [Higher-Order Functions and Lambdas in Kotlin](https://outcomeschool.com/blog/higher-order-functions-and-lambdas-in-kotlin)

* **AssociateBy - List to Map in Kotlin** - [Learn from here](https://outcomeschool.com/blog/associateby-list-to-map-in-kotlin)
    - convert list to map

* **Open keyword in Kotlin** - [Learn from here](https://outcomeschool.com/blog/open-keyword-in-kotlin)

* **Companion object in Kotlin** - [Learn from here](https://outcomeschool.com/blog/companion-object-in-kotlin)

* **internal visibility modifier in Kotlin** - [Learn from here](https://youtu.be/wOHpuf74-cI)

* **partition - filtering function in Kotlin** - [Learn from here](https://outcomeschool.com/blog/partition-filtering-function-in-kotlin)
    - Split a list to two by a predicate which returns a boolean

* **Infix notation in Kotlin** - [Learn from here](https://outcomeschool.com/blog/infix-notation-in-kotlin)
    - Functions marked with the infix keyword can also be called using the infix notation (omitting the dot and the parentheses for the call).

* **How does the Kotlin Multiplatform work?** - [Learn from here](https://youtu.be/nwfNh6Kd5hI)

* **Suspending vs Blocking in Kotlin Coroutines** - [Learn from here](https://www.youtube.com/watch?v=V2lL_aJp17I)

* **What is runBlocking in Coroutines?** - [Learn from here](https://x.com/outcome_school/status/1861455930061156797)

* **What is the meaning of structured concurrency in Kotlin Coroutines?** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_softwareengineer-androiddev-android-activity-7267476661967683584-wDCh/)

* **String vs StringBuffer vs StringBuilder** - [Learn from here](https://outcomeschool.com/blog/string-vs-stringbuffer-vs-stringbuilder)
    - StringBuffer is thread-safe while StringBuilder is not, because methods of StringBuffer is synchronized. Thus, StringBuilder has better performance thatn StringBuffer

* **What is the difference between `val` and `var`?** - [Learn from here](https://stackoverflow.com/questions/44200075/val-and-var-in-kotlin)

* **How to check if a `lateinit` variable has been initialized?** - [Learn from here](https://outcomeschool.com/blog/lateinit-vs-lazy-in-kotlin)
    - isInitialized

* **How to do lazy initialization of variables in Kotlin?** - [Learn from here](https://outcomeschool.com/blog/lateinit-vs-lazy-in-kotlin)
    - by lazy

* **What are the visibility modifiers in Kotlin?** - [Learn from here](https://www.linkedin.com/posts/pallavi-shekhar_outcomeschool-softwareengineer-tech-activity-7305070243620544512-NqDW)

* **What is the equivalent of Java static methods in Kotlin?** - [Learn from here](https://stackoverflow.com/questions/40352684/what-is-the-equivalent-of-java-static-methods-in-kotlin)

* **How to create a Singleton class in Kotlin?** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_outcomeschool-softwareengineer-tech-activity-7297112198252806144-97Eh)

* **Explain the use-case of `let`, `run`, `with`, `also`, `apply` in Kotlin.** - Learn from [here](https://kotlinlang.org/docs/scope-functions.html) and [here](https://stackoverflow.com/questions/45977011/example-of-when-should-we-use-run-let-apply-also-and-with-on-kotlin)

* **Difference between List and Array types in Kotlin** - [Learn from here](https://stackoverflow.com/questions/36262305/difference-between-list-and-array-types-in-kotlin)

* **What are `Labels` in Kotlin?** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineer-tech-activity-7305796789159215105-oEUj)
    - Labels in Kotlin: In Kotlin, labels are identifiers used to name a point in the code to enable more control over breaks, continues, and returns in nested loops and lambdas.

* **Explain inline classes in Kotlin** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_outcomeschool-softwareengineering-tech-activity-7251812269804724224-TR6Y)
    - Create lightweight wrappers around a single value, offering type safety without performance overhead
    - It does it without performance overhead by replacing instances of the inline class with the underlying value, eliminating the need for object allocation, and improving performance.
    - They are declared using the inline keyword and can have only one property. Check the code snippet.

* **When to use Kotlin sealed classes?** - [Learn from here](https://kotlinlang.org/docs/sealed-classes.html)
    - Sealed classes and interfaces provide controlled inheritance of your class hierarchies. All direct subclasses of a sealed class are known at compile time. No other subclasses may appear outside the module and package within which the sealed class is defined

* **Tell about the Collections in Kotlin** - [Learn from here](https://kotlinlang.org/docs/collections-overview.html)

* **What does ?: do in Kotlin? (Elvis Operator)** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_softwareengineer-androiddev-android-activity-7269313270669295618-g6kJ)

* **timeouts in Kotlin Coroutines** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_softwareengineer-androiddev-android-activity-7265684677770846208-Ug0Y)
    - withTimeout(long) {}

* **How do you combine multiple coroutine results?** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_softwareengineer-androiddev-android-activity-7267827335393873920-v6t3)
    - awaitAll()

* **How to Implement Debounce Using Coroutines?** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_softwareengineer-androiddev-android-activity-7285163906686164994-tOUK)

* **Kotlin code snippet demonstrating how to run two coroutines in series and parallel** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_outcomeschool-softwareengineer-tech-activity-7297944609614139392-h9NZ/)

* **yield in Kotlin Coroutines** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_outcomeschool-softwareengineer-tech-activity-7298934394113638400-ZY-y)
    - Suspends this coroutine and immediately schedules it for further execution. A coroutine runs uninterrupted on a thread until the coroutine suspends, giving other coroutines a chance to use that thread for their computations. Normally, coroutines suspend whenever they wait for something to happen: for example, trying to receive a value from a channel that's currently empty will suspend. Sometimes, a coroutine does not need to wait for anything, but we still want it to give other coroutines a chance to run. 

* **Delegates in Kotlin** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_outcomeschool-softwareengineer-tech-activity-7301107785302249474-WyDC)
    - class delegation: delegating the implementation of an interface to another object
    - property delegation: delegating the getter/setter logic of a property to be a helper object

### Android

Android Interview Questions and Answers:

#### Base

* **Why does an Android App lag?** - [Learn from here](https://outcomeschool.com/blog/android-app-lag)
    - Android app updates UI every 16ms (1000ms / 60fps)
    - If any main thread task takes more than 16ms, there will be a frame drop
    - GC runs too frequently, probably due to memory leak
    - Doing too much work on the main thread

* **What is `Context`? How is it used?** - [Context In Android Application](https://outcomeschool.com/blog/context-in-android-application)
    - In Android, a Context object provides information about the current application environment. It allows you to interact with the system services, resources, and other application components.
    - Use application context for singleton, e.g a database object
    - Use activity context for UI operation, e.g showing a toast. Otherwise app will crash.
    - Application context won't respect locale changes until the app is restarted

* **Tell all the Android application components.** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineer-tech-activity-7302543942028251137-S3vJ)
    - Activity: it represents a single screen with a user interface.
    - Services: a Service is a component that runs in the background to perform long-running operations or handle tasks without a UI. For example, playing music or downloading a file can be managed by a Service. It doesn’t interact directly with the user but can communicate with other components.
    - Broadcast receivers: a Broadcast Receiver listens for system-wide broadcast announcements or events, such as a low battery warning, a new SMS, or a custom event from another app.
    - Content providers: It manages data sharing between different applications. Example: Sharing contacts or accessing media files from the gallery. For app internal data, we can use MVVM + repository
    - Intents
        - Explicity intents: target a specific component (e.g launching a known activity)
        - Implicit intents: declare an action (e.g share a file) and let the system resolve it

* **What is the project structure of an Android Application?** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_android-app-project-structure-activity-7302902092812226560-bM8D)

* **What is `AndroidManifest.xml`?** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineer-tech-activity-7305255303908888576-c0Nf)

* **What is the `Application` class?** -[Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineer-tech-activity-7304864185010528256-2GGU)
    - global representation of an app's process.
    - use cases
        - initialize libraries
        - maintain global application state (single instances)
        - setting up DI
  
#### Activity and Fragment

* **Why is it recommended to use only the default constructor to create a `Fragment`?** - Learn from [video](https://www.youtube.com/watch?v=CitBt0FZFIc) and [blog](https://outcomeschool.com/blog/default-constructor-to-create-a-fragment)

* **What is `Activity` and its lifecycle?** - [Learn from here](https://developer.android.com/guide/components/activities/activity-lifecycle)

* **What is the difference between onCreate() and onStart()** - [Learn from here](https://developer.android.com/guide/components/activities/activity-lifecycle)

* **When only onDestroy is called for an activity without onPause() and onStop()?** - [Learn from here](https://www.youtube.com/watch?v=B2kY_ckZa-g)
    - when we explicitly call activity.finish()

* **Why do we need to call setContentView() in onCreate() of Activity class?** - [Learn from here](https://www.youtube.com/watch?v=U1aHAt7XC5I)
    - setContentView(): inflate the UI layout
    - why: onCreate is called exactly once

* **What is onSaveInstanceState() and onRestoreInstanceState() in activity?** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineer-tech-activity-7301985158608392193-pA5M)
    - onSaveInstanceState(): called before the activity is destroyed or recreated
    - onRestoreInstanceState(): called between onStart() and onResume()

* **What is `Fragment` and its lifecycle?** - [Learn from here](https://developer.android.com/guide/fragments/lifecycle)

* **What are "launchMode"?** - [Learn from here](https://outcomeschool.com/blog/singletask-launchmode-in-android) and [singleTask launchMode in Android](https://youtu.be/WYkQEnm4jeI)
    - We use launchMOde to give instructions to the Android OS about how to launch the activity
    - standard (default): Creates a new instance of the activity every time it’s launched, even if the same activity is already in the stack.
    - singleTask: if the activity exists, bring it back to the goreground and clears all activities above it.
        - use case: Main entry point

* **What is the difference between a `Fragment` and an `Activity`? Explain the relationship between the two.** - [Learn from here](https://stackoverflow.com/questions/10478233/why-fragments-and-when-to-use-fragments-instead-of-activities)
    - Purpose: activity represents a single screen with a UI. Fragment represents a reusable portion of a UI
    - Fragment can be used for dynamic UIs (e.g tabs, bottom navigation)
    - Fragment is more light-weight 

* **When should you use a Fragment rather than an Activity?**
    - When you have some UI components to be used across various activities
    - When multiple views can be displayed side by side just like ViewPager

* **What is the difference between FragmentPagerAdapter vs FragmentStatePagerAdapter?**
    - FragmentPagerAdapter: Each fragment visited by the user will be stored in the memory but the view will be destroyed. When the page is revisited, then the view will be created not the instance of the fragment.
    - FragmentStatePagerAdapter: Here, the fragment instance will be destroyed when it is not visible to the user, except the saved state of the fragment.

* **What is the difference between adding/replacing fragment in backstack?** - [Learn from here](https://stackoverflow.com/questions/24466302/basic-difference-between-add-and-replace-method-of-fragment/24466345)
    - Add
        - Behavior:
            - Adds a new fragment on top of existing fragments in the container.
            - Existing fragments remain in the container but are hidden (not destroyed).
        - Back Stack:
            - If added to the back stack (addToBackStack("tag")), pressing the back button pops the added fragment and reveals the previous fragment(s).
    - replace
        - Behavior:
            - Removes all existing fragments in the container and adds the new fragment.
            - Previous fragments are destroyed (unless the transaction is added to the back stack).
        - Back Stack:
            - If added to the back stack, pressing the back button reverts the transaction, restoring the previous fragments.

* **How would you communicate between two Fragments?**
    - Use a ViewModel scoped to the host activity. Both fragments observe the same ViewModel instance.
    - Use the fragment result Api

* **What is retained `Fragment`?** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_softwareengineer-androiddev-android-activity-7265620144289193984-hlpH)
    - A Retained Fragment in Android is a special type of fragment that is not destroyed when its host activity is recreated due to configuration changes (e.g. screen rotation, language change). It retains its instance and data across activity recreation, making it useful for preserving state or continuing background tasks.
    - Deprecated in favor of ViewModel

* **What is the purpose of `addToBackStack()` while commiting fragment transaction?**
    - A Fragment Transaction in Android is a mechanism that allows you to perform a series of operations (like adding, removing, replacing, or hiding Fragments) as a single, atomic unit.
    - By calling addToBackStack(), the replace transaction is saved to the back stack so the user can reverse the transaction and bring back the previous fragment by pressing the Back button. For more [Learn from here](https://stackoverflow.com/questions/22984950/what-is-the-meaning-of-addtobackstack-with-null-parameter)

#### Views and ViewGroups

* **Optimizing layouts in Android** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_softwareengineer-androiddev-android-activity-7269208182390951936-dAg3)
    - ViewStub: A ViewStub in Android is an invisible, zero-sized View used for lazy inflation of layouts. It acts as a placeholder for a layout resource, delaying its inflation until explicitly requested, which improves performance by reducing initial layout overhead. 

* **What is `View` in Android?**
    - View is the fundamental building block for creating user interface (UI) components.

* **Difference between `View.GONE` and `View.INVISIBLE`?** - [Learn from here](https://stackoverflow.com/questions/11556607/android-difference-between-invisible-and-gone)
    - View.GONE: This view is invisible, and it doesn't take any space for layout purposes.
    - View.INVISIBLE: This view is invisible, but it still takes up space for layout purposes.

* **Can you a create custom view? How?**

* **What are ViewGroups and how they are different from the Views?**
    - View: View objects are the basic building blocks of User Interface(UI) elements in Android. View is a simple rectangle box which responds to the user’s actions. Examples are EditText, Button, CheckBox etc. View refers to the android.view.View class, which is the base class of all UI classes.
    - ViewGroup: ViewGroup is the invisible container. It holds View and ViewGroup. For example, LinearLayout is the ViewGroup that contains Button(View), and other Layouts also. ViewGroup is the base class for Layouts.

* **What is a Canvas?** - [Learn from here](https://www.linkedin.com/posts/pallavi-shekhar_androiddev-android-activity-7301608732671520771-7WLF)
    - In Android development, a Canvas is a class that provides a drawing surface for 2D graphics. It’s part of the Android graphics framework and is used to draw shapes, text, images, and other visual elements directly onto a view or a bitmap.
    - Canvas vs bitmap: canvas is drawing tool while the Bitmap is the paper which holds the actual pixels

* **What is a `SurfaceView`?** - [Learn from here](https://developer.android.com/reference/android/view/SurfaceView)
    - A SurfaceView in Android is a specialized view that provides a dedicated drawing surface for rendering high-performance graphics, video, or animations outside the main UI thread. It’s ideal for scenarios requiring frequent or complex updates (e.g., games, camera previews, video playback).

* **Relative Layout vs Linear Layout.**

* **Tell about Constraint Layout optimization** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_constraintlayout-in-android-uses-the-cassowary-activity-7303624644165545993-xUBG)

* **Do you know what is the view tree? How can you optimize its depth?** - [Learn from here](https://developer.android.com/reference/android/view/ViewTreeObserver)
    - The view tree represents the hierarchical structure of UI components (views and view groups) that make up an activity or fragment.
    - How to optimize
        - Use efficient layout, e.g ConstrainLayout
        - Remove redundant container
        - defer loaidng with ViewStub

#### Displaying Lists of Content

* **What is the difference between `ListView` and `RecyclerView`?** - [Learn from here](https://stackoverflow.com/questions/26728651/recyclerview-vs-listview)

* **How does the RecyclerView work?** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_softwareengineer-androiddev-android-activity-7268187299811606528-u2_w)
    - Reuses (recycles) off-screen views to minimize memory usage and improve performance.

* **RecyclerView Optimization - Scrolling Performance Improvement** - [Learn from here](https://outcomeschool.com/blog/recyclerview-optimization)
    - Use optimized image loading library:
        - use bitmap pool to reduce GC overhead: we maintain a collection of unused bitmaps. When we need to create a new bitmap, we first check if there is a bitmap unused in the pool which has the same of larger size. If so, we can reuse that bitmap object
        - cancel image loading when it's no longer necessary
        - downsampling: pass the view when creating the image loading request to get view size info. Assume that we have an image of size 2000*2000, but the view size is 400*400. So why load an image of 2000*2000, Glide down-samples the bitmap to 400*400, and then show it into the view.
    - set image width and height
    - use notify item RecyclerView APi
    - avoid a nested view 

* **Optimizing Nested RecyclerView** - [Learn from here](https://outcomeschool.com/blog/setrecycledviewpool-for-optimizing-nested-recyclerview)
    - setRecycledViewPool so nested recyclerView can share there view pool

* **How does RecyclerView improve performance over ListView?**

* **What are the components of a RecyclerView?**
    - Adapter: Bridges the dataset and the UI by creating and binding views to data items.
    - ViewHolder: Holds references to UI elements (views) for a single list item to avoid repetitive findViewById() calls.
    - LayoutManager: Determines how items are arranged and displayed (e.g., list, grid, staggered grid).
    - ItemDecoration: Adds visual decorations (e.g., dividers, spacing) between items.
    - ItemAnimator: Handles animations for item changes (add, remove, update).
    - notifyDataSetChanged is inefficient because it forces the entire dataset to be treated as "changed"
        - Use DiffUtil
        - Use ListAdapter to automate DiffUtil handling

* **Explain the role of RecyclerView.Adapter and RecyclerView.ViewHolder** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_softwareengineer-androiddev-android-activity-7274733205927182337-hvTG)

* **What is a LayoutManager in RecyclerView?**

* **How do you handle multiple view types in a single RecyclerView?**
    - Override getItemViewType()

* **What is DiffUtil and how does it improve RecyclerView performance?** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_softwareengineer-androiddev-android-activity-7279435764973686785-pfiQ)
    - DiffUtil is a utility class that efficiently calculates the differences between two lists and updates only the items that have changed in the RecyclerView. By minimizing unnecessary updates, it reduces the workload on the RecyclerView, enhancing performance and ensuring a smoother user experience.
    - Only the items that actually changed are updated.
    - It performs its calculations on a background thread by default.
    - Instead of manually tracking changes and calling specific notify methods (notifyItemChanged, notifyItemInserted, etc), it handles all the complexity of determining and applying the changes.
    - areItemsTheSame: Determines if two items represent the same logical entity (e.g., the same user, post, or product)
    - areContentsTheSame: Checks if the content/data of the two items is identical (i.e., no UI update needed).

* **What is the purpose of RecyclerView.setHasFixedSize(true)?** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_softwareengineer-androiddev-android-activity-7282252857637007361-thzv/)
    - optimize the performance of a RecyclerView when the size of its layout does not change based on the adapter's content. This allows the RecyclerView to avoid unnecessary layout recalculations and re-measurements when data changes, leading to smoother scrolling and better performance.

* **How do you update a specific item in RecyclerView?**
    - notifyItemChanged(position)

* **What is `SnapHelper`?** - Learn from here: [SnapHelper](https://outcomeschool.com/blog/snaphelper)
    - a helper class that helps in snapping any child view of the RecyclerView
    - LinearSnapHelper: intended for smaller items and snaps the center of the target child view to the center of the RecyclerView
    - PagerSnapHelper: intended for full-screen items and behaves similarly to a ViewPager:

#### Dialogs and Toasts

* **What is `Dialog` in Android?** - [Learn from here](https://developer.android.com/guide/topics/ui/dialogs)
    - A dialog is a small window that prompts the user to make a decision or enter additional information. A dialog doesn't fill the screen and is normally used for modal events that require users to take an action before they can proceed.
        - AlertDialog
        - DatePickerDialog/TimePickerDialog  

* **What is `Toast` in Android?** - [Learn from here](https://developer.android.com/guide/topics/ui/notifiers/toasts)
    - A toast provides simple feedback about an operation in a small popup.
    - Toast vs snackbar
        - Toast doesn't have user-actionable options while snackbar does 

* **What the difference between `Dialog` and `Dialog Fragment`?** - [Learn from here](https://stackoverflow.com/questions/7977392/android-dialogfragment-vs-dialog)

| **Aspect**               | **DialogFragment**                          | **AlertDialog**                      |
|--------------------------|---------------------------------------------|--------------------------------------|
| **Lifecycle Management** | Managed as a `Fragment` (properly tied to Activity/Fragment lifecycle). | Tied directly to Activity context (risk of leaks if not dismissed manually). |
| **Reusability**          | Reusable across Activities/Fragments.       | Tightly coupled to the context it’s created in. |
| **Customization**         | Supports full UI customization via `onCreateView` (e.g., custom layouts). | Limited to pre-defined dialog styles, buttons, and text. |
| **Backstack Integration**| Can be added to Fragment backstack (dismissed with back button). | No native backstack support. |
| **Configuration Changes**| Automatically survives screen rotation/configuration changes. | Dismissed on configuration changes; requires manual state restoration. |
| **Risk of Leaks**         | Low (lifecycle-aware, auto-dismisses).      | High (holds Activity reference; leaks if not dismissed before Activity destruction). |
| **Material Design**       | Integrates with `MaterialAlertDialogBuilder` for modern styling. | Requires manual theming; less consistent with Material 3. |
| **Use Case**              | Complex UIs, forms, reusable dialogs.       | Simple, one-off alerts with minimal interaction. |
| **Context Handling**      | Uses `Fragment` context safely.             | Directly references Activity context (leak-prone). |

#### Intents and Broadcasting

* **What is `Intent`?** - [Learn from here](https://developer.android.com/guide/components/intents-filters)
    - An Intent is a messaging object you can use to request an action from another app component
    - Fundamental use cases:
        - Starting an activity
        - Starting a service
        - Deliver a broadcast 

* **Implicit `Intent` vs  Explicit `Intent`?** - [Learn from here](https://developer.android.com/guide/components/intents-filters)
    - Explicity intents: target a specific component (e.g launching a known activity)
    - Implicit intents: declare an action (e.g share a file) and let the system resolve it

* **What is a `BroadcastReceiver`?** - [Learn from here](https://developer.android.com/guide/components/broadcasts)

* **What is a Sticky `Intent`?**
    - Sticky Intent refers to a type of Android broadcast intent that remains accessible in the system even after it has been sent and processed.
    - Sticky intents "stick around" in the system, retaining their data after being broadcast. New components (e.g., apps or services) that register to receive this intent later can immediately retrieve the last sent value.
    - Primarily used for system state updates, such as battery level, connectivity status, or time zone changes. For example, if an app starts after a sticky battery-level update was sent, it can still fetch the latest battery status.
    - Sticky Intents allows communication between a function and a service. sendStickyBroadcast() performs a sendBroadcast(Intent) known as sticky, i.e. the Intent you are sending stays around after the broadcast is complete, so that others can quickly retrieve that data through the return value of registerReceiver(BroadcastReceiver, IntentFilter). For example, if you take an intent for ACTION_BATTERY_CHANGED to get battery change events: When you call registerReceiver() for that action — even with a null BroadcastReceiver — you get the Intent that was last Broadcast for that action. Hence, you can use this to find the state of the battery without necessarily registering for all future state changes in the battery.

* **Describe how broadcasts and intents work to be able to pass messages around your app?** - [Learn from here](https://stackoverflow.com/questions/7276537/using-a-broadcast-intent-broadcast-receiver-to-send-messages-from-a-service-to-a)
    - Register broadcast receiver in the activity 

* **What is a `PendingIntent`?**
    - A PendingIntent is a powerful Android mechanism that allows one app to delegate a specific action (like starting an Activity, Service, or sending a Broadcast) to another app, while retaining the original app's permissions and identity. It acts as a "token" that another process can use to execute predefined actions on behalf of your app, even if your app is not running.
    - Common use case:
        - Triggering actions from notifications (e.g., opening an Activity when a notification is tapped).
        - Scheduling future tasks with AlarmManager.
        - Handling app widgets (e.g., a button click on a widget). 

* **What are the different types of Broadcasts?** - [Learn from here](https://developer.android.com/guide/components/broadcasts)
    - context-registered receiver: dynamically register a receiver during an activity/fragment/application's lifecycle
    - manifest-declared receiver: the system can start the app and deliver the broadcast even if the app is not running
    - Prefer context-registered unless manifest-declared receiver is absolutely necessary

#### Services

* **Explain Android Service Lifecycle** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_softwareengineer-androiddev-android-activity-7265212180570992640-CJn_)
    - onCreate: when the service is created for the first time
    - onStartCommand: called each time when your service using startService()
    - onBind: called when a client explicitly binds to the service by calling bindService
    - onUnbind: called when all clients have unbound from the service (after the last unbindService call)
    - onDestroy: when the service is no longer used and is being destroyed

* **What is Service?** - [Learn from here](https://developer.android.com/guide/components/services)
    - bind: you can bind a service with app components so they can communicate directly with each other
    - foreground/background: or you can start it by calling startService() and then stop it manually

* **On which thread does a Service run in Android?** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_softwareengineer-androiddev-android-activity-7283717741130215424-Vn39)
    - Service runs on the main thread by default
    - If you need to perform a long-running task, you must create a separate thread using Thread/Coroutine etc within the service
    - IntentService runs on a background thread automatically. It creates a worker thread to handle the intents, so you don’t have to manage threading manually.

* **Service vs IntentService** - [Learn from here](https://stackoverflow.com/questions/15524280/service-vs-intentservice-in-the-android-platform)
    - limitations
        - The service may block the main thread
        - The IntentService cannot run tasks in parallel. Hence all the consecutive intents will go into the message queue for the worker thread and will execute sequentially.

* **Background tasks** - Learn from here](https://developer.android.com/develop/background-work/background-tasks)
    - asynchronous work
        - concurrent operation, e.g time consuming calculation
        - use Kotlin coroutine
        - not guranteed to finish if the app stops being in a valid lifecycle stage (for example, if the app leaves the foreground). 
    - task scheduling APIs
        - do tasks that need to continue even if the user leaves the app.
        - WorkManager/JobSceduler. You can use WorkManager to schedule tasks to run at specific times, or specify the conditions when the task should run. You can even set up chains of tasks, so each task runs in turn, passing its results to the next one.
        - common senarios:
            - Fetching data from server periodically
            - Fetching sensor data (for example, step counter data)
            - Getting periodic location data (you must be granted ACCESS_BACKGROUND_LOCATION permission on Android 10 or higher)  
    - foreground services
    - alternative APIs
    - [tasks initiated by the user](https://developer.android.com/develop/background-work/background-tasks#user-initiated)
    - [Tasks in response to an event](https://developer.android.com/develop/background-work/background-tasks#event-driven)

* **What is a Foreground Service?** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_foreground-service-in-android-activity-7303268432030879745-TFVI)
    - a type of service that performs tasks noticeable to the user and must display a persistent notification (that cannot be dismissed) while running
    - unlike background services, foreground services are less likely to be killed by the system when resources are low because they are consisder a higher priority due to their direct interaction with the user
    - e.g Music playbck, location tracking, file transfer

* **What is a `JobScheduler`?** - [Learn from here](https://developer.android.com/reference/android/app/job/JobScheduler)
    - Schedule background jobs that run under specific conditions (e.g., network availability, charging state).

#### Inter-process Communication

* **How can two distinct Android apps interact?** - [Learn from here](https://developer.android.com/training/basics/intents)

* **Is it possible to run an Android app in multiple processes? How?** - [Learn from here](https://stackoverflow.com/questions/6567768/how-can-an-android-application-have-more-than-one-process)

* **What is AIDL? Enumerate the steps in creating a bounded service through AIDL.** - [Learn from here](https://developer.android.com/guide/components/aidl)

* **What can you use for background processing in Android?** - [Learn from here](https://developer.android.com/guide/background)

* **What is a `ContentProvider` and what is it typically used for?** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_softwareengineer-androiddev-android-activity-7268117553040764931-64fI)

#### Long-running Operations

* **How to run parallel tasks and get a callback when all are complete?** - [Long-running tasks in parallel with Kotlin Flow](https://outcomeschool.com/blog/long-running-tasks-in-parallel-with-kotlin-flow)

* **What is ANR? How can the ANR be prevented?** - [Learn from here](https://developer.android.com/topic/performance/vitals/anr.html)

* **What is an `AsyncTask`(Deprecated in API level 30) ?**

* **What are the problems in AsyncTask?**

* **Daemon Threads vs. User Threads** - [Learn from here](https://x.com/amitiitbhu/status/1817783254885478872)

* **Explain `Looper`, `Handler`, and `HandlerThread`.**

* **Android Memory Leak and Garbage Collection**

* **Can you explain the difference between a Runnable and a Thread in Android?** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_softwareengineer-androiddev-android-activity-7279784055284420609-Xa8b)

#### Working With Multimedia Content

* **How do you handle bitmaps in Android as it takes too much memory?** - [Learn from here](https://developer.android.com/topic/performance/graphics/load-bitmap) and [here](https://developer.android.com/topic/performance/graphics/manage-memory)

* **Tell about the `Bitmap` pool.** - [Learn from here](https://outcomeschool.com/blog/bitmap-pool)

#### Data Saving

* **Jetpack DataStore Preferences** - [Learn from here](https://outcomeschool.com/blog/jetpack-datastore-preferences)

* **Persisting Data in an Android App** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_outcomeschool-softwareengineer-tech-activity-7301836718003888128-oNi2)

* **What is ORM? How does it work?**

* **How would you preserve the `Activity` state during a screen rotation?** - [Learn from here](https://www.youtube.com/watch?v=ORtieK5f_zg)

* **What are different ways to store data in your Android app?**

* **Explain Scoped Storage in Android.**

* **How to encrypt data in Android?**

* **What is commit() and apply() in SharedPreferences?**
    - commit() returns a boolean value of success or failure immediately by writing data synchronously.
    - apply() is asynchronous and it won't return any boolean response. If you have an apply() outstanding and you are performing commit(), then the commit() will be blocked until the apply() is not completed.

#### Look and Feel

* **What is a `Spannable`?**

* **What is a `SpannableString`?**
   - A SpannableString has immutable text, but its span information is mutable. Use a SpannableString when your text doesn't need to be changed but the styling does. Spans are ranges over the text that include styling information like color, heighliting, italics, links, etc

* **What are the best practices for using text in Android?**

* **How to implement Dark mode in any application?**

#### Memory Optimizations

* **What is the `onTrimMemory()` method?** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_softwareengineer-androiddev-android-activity-7267752779727679488--kk4)

* **How to identify and fix OutOfMemory issues?**

* **How do you find memory leaks in Android applications?**

#### Battery Life Optimizations

* **How to reduce battery usage in an android application?**

* **What is Doze? What about App Standby?** - [Learn from here](https://developer.android.com/training/monitoring-device-state/doze-standby)

* **What is `overdraw`?** - [Learn from here](https://developer.android.com/topic/performance/rendering/overdraw.html)

#### Supporting Different Screen Sizes

* **How do you support different types of resolutions?** - [Learn from here](https://developer.android.com/training/multiscreen/screensizes)

#### Permissions

* **What are the different protection levels in permission?**

#### Native Programming

* **What is the NDK and why is it useful?** - Learn from here: [Android NDK and RenderScript](https://outcomeschool.com/blog/ndk-and-renderscript)

* **What is renderscript?** - Learn from here: [Android NDK and RenderScript](https://outcomeschool.com/blog/ndk-and-renderscript)

#### Android System Internal

* **What is Android Runtime?** - [Android Runtime](https://outcomeschool.com/blog/dalvik-art-jit-aot)

* **Dalvik, ART, JIT, and AOT in Android** - [Dalvik, ART, JIT, and AOT](https://outcomeschool.com/blog/dalvik-art-jit-aot)

* **What are the differences between Dalvik and ART?** - [Difference between Dalvik and ART](https://outcomeschool.com/blog/dalvik-art-jit-aot)

* **What is DEX?** - [Learn from here](https://developer.android.com/reference/dalvik/system/DexFile)

* **What is Multidex in Android?** - [Learn from here](https://www.youtube.com/watch?v=R0zd8lmHnmE)

* **Can you manually call the Garbage collector?** - [Is it possible to force Garbage Collection in Android?](https://www.youtube.com/watch?v=fPEjpFKo1-Q)

#### Android Jetpack

* **What is Android Jetpack and why to use this?**

* **What is a ViewModel and how is it useful?** Learn: [What is a ViewModel and how is it useful?](https://youtu.be/ORtieK5f_zg)

* **SharedViewModel in Android** Learn: [SharedViewModel in Android](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineering-tech-activity-7262328327531577344-fwSE)

* **What are Android Architecture Components?**

* **What is LiveData in Android?**

* **How LiveData is different from ObservableField?**

* **What is the difference between setValue and postValue in LiveData?** Learn: [setValue() vs postValue() in LiveData](https://www.linkedin.com/posts/outcomeschool_softwareengineer-androiddev-android-activity-7274283452563107840-SXXl)

* **How to share ViewModel between Fragments in Android?** Learn: [SharedViewModel in Android](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineering-tech-activity-7262328327531577344-fwSE)

* **Explain WorkManager and its use cases.**

* **How does ViewModel work internally?**

#### Others

* **What is the difference between Serializable and Parcelable? Which is the best approach in Android?** - [Learn from here](https://outcomeschool.com/blog/parcelable-vs-serializable)

* **Why Bundle class is used for data passing and why cannot we use simple Map data structure?** - [Learn from here](https://developer.android.com/guide/components/activities/parcelables-and-bundles)

* **How do you troubleshoot a crashing application?** - [Learn from here](https://developer.android.com/topic/performance/vitals/crash)

* **Explain the Android push notification system?** Learn from here: [How does the Android push notification system work?](https://youtu.be/810IFG2sWlc)

* **What is AAPT?** - [Learn from here](https://developer.android.com/studio/command-line/aapt2)

* **FlatBuffers vs JSON.**

* **`HashMap`, `ArrayMap` and `SparseArray`** - [Learn from here](https://outcomeschool.com/blog/optimization-using-arraymap-and-sparsearray)

* **What are Annotations?** - [Learn from here](https://outcomeschool.com/blog/creating-custom-annotations)

* **How to create custom Annotation?** - [Learn from here](https://outcomeschool.com/blog/creating-custom-annotations)

* **What is the Android Support Library? Why was it introduced?** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_androiddev-activity-7275725268680392705-waUi)

* **What is Android Data Binding?**

### Android Libraries

Android Interview Questions and Answers:

* **Explain OkHttp Interceptor** - [Learn from here](https://outcomeschool.com/blog/okhttp-interceptor)

* **OkHttp - HTTP Caching** - [Learn from here](https://outcomeschool.com/blog/caching-with-okhttp-interceptor-and-retrofit)

* **How to enable logging in OkHttp?** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_softwareengineer-androiddev-android-activity-7274652524433850368-qC4D)

* **Why do we use the Dependency Injection Framework like Dagger in Android?** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_androiddev-activity-7038019147737276417-tH4s)

* **How does the Dagger work?**

* **How will you choose between Dagger 2 and Dagger-Hilt?**

* **What is a Component in Dagger?**

* **What is Module in Dagger?**

* **How does the custom scope work in Dagger?**

* **When to call dispose and clear on CompositeDisposable in RxJava?** - [Learn from here](https://outcomeschool.com/blog/dispose-vs-clear-compositedisposable-rxjava)

* **What is Multipart Request in Networking?**

* **What is Flow in Kotlin?** - [Learn from here](https://outcomeschool.com/blog/flow-api-in-kotlin)

* **App Startup Library** - [Learn from here](https://outcomeschool.com/blog/app-startup-library)

* **Tell me something about RxJava.**

* **How will you handle error in RxJava?**

* **FlatMap Vs Map Operator** - [Learn from here](https://outcomeschool.com/blog/rxjava-map-vs-flatmap)
    
* **When to use `Create` operator and when to use `fromCallable` operator of RxJava?** - Learn from here: [RxJava Create and fromCallable Operator](https://outcomeschool.com/blog/rxjava-create-and-fromcallable-operator)
    
* **When to use `defer` operator of RxJava?** - Learn from here: [RxJava Defer Operator](https://outcomeschool.com/blog/rxjava-defer-operator)
    
* **How are Timer, Delay, and Interval operators used in RxJava?** - [Learn from here](https://outcomeschool.com/blog/rxjava-interval-operator)

* **How to make two network calls in parallel using RxJava?** - [RxJava Zip Operator](https://outcomeschool.com/blog/rxjava-zip-operator)
    
* **Tell the difference between Concat and Merge.** - [Learn from here](https://outcomeschool.com/blog/rxjava-concat-operator) and [here](https://outcomeschool.com/blog/rxjava-merge-operator)

* **Explain Subject in RxJava?** - [Learn from here](https://outcomeschool.com/blog/rxjava-subject-publish-replay-behavior-async)

* **What are the types of Observables in RxJava?** - Learn from here: [Types Of Observables In RxJava](https://outcomeschool.com/blog/types-of-observables-in-rxjava)

* **How to implement search feature using RxJava in your application?** - Learn from here: [Instant Search Using RxJava Operators](https://outcomeschool.com/blog/instant-search-using-rxjava-operators)

* **Pagination In RecyclerView Using RxJava Operators** - [Learn from here](https://outcomeschool.com/blog/pagination-in-recyclerview-using-rxjava-operators)

* **How The Android Image Loading Library Glide and Fresco Works?** - [Learn from here](https://outcomeschool.com/blog/android-image-loading-library-optimize-memory-usage), [here](https://outcomeschool.com/blog/android-image-loading-library-use-bitmap-pool-for-responsive-ui) and [here](https://outcomeschool.com/blog/android-image-loading-library-solve-the-slow-loading-issue)

* **Difference between Schedulers.io() and Schedulers.computation() in RxJava.**

### Android Architecture

Android Interview Questions and Answers:

* **Describe the architecture of your last app.**

* **Describe MVVM.** - [MVVM Architecture](https://outcomeschool.com/blog/mvvm-architecture-android)

* **MVC vs MVP vs MVVM architecture.**

* **Clean Architecture** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_androiddev-kotlin-activity-7123192186627571714-6143)

* **MVI** - [MVI (Model-View-Intent) Architecture in Android](https://www.linkedin.com/posts/amit-shekhar-iitbhu_outcomeschool-softwareengineering-tech-activity-7288428333430644738-muDc)

* **Software Architecture vs Software Design** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineering-tech-activity-7230434583584858112-mMEG)

### Design Pattern

Android Interview Questions and Answers

* **Builder** - [Learn from here](https://www.linkedin.com/posts/pallavi-shekhar_outcomeschool-softwareengineer-tech-activity-7297905207080800256-sRuJ)
* **Singleton**
* **Factory** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_outcomeschool-softwareengineer-tech-activity-7300164529571733505-MYfP)
* **Observer** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineer-tech-activity-7298657173910233089-3qzw)
* **Repository**
* **Adapter**
* **Facade**
* **Dependency Injection**
* **Design Pattern used in Android** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineering-tech-activity-7289501147243982848-hhym)
* **Kotlin Optional Parameters vs Builder Pattern** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_softwareengineer-androiddev-android-activity-7270656113845370881-LDW8)
* **Examples of the Observer pattern used in Android** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_androiddev-activity-7288114509120970752-Z6c8)
* **Design Pattern Used in Retrofit Library Source Code** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_androiddev-opensource-activity-7289173219142516738-3sjB/)
* **Design Pattern used in Glide (Image Loading Library)** - [Learn from here](https://www.linkedin.com/posts/pallavi-shekhar_androiddev-android-opensource-activity-7294335764249595904-6LSD)

### Android System Design

Android Interview Questions and Answers:

Refer to this blog: [**Android System Design Interviews**](https://outcomeschool.com/blog/android-system-design-interviews) 

* **Design an Image Loading Library** - [Learn from here](https://outcomeschool.com/blog/android-image-loading-library-optimize-memory-usage), [here](https://outcomeschool.com/blog/android-image-loading-library-use-bitmap-pool-for-responsive-ui) and [here](https://outcomeschool.com/blog/android-image-loading-library-solve-the-slow-loading-issue)

* **Design File Downloader Library** - [Learn from here](https://github.com/amitshekhariitbhu/PRDownloader)

* **Design WhatsApp**

* **Design Instagram Stories**

* **Design Networking Library**

* **Design Facebook Near-By Friends App**

* **Design Caching Library.**

* **Design problems based on location-based app**

* **How to build an offline-first app? Explain the architecture**

* **Design LRU Cache**

* **Design Analytics Library**

* **HTTP Request vs HTTP Long-Polling vs WebSocket vs Server-Sent Events** - [Learn from blog](https://outcomeschool.com/blog/http-request-long-polling-websocket-sse) and [Video - HTTP Request vs HTTP Long-Polling vs WebSocket vs Server-Sent Events](https://www.youtube.com/watch?v=8ksWRX4xV-s)

* **How do Voice And Video Call Work?** - [Learn from here](https://outcomeschool.com/blog/voice-and-video-call)

* **Design Uber App** - [Learn from here](https://github.com/amitshekhariitbhu/ridesharing-uber-lyft-app)

* **Database Normalization vs Denormalization** - [Database Normalization vs Denormalization](https://outcomeschool.com/blog/database-normalization-vs-denormalization)

* **Hash vs Encrypt vs Encode** - [Learn from here](https://www.linkedin.com/posts/pallavi-shekhar_outcomeschool-softwareengineering-activity-7227173077665660929--KD8)

* **Webhook vs Polling** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_softwareengineer-activity-7265962230553223168-fsPx)

* **Options for real-time updates in an Android App** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_androiddev-android-activity-7287460425212866560-dJNB)

* **Options for Network Optimization in a Mobile App** - [Options for Network Optimization in a Mobile App](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineering-tech-activity-7287470994447900672-XYM9)

* **Firebase Remote Config in Android** - [Firebase Remote Config in Android](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineering-tech-activity-7288408601944043520-pHZX)

* **Accurate time in Android** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineer-tech-activity-7298341712634990592-tgyR)

* **Query Optimization in SQLite for Better Performance** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_outcomeschool-softwareengineer-tech-activity-7299289876846284801-3gfH)

* **WebSocket vs Socket.IO** - [Learn from here](https://www.linkedin.com/posts/pallavi-shekhar_outcomeschool-softwareengineer-tech-activity-7305902742537916416-C5b9)

### Android Unit Testing

Android Interview Questions and Answers:

* **Unit Testing ViewModel with Kotlin Coroutines and LiveData** - [Learn from here](https://outcomeschool.com/blog/unit-testing-viewmodel-with-kotlin-coroutines-and-livedata)

* **Unit Testing ViewModel with Kotlin Flow and StateFlow** - [Learn from here](https://outcomeschool.com/blog/unit-testing-viewmodel-with-kotlin-flow-and-stateflow)

* **What is Espresso?** - [Learn from here](https://developer.android.com/training/testing/espresso/basics)

* **What is Robolectric?** - [Learn from here](http://robolectric.org/)

* **What are the disadvantages of using Robolectric?** - [Learn from here](https://stackoverflow.com/questions/18271474/robolectric-vs-android-test-framework) 

* **What is UI-Automator?** - [Learn from here](https://developer.android.com/training/testing/ui-testing/uiautomator-testing.html)

* **Explain the unit test.** - [Learn from here](https://developer.android.com/training/testing/unit-testing/local-unit-tests)

* **Explain instrumented test.** - [Learn from here](https://developer.android.com/training/testing/unit-testing/instrumented-unit-tests)

* **Why Mockito is used?** - [Learn from here](http://site.mockito.org/)

* **Describe code coverage.** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineer-tech-activity-7298564060105609217-8zXA)

### Android Tools And Technologies

Android Interview Questions and Answers:

* **CI/CD Pipeline for Android** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_softwareengineer-androiddev-android-activity-7294600775178063872-Q0oY/)

* **What is ADB?** - [Learn from here](https://developer.android.com/studio/command-line/adb)

* **What is the StrictMode?** - Learn from here: [StrictMode](https://outcomeschool.com/blog/strictmode-in-android-development)

* **What is Lint? What is it used for?**

* **Android App Release Checklist For The Production Launch** - Learn from here: [Android App Release Checklist For The Production Launch](https://www.linkedin.com/posts/amit-shekhar-iitbhu_androiddev-android-activity-7275029928692080640-HIhx)

* **Git.**

* **Firebase.** - [Learn from here](https://firebase.google.com/)

* **How to measure method execution time in Android?**

* **Can you access your database of SQLite Database for debugging?** - [Learn from here](https://github.com/amitshekhariitbhu/Android-Debug-Database)

* **What are things that we need to take care while using Proguard?**

* **How to use Android Studio Memory Profiler?**

* **What is Kotlin DSL for Gradle?** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_softwareengineer-androiddev-android-activity-7282624364695404546-BvbS)

* **implementation vs api in Gradle** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineering-tech-activity-7287325379441082368-_P9m)

* **What is Gradle?**

* **Gradle related files in Android Project** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineering-tech-activity-7292045394778148864-mFVf)

* **How do you create a custom task in Gradle?** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_softwareengineer-androiddev-android-activity-7282991795133685760-uUxE/)

* **annotationProcessor, kapt, ksp in Gradle** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_outcomeschool-softwareengineer-tech-activity-7296566489803866112-DnT8)

* **Build Variants in Android** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_outcomeschool-softwareengineer-tech-activity-7298197111030824962-6vW0)

* **APK Size Reduction.**

* **How can you speed up the Gradle build?**

* **About gradle build system.**

* **About multiple apk for Android Apps.**

* **What is ProGuard used for?** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_outcomeschool-activity-7218840466283220993-afVr)

* **What is proguard-rules.pro file used for?** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_outcomeschool-softwareengineer-tech-activity-7300763237942181888-P_jL)

* **What is obfuscation? What is it used for? What about minification?**

* **How to change some parameters in an app without app update?** - [Firebase Remote Config in Android](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineering-tech-activity-7288408601944043520-pHZX)

* **What is Write-Ahead Logging (WAL) and why it is used internally in databases?** - [Learn from here](https://outcomeschool.com/blog/write-ahead-logging)

### Java

Android Interview Questions and Answers:

#### Solid Principles

* **“S” in SOLID Principles: The Single Responsibility Principle** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineering-tech-activity-7234425076308164611-sY57)
* **"O" in SOLID Principles: Open/Closed Principle** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineering-tech-activity-7287026079851061248-bjdM)
* **“L” in SOLID Principles: Liskov Substitution Principle (LSP)** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineering-tech-activity-7300845161725448193-iCnO)
* **“I” in SOLID Principles: Interface Segregation Principle (ISP)** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineer-tech-activity-7301459048292397056--9bL)
* **“D” in SOLID Principles: Dependency Inversion Principle (DIP)** - [Learn from here](https://www.linkedin.com/posts/outcomeschool_outcomeschool-softwareengineer-tech-activity-7303987022493270016-VrZL)

#### OOP

* **Explain OOP Concepts.**

* **Differences between abstract classes and interfaces?** 
    - An abstract class, is a class that contains both concrete and abstract methods 
    (methods without implementations). An abstract method must be implemented by the abstract class
     sub-classes. Abstract classes cannot be instantiated and need to be extended to be used.
    - An interface is like a blueprint/contract of a class (or it may be thought of as a class with methods, but without their implementation). It contains empty methods that 
    represent, what all of its subclasses should have in common. The subclasses provide the 
    implementation for each of these methods. Interfaces are implemented.

* **Difference between method overloading and overriding.**

* **What are the access modifiers you know? What does each one do?**
   - There are four access modifiers in Java language (from strictest to the most lenient):
        1. `private` *variables*, *methods*, *constructors* or *inner classes* are only visible to its' containing class and its' methods. This modifier is most commonly used, for example, to allow variable access only through getters and setters or to hide underlying implementation of classes that should not be used by user and therefore maintain encapsulation. Singleton constructor is also marked `private` to avoid unwanted instantiation from outside.
        2. `Default` (no keyword is used) this modifier can be applied to *classes*, *variables*, *constructors* and *methods* and allows access from classes and methods inside the same package.
        3. `protected` can be used on *variables*, *methods* and *constructors* therefore allowing access only to subclasses and classes that are inside the same package as protected members' class.
        4. `public` modifier is widely-used on *classes*, *variables*, *constructors* and *methods* to grant access from any class and method anywhere. It should not be used everywhere as it implies that data marked with `public` is not sensitive and can not be used to harm the program.

* **Can an Interface implement another Interface?**
  - Yes, an interface can implement another interface (and more than one), but it needs to use `extends`, rather than `implements` keyword. And while you can not remove methods from parent interface, you can add new ones freely to your sub-interface.

* **What is Polymorphism? What about Inheritance?**

#### Collections and Generics

* **Arrays Vs ArrayLists** - [Learn from here](https://stackoverflow.com/questions/32020000/what-is-the-difference-between-an-array-arraylist-and-a-list/32020072)

* **HashSet Vs TreeSet** - [Learn from here](https://stackoverflow.com/questions/25602382/java-hashset-vs-treeset-when-should-i-use-over-other)

* **HashMap Vs Set** - [Learn from here](https://stackoverflow.com/questions/2773824/difference-between-hashset-and-hashmap)

* **Explain Generics in Java?**

#### Objects and Primitives

* **How is `String` class implemented? Why was it made immutable?**
  - There is no primitive variant of `String` class in Java language - all strings are just wrappers around underlying array of characters, which is declared `final`. This means that, once a `String` object is instantiated, it cannot be changed through normal tools of the language (Reflection still can mess things up horribly, because in Java no object is truly immutable). This is why `String` variables in classes are the first candidates to be used, when you want to override `hashCode()` and `equals()` of your class - you can be sure, that all their required contracts will be satisfied.
    > Note: The String class is immutable, so that once it is created a String object cannot be changed. The String class  has a number of methods, some of which will be discussed below, that appear to modify strings. Since strings are  immutable, what these methods really do is create and return a new string that contains the result of the operation. ([Official Java Documentation](https://docs.oracle.com/javase/tutorial/java/data/strings.html))

    This class is also unique in a sense, that, when you create an instance like this:
    ```java
    String helloWorld = "Hello, World!";
    ```
    `"Hello, World!"` is called a *literal* and compiler creates a `String` object with its' value. So
    ```java
    String capital = "Hello, World!".toUpperCase();
    ```
    is a valid statement, that, firstly, will create an object with literal value "Hello, World!" and then will create and return another object with value "HELLO, WORLD!"
  - `String` was made immutable to prevent malicious manipulation of data, when, for example, user login or other sensitive data is being send to a server.

* **What does it means to say that a `String` is immutable?**
    - It means that once created, `String` object's `char[]` (its' containing value) is declared `final` and, therefore, it can not be changed during runtime.

* **Can you list 8 primitive types in java?**
    - `byte`
    - `short`
    - `int`
    - `long`
    - `float`
    - `double`
    - `char`
    - `boolean`

* **What is the difference between an Integer and int?**
  - `int` is a primitive data type (with `boolean`, `byte`, `char`, `short`, `long`, `float` and `double`), while `Integer` (with `Boolean`, `Byte`, `Character`, `Short`,`Long`, `Float` and `Double`) is a [wrapper](https://docs.oracle.com/javase/tutorial/java/data/numberclasses.html) class that encapsulates primitive data type, while providing useful methods to perform different tasks with it.

* **Do objects get passed by reference or value in Java? Elaborate on that.**

#### Java Memory Model and Garbage Collector

* **What is garbage collector? How does it work?**
  - All objects are allocated on the heap area managed by the JVM.
  As long as an object is being referenced, the JVM considers it alive.
  Once an object is no longer referenced and therefore is not reachable by the application code,
  the garbage collector removes it and reclaims the unused memory.

#### Concurrency

* **What does the keyword `synchronized` mean?**

* **What is a `ThreadPoolExecutor`?** - [ThreadPoolExecutor in Android](https://outcomeschool.com/blog/threadpoolexecutor-in-android)

* **What is `volatile` modifier?**

* **Object Level Lock vs Class Level Lock in Java** - [Learn from here](https://x.com/amitiitbhu/status/1818156936413778332)

* **Concurrency vs Parallelism** - [Learn from here](https://www.linkedin.com/posts/pallavi-shekhar_outcomeschool-softwareengineering-activity-7226208648115404801-u8uu)

* **The classes in the atomic package expose a common set of methods: `get`, `set,`, `lazyset`, `compareAndSet`, and `weakCompareAndSet`. Please describe them.**

#### Exceptions

* **How does the `try{}`, `catch{}`, `finally` works?**

* **What is the difference between a `Checked Exception` and an `Un-Checked Exception`?**

#### Others

* **Shallow vs. Deep Copy in Java** - [Learn from here](https://www.linkedin.com/posts/amit-shekhar-iitbhu_outcomeschool-softwareengineering-activity-7224635014641016834-j8X1)

* **Explain Serialization and Deserialization** - [Learn from here](https://www.linkedin.com/posts/pallavi-shekhar_outcomeschool-softwareengineering-tech-activity-7228977637916823552-Bo2N)

* **What is serialization? How do you implement it?**

* **What is `transient` modifier?**

* **What are anonymous classes?**

* **What is the difference between using `==` and `.equals` on an object?**

* **What is the `hashCode()` and `equals()` used for?**

* **When would you make an object value `final`?**

* **What are these `final`, `finally` and `finalize` keywords?**

* **What is the difference between "throw" and "throws" keyword in Java?**
    - `throws` is just used to indicated which exception is to be thrown. But the `throw` keyword is used to throw some exception from any static block or any method.

* **What does the `static` word mean in Java?**
    - In case of `static` variable it means that this variable (its' value or the object it references) spans across all instances of enclosing class (changing it in one instance affects all others), while in case of `static` methods it means that these methods can be invoked without an instance of their enclosing class. It is useful, for example, when you create util classes that need not be instantiated every time you want to use them.

* **Can a `static` method be overridden in Java?**
    - While child class can override a static method with another static method with the same signature (return type can be down-casted), it is not truly overridden - it becomes "hidden", but both methods can still be accessed under right circumstances (see question about overloading/overriding above).

* **When is a `static` block run?**
    - Code inside static block is executed only once: the first time you make an object of that class or the first time you access a static member of that class (even if you never make an object of that class).

* **Explain Reflection in Java** - [Learn from here](https://x.com/amitiitbhu/status/1819234916812341567)

* **What is Dependency Injection?**

* **Difference between `StringBuffer` and `StringBuilder`?** - [Learn from here](https://outcomeschool.com/blog/string-vs-stringbuffer-vs-stringbuilder)

* **What is the difference between fail-fast and fail-safe iterators in Java?**

* **Monitor and Synchronization**

### Jetpack Compose

Topics you should know in **Jetpack Compose** for Android Interview:

* Compose
* State: remember, rememberSaveable, MutableState
* Recomposition
* State hoisting
* Side-effects
* Modifier
* Theme
* Layout, List
* Gestures, Animation
* CompositionLocal

Learn the above-mentioned from the following links:

- [Getting Started with Compose](https://developer.android.com/jetpack/compose/tutorial)
- [Thinking in Compose](https://developer.android.com/jetpack/compose/mental-model)
- [State](https://developer.android.com/jetpack/compose/state)
- [remember vs rememberSaveable](https://outcomeschool.com/blog/remember-vs-remembersaveable)
- [Lifecycle](https://developer.android.com/jetpack/compose/lifecycle)
- [Modifiers](https://developer.android.com/jetpack/compose/modifiers)
- [Side-effects](https://developer.android.com/jetpack/compose/side-effects)
- [Phases](https://developer.android.com/jetpack/compose/phases)
- [Semantics](https://developer.android.com/jetpack/compose/semantics)
- [CompositionLocal](https://developer.android.com/jetpack/compose/compositionlocal)
- [Can we use traditional Android Views and Compose together?](https://www.linkedin.com/posts/amit-shekhar-iitbhu_outcomeschool-softwareengineering-tech-activity-7235142707138961408-40hQ)

Questions

* **Jetpack Compose vs Android View System**
  
* **Explain the concept of declarative UI in Jetpack Compose.**
  
* **Declarative UI vs Imperative UI**
  
* **What are Composable functions?**
  
* **What is Recomposition?**
  
* **What is State in Compose?**
  
* **How does state management work in Jetpack Compose?**
  
* **Stateful composable vs Stateless composable**
  
* **What are the side effects?**
  
* **Difference between LaunchedEffect and DisposableEffect**.
  
* **What is rememberCoroutineScope and its use cases?**
  
* **How to observe Flows, and LiveData states in Compose UI?**
  
* **How can we handle asynchronous operations in Jetpack Compose?**
  
* **How can we convert a non-compose state into a Compose state?**
  
* **Explain derivedStateOf.**
  
* **Explain rememberUpdatedState.**
  
* **Difference between remember and rememberSaveable.** - [Learn from here](https://outcomeschool.com/blog/remember-vs-remembersaveable)
  
* **Explain the Lifecycle of a Composable in Jetpack Compose.**
  
* **How do you handle lifecycle events in Compose functions?**
  
* **What are the best practices for performance optimization in Jetpack Compose?**
  
* **Can we use both Jetpack Compose and Android View in a Single App?**
  
* **What is State Hoisting?**
  
* **Explain CompositionLocal**
  
* **Explain Jetpack Compose Phases.**
  
* **What is the role of the Modifier in Jetpack Compose?**
  
* **What are Semantics?**
  
* **How can you handle user input and events in Jetpack Compose?**
  
* **How do you handle navigation in Jetpack Compose?**
  
* **How do you handle orientation changes in Jetpack Compose?**
  
* **Explain the concept of unidirectional data flow in Jetpack Compose.**
  
* **How to create Custom Layouts in Compose?**

### Other Topics

Android Interview Questions and Answers:

* **Describe SQLite.**

* **Have you used Room?**

* **Can we identify the users who have uninstalled our application?**

* **Android Development Best Practices.** - Learn from here: [Android Development Best Practices](https://outcomeschool.com/blog/android-development-best-practices)

* **React Native vs Flutter** - Learn from here: [React Native vs Flutter](https://outcomeschool.com/blog/react-native-vs-flutter)

* **What are the metrics that you should measure continuously while android application development?** - Learn from here: [Android App Performance Metrics](https://outcomeschool.com/blog/android-app-performance-metrics)

* **How to avoid API keys from check-in into VCS?**

* **How does the Kotlin Multiplatform work?** - [Blog](https://outcomeschool.com/blog/how-does-the-kotlin-multiplatform-work)

* **How to use Memory Heap Dumps data?**

* **How to implement Dark Theme in your app?**

* **How to secure the API keys used in an Android App?**

* **What is Cleartext traffic?** Learn from here: [What is Cleartext traffic?](https://www.linkedin.com/posts/amit-shekhar-iitbhu_softwareengineer-androiddev-android-activity-7281879316601126913-x1az)

* **Tell something about memory usage in Android.**

* **Explain Annotation processing.**

* **How does the Android Push Notification system work?** Learn from here: [How does the Android Push Notification system work?](https://youtu.be/810IFG2sWlc)

* **Android Push Notification Flow using FCM.** Learn from here: [Android Push Notification Flow using FCM](https://outcomeschool.com/blog/android-push-notification-flow-using-fcm)

* **How to show local Notification at an exact time?**

### Data Structures and Algorithms

* **Android Developer should know these Data Structures for Next Interview** - [Check here](https://outcomeschool.com/blog/android-developer-should-know-these-data-structures-for-next-interview)

### High-quality videos to prepare for Android Interview - [Amit Shekhar YouTube Channel](https://www.youtube.com/@amitshekhar)

### High-quality blogs to prepare for Android Interview - [Check here - Outcome School Blog](https://outcomeschool.com/blog)

### Found this project useful :heart:

* Support by clicking the :star: button on the upper right of this page. :v:

You can connect with me on:

- [Twitter](https://twitter.com/amitiitbhu)
- [YouTube](https://www.youtube.com/@amitshekhar)
- [LinkedIn](https://www.linkedin.com/in/amit-shekhar-iitbhu)
- [GitHub](https://github.com/amitshekhariitbhu)

### License
```
   Copyright (C) 2024 Amit Shekhar

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```
