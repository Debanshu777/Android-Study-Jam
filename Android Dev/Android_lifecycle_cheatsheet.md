# Android lifecycle cheatsheet
Android is designed to empower users and let them use apps in a intuitive way. For example, users of an app might rotate the screen, respond to a notification, or switch to another task, and they should be able to continue using the app seamlessly after such an event.

To provide this user experience, you should know how to manage component lifecycles. A component can be an Activity, a Fragment, a Service, the Application itself and even the underlying process. The component has a lifecycle, during which it transitions through states. Whenever a transition happens, the system notifies you via a lifecycle callback method.

To help us explain how lifecycles work, we’ve defined a series of scenarios which are grouped according to the components that are present:

## Activities - single activity lifecycle

**Scenario 1- App is finished and restarted:**<br>

Triggered by:
* The user presses the Back button, or
* The `Activity.finish()` method is called

The simplest scenario shows what happens when a single-activity application is started, finished and restarted by the user:
![Lifecycle](https://miro.medium.com/max/575/1*U_j3OP74jrPFoNvO2i7XzQ.png)

Managing state:

* `onSaveInstanceState` is not called (since the activity is finished, you don’t need to save state)
* `onCreate` doesn’t have a Bundle when the app is reopened, because the activity was finished and the state doesn’t need to be restored.

**Scenario 2 - User navigates away**

Triggered by:
* The user presses the Home button
* The user switches to another app (via Overview menu, from a notification, accepting a call, etc.)

![Lifecycle](https://miro.medium.com/max/662/1*3qxYnT2vRwrQVORi9mfUhw.png)

In this scenario the system will stop the activity, but won’t immediately finish it.

Managing state:

When your activity enters the Stopped state, the system uses onSaveInstanceState to save the app state in case the system kills the app’s process later on.

Assuming the process isn’t killed, the activity instance is kept resident in memory, retaining all state. When the activity comes back to the foreground, the activity recalls this information. You don’t need to re-initialize components that were created earlier.

**Scenario 3: Configuration changes**

Triggered by:
* Configuration changes, like a rotation
* User resizes the window in multi-window mode

![Lifecycle](https://miro.medium.com/max/723/1*DCo7awxJ3KhnW88h365vhA.png)

Managing state:

Configuration changes like rotation or a window resize should let users continue exactly where they left off.

* The activity is completely destroyed, but the state is saved and restored for the new instance.
* The Bundle in `onCreate` and `onRestoreInstanceState` is the same.

**Scenario 4: App is paused by the system**

Triggered by:
* Enabling Multi-window mode (API 24+) and losing the focus
* Another app partially covers the running app (a purchase dialog, a runtime permission dialog, a third-party login dialog…)
* An intent chooser appears, such as a share dialog

![Lifecycle](https://miro.medium.com/max/785/1*j3blnCW082yMbQe5fkjMMg.png)

## Multiple activities — navigation and back stack

**Scenario 1: Navigating between activities**

In this scenario, when a new activity is started, activity 1 is STOPPED (but not destroyed), similar to a user navigating away (as if “Home” was pressed).
When the Back button is pressed, activity 2 is destroyed and finished.

![Lifecycle](https://miro.medium.com/max/1050/1*Bt1fQmVtZc0ExHUlzhJO6Q.png)

Managing state:

Note that `onSaveInstanceState` is called, but `onRestoreInstanceState` is not. If there is a configuration change when the second activity is active, the first activity will be destroyed and recreated only when it’s back in focus. That’s why saving an instance of the state is important.

If the system kills the app process to save resources, this is another scenario in which the state needs to be restored.

**Scenario 2: Activities in the back stack with configuration changes**

![Lifecycle](https://miro.medium.com/max/1050/1*TaoqKwKSPur_2S__OzhdoQ.png)

Managing state

Saving state is not only important for the activity in the foreground. All activities in the stack need to restore state after a configuration change to recreate their UI.
Also, the system can kill your app’s process at almost any time so you should be prepared to restore state in any situation.

**Scenario 3: App’s process is killed**

When the Android operating system needs resources, it kills apps in the background.

![Lifecycle](https://miro.medium.com/max/1050/1*Au5PqGADz31UCfANL3ZRug.png)

Managing state

Note that the state of the full back stack is saved but, in order to efficiently use resources, activities are only restored when they are recreated.

## Fragments — activity and fragment lifecycle 

In this section we’ll cover the behavior of a fragment that is attached to an activity. Don’t confuse this scenario with that of a fragment added to the back stack

**Scenario 1: Activity with Fragment starts and finishes**

![Lifecycle](https://miro.medium.com/max/1041/1*ALMDBkuAAZ28BJ2abmvniA.png)

Note that it’s guaranteed that the Activity’s onCreate is executed before the Fragment’s. However, callbacks shown side by side — such as `onStart` and `onResume` — are executed in parallel and can therefore be called in either order. For example, the system might execute the Activity’s `onStart` method before the Fragment’s `onStart` method, but then execute the Fragment’s `onResume` method before the Activity’s `onResume method`.

**Scenario 2: Activity with Fragment is rotated**

![Lifecycle](https://miro.medium.com/max/1050/1*ukapaC23cOJSPUeZ0bUdCA.png)

State management

Fragment state is saved and restored in very similar fashion to activity state. The difference is that there’s no onRestoreInstanceState in fragments, but the Bundle is available in the fragment’s `onCreate`, `onCreateView` and `onActivityCreated`.
Fragments can be retained, which means that the same instance is used on configuration change. As the next scenario shows, this changes the diagram slightly.

**Scenario 3: Activity with retained Fragment is rotated**

![Lifecycle](https://miro.medium.com/max/1050/1*hK_YRdty1GoafABfug-r4g.png)

The fragment is not destroyed nor created after the rotation because the same fragment instance is used after the activity is recreated. The state bundle is still available in `onActivityCreated`.

Using retained fragments is not recommended unless they are used to store data across configuration changes (in a non-UI fragment). This is what the <a href="https://developer.android.com/topic/libraries/architecture/viewmodel.html">ViewModel</a> class from the Architecture Components library uses internally, but with a simpler API.

You can also check out this <a href="https://blog.mindorks.com/android-fragments-and-its-lifecycle">post</a> to know more about fragment lifecycle.
