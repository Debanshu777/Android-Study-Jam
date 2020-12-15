# Android development for beginners
## Introduction
Android is a platform where apps are built and deployed. The process of building apps is a typical way of learning and experimenting with different things. In Android development there also the flexibility of choosing languages like Java or Kotlin for development. It’s not so complicated to begin and do some basic stuff but for mastering anything takes much time so be patient. Things will be simple in the first phase once you dig a little you understand the depth.
<br>

## Why learn android
One important thing about learning Android is you can explore the entire SDLC(Software Development lifecycle) on your own. Let’s take a simple example of creating a simple app of displaying a list of customized smileys with share feature. For this simple thing, you can define the scope of your application, sit and analyze the requirements with ease, develop it, and deploy it to the Play Store with minimal cost of 25USD as a lifetime fee. Later you have many free tools like firebase Analytics and Crashlytics where you can track your users and do the changes for better user engagement. These things if you are proficient in Android can be done in one day nothing much so rush in and crush it.<br>

Android development mainly consists of two basic things like:
* UI(User Interface) design part.
* Management of the UI stuff and handling of other things like networking, storage management, etc.

We will discuss what are the basic things needed for a person who wants to start learning Android Development.

## Select a language of your choice for development
At the start point of Android development, Java is the only language for developing Android apps. Things don’t remain the same all the time, After the introduction of Kotlin, it has become the preferred language both by the developers and Google. So Google announced Kotlin as the first preferred language for the development of Android in I/O held in 2019. As everyone has their tastes so choose as per yours.

But suggestion would always be Kotlin because the ease of learning and adoption is great and also the most libraries available out there are being developed in Kotlin. Most top apps already ported their apps to Kotlin.
## Start with UI design
Just go to the official site in our case the Wikipedia of Android Development is always been <a href="https://developer.android.com">Android Developers</a>. Go to the official site check the IDE and system requirements. Android Studio is our IDE to scratch the hands.

Once you setup your environment just explore the options and start kicking in with UI design. We basically do it in layout files with XML (Extensible Markup Language) code. The first and foremost important thing is UI it’s not a simple thing to take because everything we do here the user experiences it. The good design creates a great experience and will be a good standing factor for app success rate. Regardless of how much stuff the app has, it will always be like a drowning ship without good UI/UX.

The individual thing or component which we see on the screen we refer them commonly as Views because View is the base class for all the widgets available. The individual button or text or image you see on the screen is commonly referred to as a view. And the component that has the collection of certain views is called ViewGroup. So let’s go a bit deeper if you see a text on the screen we generally use TextView or if you see an image we use ImageView, depending on the requirement we use the widgets available.

The files used for UI design are called layouts. On the project structure on the left-hand side, you can find them by navigation to folders: **res →layout → layout_file**

Next is learning about various views and ViewGroups available.The basic layouts used from the start are Relative and Linear for most purposes and rarely FrameLayout at the starting of Android Development. Explore more about layouts <a href="https://developer.android.com/guide/topics/ui/declaring-layout">here</a>.
Now there are many layouts that came into existence but one that gained most attention is Constraint Layout for aligning views and removing nested hierarchies.The second important layout is Motion layout which gained popularity recently for its ease of handling animations.

## Management of the UI stuff
This is also one more important step to take care of. Layouts are for UI designs and classes like what we call Activities and fragments are to hold the container layouts and display them to the users with clicks management, showing and hiding loaders as required, etc.

A class which we call Activity is a single screen which you see on any App. And fragment classes are the portions inside the activity. There can be multiple fragments visible to the user but mostly at a time user can see one Activity. These classes will be in the **src** folder. Here we create the classes and extend them with Activity or Fragment and then bind the layouts created accordingly and write the code for state management or clicks for the views, declare Activities in Manifest and render them by running the app. Isn’t that easy single line of the statement. At first, it takes a few minutes but once you are accustomed to it, it may take a minute for simply binding layout, declaring in the manifest, and running the app.
Think of activity is a simple class extending some other class binding a view with it inside the **setContentView** method that will be shown to the user.

An activity has a lifecycle with callback methods where we can do our stuff. Suppose the app is going to background a set of methods in the Activity gets invoked where we can do our stuff and vice-versa. We need to register the activity in the manifest file.Here is the guide for Activities stuff from our beloved <a href="https://developer.android.com/reference/android/app/Activity">Android Developers site</a>. You can explore a lot of things in it. It will take days at least to explore & experiment with each and everything related Activity.

## Basics of networking
As every application these days has networking included it was almost important to learn networking at the start point rather than demanding situation. We use networking basically to hit an API and get the data to display it or to hit the API and send some data for CRUD operation at the server-side, etc. The requirement may be anything but networking is a basic common thing we do almost in all apps. This is because when a user does something after few days he uninstalls the app and later on he reinstalls it we don’t want to make the user uncomfortable to start from the beginning he should ideally resume where he stopped. So we do networking to record the session or snapshot of users with the app.
You no need to create everything thing from scratch because there are many libraries available like Retrofit, Volley, etc for better management. So explore them and try integrating the basic things with open API’s.

## Storage
Android provides us different storage mechanisms like SharedPerfernces, Database, Disk Storage, etc. Which type to choose depends on the requirement again. Explore all these basic types it don't take much time. To save basic key-value pairs use SharedPerfernces, to save huge data in tables use database and for saving images or files we use disk storage.
The popular database we use currently is ROOM which is very easy to use. We no need to write statements for the creation of tables and fetching data everything is in the format of data classes or models or POJO(Plain Old Java Objects). If you want to experience a more traditional approach use the SQLite database with SQliteOpenHelper.

## Threading
Not only in Android threading is equally important in almost all programming languages. It’s obviously asked in most interviews. Thread a lightweight process to do some stuff. Why do we need threads? Android launches its applications with a single UI or Main thread that handles things related to UI. So if you do some network operation on the Main thread it crashes saying Network on main thread exception. And if you do some heavy logical operation or holding main thread then UI freezes and the application will not be as responsive as expected and even in some worst cases, it shows ANR’s(Android Not Responding) dialogs. So we need to be careful while dealing with thread to avoid unnecessary situations.
You can’t touch the UI elements from different threads you need to use **runOnUithread** to access UI from background threads. Android provides a custom component called Handler which is similar to a thread but Android specific to do stuff related to UI.

## Summary
Though there are many more things but these are the basic ones that would be helpful for a beginner as an android developer.If you want deep dive further into android then you can always refer to the official <a href="https://developer.android.com/guide">Documentation</a> or you can check out this awesome article by <a href="https://medium.com/mindorks/learning-android-development-in-2019-a-practical-guide-ddc71e008696">MindOrks</a>.