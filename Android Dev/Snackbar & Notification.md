# Snackbar & Notification
###   Snackbar
Snackbar provides lightweight feedback about an operation. The message appears at the bottom of the screen on mobile and lower left on larger devices. Snackbar appears above all the elements of the screen. But no component is affected by it. Steps to implement are mentioned below:

- Add the support Library in build.gradle file and add Material Design dependency in the dependencies section.It is a part of Material Design that’s why we have to add a dependency.

> `dependencies { 
	implementation 'com.google.android.material:material:1.1.0' 
} `

- Now add the following code in the activity_main.xml file. 
<b>activity_main.xml</b>

 ```<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
   xmlns:tools="http://schemas.android.com/tools"
   android:layout_width="match_parent"
   android:layout_height="match_parent"
   tools:context=".MainActivity">
   <TextView
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:layout_centerHorizontal="true"
      android:layout_marginTop="50dp"
      android:text="DSC KIIT"
      android:textAlignment="center"
      android:textColor="@android:color/holo_green_dark"
      android:textSize="32sp"
      android:textStyle="bold" />
   <TextView
      android:id="@+id/textView"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:layout_centerInParent="true"
      android:text="Click the button to display snackBar"
      android:textColor="@android:color/background_dark"
      android:textSize="24sp"
      android:textStyle="bold|italic" />
   <Button
      android:id="@+id/btnSnackBar"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:layout_below="@id/textView"
      android:layout_centerInParent="true"
      android:layout_marginTop="10dp"
      android:text="Tap To Display SnackBar"
      android:textColor="@android:color/background_dark" />
</RelativeLayout>
```

- Now add the following code in the **MainActivity.kt** file. This will define the button and add a onClickListener to the button. In the onClickListener a Snackbar is created and is called. So whenever the button is clicked, the onClickListener creates a snackbar and calls it and the user sees the message. This snackbar contains an action and if clicked will show a toast.

<b>MainActivity.kt</b>

```
import android.graphics.Color
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.Button
import android.widget.TextView
import com.google.android.material.snackbar.Snackbar
class MainActivity : AppCompatActivity() {
   lateinit var button: Button
   override fun onCreate(savedInstanceState: Bundle?) {
      super.onCreate(savedInstanceState)
      setContentView(R.layout.activity_main)
      title = "KotlinApp"
      button = findViewById(R.id.btnSnackBar)
      button.setOnClickListener {
         val snackBar = Snackbar.make(
            it, "Replace with your own action",
            Snackbar.LENGTH_LONG
         ).setAction("Action", null)
         snackBar.setActionTextColor(Color.BLUE)
         val snackBarView = snackBar.view
         snackBarView.setBackgroundColor(Color.CYAN)
         val textView = snackBarView.findViewById(com.google.android.material.R.id.snackbar_text) as TextView
         textView.setTextColor(Color.BLUE)
         snackBar.show()
      }
   }
}
```
- Run the codes & see the output.



------


### Notification
As you all know notifcationis a kind of message, alert, or status of an application (probably running in the background) that is visible or available in the Android’s UI elements. This application could be running in the background but not in use by the user. The purpose of a notification is to notify the user about a process that was initiated in the application either by the user or the system.

Notifications could be of various formats and designs depending upon the developer. In General, one must have witnessed these four types of notifications:

1. Status Bar Notification (appears in the same layout as the current time, battery percentage)
2. Notification drawer Notification (appears in the drop-down menu)
3. Heads-Up Notification (appears on the overlay screen, ex: Whatsapp notification, OTP messages)
4. Lock-Screen Notification.


![](https://media.geeksforgeeks.org/wp-content/uploads/20200720160849/Output-660x293.jpg)

Here are some steps to create notification.

- Check  for the dependencies if not added add them.
>`dependencies { 
	implementation 'com.android.support:support-compat:28.0.0' 
} `

- Modify **android_main.xml** file.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
	xmlns:android="http://schemas.android.com/apk/res/android"
	xmlns:tools="http://schemas.android.com/tools"
	android:layout_width="match_parent"
	android:layout_height="match_parent"
	tools:context=".MainActivity">

	<Button
		android:id="@+id/btn"
		android:layout_width="wrap_content"
		android:layout_height="wrap_content"
		android:layout_centerInParent="true"
		android:text="Send Notification" />

</RelativeLayout>

```

- Create a new activity named after notification. For this go to res/layout then right-click and select new then activity, Empty Activity. When someone clicks on the notification, this activity will open up in our app that is the user will be redirected to this page. Modify activity_after_notification.xml file.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
	xmlns:android="http://schemas.android.com/apk/res/android"
	xmlns:tools="http://schemas.android.com/tools"
	android:layout_width="match_parent"
	android:layout_height="match_parent"
	tools:context=".afterNotification">

	<TextView
		android:id="@+id/textView"
		android:layout_width="wrap_content"
		android:layout_height="wrap_content"
		android:layout_centerInParent="true"
		android:text="Welcome To GeeksforGeeks"
		android:textSize="15sp"
		android:textStyle="bold" />

</RelativeLayout>

```

- Modify MainActivity.kt file

```
import androidx.appcompat.app.AppCompatActivity
import android.app.Notification
import android.app.NotificationChannel
import android.app.NotificationManager
import android.app.PendingIntent
import android.content.Context
import android.content.Intent
import android.graphics.BitmapFactory
import android.graphics.Color
import android.os.Build
import android.os.Bundle
import android.widget.Button
import android.widget.RemoteViews

class MainActivity : AppCompatActivity() {

	// declaring variables
	lateinit var notificationManager : NotificationManager
	lateinit var notificationChannel : NotificationChannel
	lateinit var builder : Notification.Builder
	private val channelId = "i.apps.notifications"
	private val description = "Test notification"

	override fun onCreate(savedInstanceState: Bundle?) {
		super.onCreate(savedInstanceState)
		setContentView(R.layout.activity_main)

		// accessing button
		val btn = findViewById<Button>(R.id.btn)

		// it is a class to notify the user of events that happen. 
		// This is how you tell the user that something has happened in the
		background.notificationManager = 
			getSystemService(Context.NOTIFICATION_SERVICE) as NotificationManager

		// onClick listener for the button
		btn.setOnClickListener {

			//pendingIntent is an intent for future use i.e after
			// the notification is clicked, this intent will come into action

			val intent = Intent(this,afterNotification::class.java)

			// FLAG_UPDATE_CURRENT specifies that if a previous 
			// PendingIntent already exists, then the current one 
			// will update it with the
			latest intent
			// 0 is the request code, using it later with the 
			// same method again will get back the same pending 
			// intent for future reference
			// intent passed here is to our afterNotification class
			val pendingIntent = PendingIntent.getActivity(this,
				0,intent,PendingIntent.FLAG_UPDATE_CURRENT)

			// RemoteViews are used to use the content of 
			// some different layout apart from the current activity layout
			val contentView = RemoteViews(packageName,
				R.layout.activity_after_notification)

			// checking if android version is greater than oreo(API 26) or not
			if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
				notificationChannel = NotificationChannel(
					channelId,description,NotificationManager.IMPORTANCE_HIGH)
				notificationChannel.enableLights(true)
				notificationChannel.lightColor = Color.GREEN
				notificationChannel.enableVibration(false)
				notificationManager.createNotificationChannel(notificationChannel)

				builder = Notification.Builder(this,channelId)
					.setContent(contentView)
					.setSmallIcon(R.drawable.ic_launcher_background)
					.setLargeIcon(BitmapFactory.decodeResource(this.resources,
						R.drawable.ic_launcher_background))
					.setContentIntent(pendingIntent)
			}else{

				builder = Notification.Builder(this)
					.setContent(contentView)
					.setSmallIcon(R.drawable.ic_launcher_background)
					.setLargeIcon(BitmapFactory.decodeResource(this.resources,
						R.drawable.ic_launcher_background))
					.setContentIntent(pendingIntent)
			}
			notificationManager.notify(1234,builder.build())
		}
	}
}

```

- Run the application & see the results
