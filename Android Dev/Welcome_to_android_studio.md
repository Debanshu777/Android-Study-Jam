# Welcome to Android Studio
Android Studio is the official Integrated Development Environment (IDE) for Android app development, based on <a href="https://www.jetbrains.com/idea/">IntelliJ IDEA</a> . On top of IntelliJ's powerful code editor and developer tools, Android Studio offers even more features that enhance your productivity when building Android apps, such as:
* A flexible Gradle-based build system
* A fast and feature-rich emulator
* A unified environment where you can develop for all Android devices
* Apply Changes to push code and resource changes to your running app without restarting your app
* Code templates and GitHub integration to help you build common app features and import sample code
* Extensive testing tools and frameworks
* Lint tools to catch performance, usability, version compatibility, and other problems
* C++ and NDK support
* Built-in support for Google Cloud Platform, making it easy to integrate Google Cloud Messaging and App Engine
## Project Structure
Each project in Android Studio contains one or more modules with source code files and resource files. Types of modules include:
* Android app modules
* Library modules
* Google App Engine modules

By default, Android Studio displays your project files in the Android project view, as shown in figure. This view is organized by modules to provide quick access to your project's key source files.
![Project Structure](https://static.packt-cdn.com/products/9781788473699/graphics/8db2b24b-4f7c-4377-b60b-ec09e4027ac9.png)

All the build files are visible at the top level under Gradle Scripts and each app module contains the following folders:
* **manifests**: Contains the AndroidManifest.xml file.
* **java**: Contains the Java source code files, including JUnit test code.
* **res**: Contains all non-code resources, such as XML layouts, UI strings, and bitmap images.

For more information, see <a href="https://developer.android.com/studio/projects">Projects overview</a>.
## The user interface
The Android Studio main window is made up of several logical areas identified in figure.
![Android Studio](https://developer.android.com/studio/images/intro/main-window_2-2_2x.png)
<ol>
<li>The toolbar lets you carry out a wide range of actions, including running your app and launching Android tools.</li>
<li>The navigation bar helps you navigate through your project and open files for editing. It provides a more compact view of the structure visible in the Project window.</li>
<li>The editor window is where you create and modify code. Depending on the current file type, the editor can change. For example, when viewing a layout file, the editor displays the Layout Editor.</li>
<li>The tool window bar runs around the outside of the IDE window and contains the buttons that allow you to expand or collapse individual tool windows.</li>
<li>The tool windows give you access to specific tasks like project management, search, version control, and more. You can expand them and collapse them.</li>
<li>The status bar displays the status of your project and the IDE itself, as well as any warnings or messages.</li>
</ol>
You can organize the main window to give yourself more screen space by hiding or moving toolbars and tool windows. You can also use keyboard shortcuts to access most IDE features.

At any time, you can search across your source code, databases, actions, elements of the user interface, and so on, by double-pressing the Shift key, or clicking the magnifying glass in the upper right-hand corner of the Android Studio window. This can be very useful if, for example, you are trying to locate a particular IDE action that you have forgotten how to trigger.

For more info regarding tool windows,code completion,navigation,style and formatting in android studio you can refer to the official <a href="https://developer.android.com/studio/intro">docs</a>.s