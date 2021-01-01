# Android Jetpack Navigation component

In Android, we generally code the navigation logic using `Intent` to travel between activities and fragment transactions to navigate between fragments. Google’s Navigation Architecture Component simplifies navigation in the Android app. In this piece, we discuss both the basic and the advanced way of using the `Navigation` component.

**What was the problem?**

When developing the apps with multiple fragments we tend to do a lot of fragment transactions to navigate between them. Writing these fragment transactions and handling the back stack takes a certain amount of effort. If you don’t implement it the right way, another major issue is the `IllegalStateException` that can occur.

**Solution**

In order to make navigation easier, Google has introduced the Navigation component. With the help of the navigation component, it will be easy to code the navigation between fragments and handling cases like back stack, exception cases, etc. Let’s start exploring the Navigation component.

## What is the Navigation Component?

The `Navigation` component is a set of libraries, a plugin, and tooling that simplifies Android navigation. Android Jetpack’s `Navigation` component helps us to implement navigation, from simple button clicks to more complex patterns, such as app bars and the navigation drawer. The `Navigation` component also ensures a consistent and predictable user experience by adhering to an established set of principles.
The `Navigation` component consists of three key parts.

**Navigation graph**

This is a new resource type — an XML file that contains all navigation-related information in one centralized location. This includes all the individual content areas in your app, called destinations, as well as the possible paths a user can take through your app.

![Navigation](https://miro.medium.com/max/1050/1*K39Yeuk5yv_F-zbGDB0ktw.png)

The `Navgraph` from the navigation editor can be visualized as above. The screens above are called destinations — they’re are nothing but fragments. The arrows between these destinations are called actions — they define the paths the user can take navigate.

**NavHost**

This is an empty container that displays destinations from your navigation graph. The `Navigation` component contains a default `NavHost` implementation `NavHostFragment`, which displays fragment destinations.

**NavController**

An object that manages app navigation within a `NavHost`. The `NavController` orchestrates the swapping of destination content in the `NavHost` as users move through your app.

**Benefits**

The `Navigation` component provides a number of other benefits, including:

* Handling fragment transactions.
* Handling `Up` and `Back` actions correctly by default.
* Providing standardized resources for animations and transitions.
* Implementing and handling deep linking.
* Including navigation UI patterns, such as navigation drawers and bottom navigation, with minimal additional work.
* `ViewModel` support — you can scope a `ViewModel` to a navigation graph to share UI-related data between the graph’s destinations.

## Example

Let’s look at how this component works by creating a simple example. We’ll create a simple `Activity` with two fragments and check how we can use `Navigation` component to navigate between these fragments.

**Step 1**

Create a new project with androidx support or refactor your codebase to support androidx. AndroidX is the open-source project that the Android team uses to develop, test, package, version and release libraries within Jetpack. Check out more at <a href="https://developer.android.com/jetpack/androidx">Androidx OverView</a>.

**Step 2**

Add dependencies in `build.gradle`.

**Step 3**

Create a navigation graph.
To add a navigation graph to your project:

* In the project window, right-click on the res directory and select New > Android Resource File. The New Resource File dialog appears.
* Type a name in the File name field, such as “nav_graph”.
* Select Navigation from the Resource type drop-down list, and then click OK.

When you add your first navigation graph, Android Studio creates a navigation resource directory within the res directory. This directory contains your navigation graph resource file. The file created will looking something like this:

```
<?xml version="1.0" encoding="utf-8"?>
<navigation xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/nav_graph">
</navigation>
```
The `<navigation>` element is the root element of a navigation graph. As you add destinations and connecting actions to your graph, you can see the corresponding `<destination>` and `<action>` elements here as child elements. If you have <a href="https://developer.android.com/guide/navigation/navigation-nested-graphs">nested graphs</a>, they appear as child `<navigation>` elements.

**Step 3**

Add a `NavHost` to an activity XML file
Anatomy of a `nav_host_fragment`:

* The `android:name` the attribute contains the class name of your `NavHost`. implementation.
* The `app:navGraph` attribute associates the `NavHostFragment` with a navigation graph. The navigation graph specifies all of the destinations in this `NavHostFragment` to which users can navigate.
* The `app:defaultNavHost=”true”` attribute ensures that your `NavHostFragment` intercepts the system Back button. Note that only one NavHost can be the default. If you have multiple hosts in the same layout (two-pane layouts, for example), be sure to specify only one default NavHost.

**Step 4**

Add destinations and paths in `nav_graph`.
Before adding destinations create two fragments and their XMLs.

Now create the XML file for FragmentOne class.
Similarly, create the second fragment. 

Now let’s add the destinations to the `nav_graph`.
Anatomy of a destination:

* The `Type` field indicates whether the destination is implemented as a fragment, activity, or other custom class in your source code.
* The `Label` field contains the name of the destination’s XML layout file.
* The `ID` field contains the ID of the destination which is used to refer to the destination in code.
* The `Class` dropdown shows the name of the class that is associated with the destination. You can click this dropdown to change the associated class to another destination type.

Now add `NavHost` to the `activity_main` XML file:

```
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">



    <fragment
        android:id="@+id/nav_host_fragment"
        android:name="androidx.navigation.fragment.NavHostFragment"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:defaultNavHost="true"
        app:navGraph="@navigation/nav_graph" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

Our `MainActivity` will look like this:

```
package com.example.navigationsample
import android.support.v7.app.AppCompatActivity
import android.os.Bundle
import androidx.navigation.findNavController
class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
    }
    override fun onSupportNavigateUp() = findNavController(R.id.nav_host_fragment).navigateUp()
}
```
That’s it — we’re done.
