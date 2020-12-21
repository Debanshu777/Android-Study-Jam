# ListView & Scroll View

### ListView
Android ListView is a ViewGroup which is used to display the list of items in multiple rows and contains an adapter which automatically inserts the items into the list.

The main purpose of the adapter is to fetch data from an array or database and insert each item that placed into the list for the desired result. So, it is main source to pull data from strings.xml file which contains all the required strings in Kotlin or xml files.

#### Android Adapter
Adapter holds the data fetched from an array and iterates through each item in data set and generates the respective views for each item of the list. So, we can say it act as an intermediate between the data sources and adapter views such as ListView, Gridview. Different Types of Adapter :-

1. ArrayAdapter: It always accepts an Array or List as input. We can store the list items in the strings.xml file also.
2. CursorAdapter: It always accepts an instance of cursor as an input means.
3. SimpleAdapter: It mainly accepts a static data defined in the resources like array or database.
4. BaseAdapter: It is a generic implementation for all three adapter types and it can be used in the views according to our requirements.

Below are the demonstration to create ListView.
- In **activity_main.xml** file, we declare the LisitView within LinearLayout and set its attributes. Later, we will access the ListView in Kotlin file using the id.

```xml
<?xml version="1.0" encoding="utf-8"?> 
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
	xmlns:tools="http://schemas.android.com/tools"
	android:layout_width="match_parent"
	android:layout_height="match_parent"
	android:orientation="vertical"> 
	<ListView 
		android:id="@+id/userlist"
		android:layout_width="match_parent"
		android:layout_height="wrap_content" > 
	</ListView> 
</LinearLayout> 

```

- When we have created layout, we need to load the XML layout resource from our activity onCreate() callback method and access the UI element form the XML using findViewById.

**MainActivity.kt**
```kotlin
import android.widget.ArrayAdapter 
import android.widget.ListView 
class MainActivity : AppCompatActivity() { 

	override fun onCreate(savedInstanceState: Bundle?) { 
		super.onCreate(savedInstanceState) 
		setContentView(R.layout.activity_main) 

		// use arrayadapter and define an array 
		val arrayAdapter: ArrayAdapter<*> 
		val users = arrayOf( 
			"Virat Kohli", "Rohit Sharma", "Steve Smith", 
			"Kane Williamson", "Ross Taylor"
		) 
		
		// access the listView from xml file 
		var mListView = findViewById<ListView>(R.id.userlist) 
		arrayAdapter = ArrayAdapter(this, 
			android.R.layout.simple_list_item_1, users) 
		mListView.adapter = arrayAdapter 
	} 
} 

```

- Run the files to & see the output.


---------

### ScrollView

In Android ScrollView incorporates multiple views within itself and allows them to be scrolled. To create it follow these steps:

- Modify activity_main.xml file

```xml
<?xml version="1.0" encoding="utf-8"?> 
<LinearLayout
		xmlns:android="http://schemas.android.com/apk/res/android"
		xmlns:tools="http://schemas.android.com/tools"
		xmlns:app="http://schemas.android.com/apk/res-auto"
		android:layout_width="match_parent"
		android:layout_height="match_parent"
		android:id="@+id/layout"
		tools:context=".MainActivity"> 



</LinearLayout> 

```

- We will be needing some images to be used in application. You can use the images that you like but the images need to be copied from our local computer path to app/res/drawable folder.

- Modify MainActivity.kt file

```kotlin
package com.geeksforgeeks.myfirstkotlinapp 

import androidx.appcompat.app.AppCompatActivity 
import android.os.Bundle 
import android.view.Gravity 
import android.view.ViewGroup 
import android.widget.ImageView 
import android.widget.LinearLayout 
import android.widget.ScrollView 

class MainActivity : AppCompatActivity() { 

	override fun onCreate(savedInstanceState: Bundle?) { 
		super.onCreate(savedInstanceState) 
		setContentView(R.layout.activity_main) 

		val scrollView = ScrollView(this) 
		val layoutParams = LinearLayout.LayoutParams( 
		ViewGroup.LayoutParams.MATCH_PARENT, 
		ViewGroup.LayoutParams.MATCH_PARENT) 
		scrollView.layoutParams = layoutParams 

		val linearLayout = LinearLayout(this) 
		val linearParams = LinearLayout.LayoutParams( 
		ViewGroup.LayoutParams.MATCH_PARENT, 
		ViewGroup.LayoutParams.WRAP_CONTENT) 
		linearLayout.orientation = LinearLayout.VERTICAL 
		linearLayout.layoutParams = linearParams 

		scrollView.addView(linearLayout) 

		val imageView1 = ImageView(this) 
		val params1 = 
			LinearLayout.LayoutParams(ViewGroup.LayoutParams.MATCH_PARENT, 
			ViewGroup.LayoutParams.WRAP_CONTENT) 
		//setting margin 
		params1.setMargins(0, 30, 0, 30) 
		//aligning the layout to center of the screen 
		params1.gravity = Gravity.CENTER 
		imageView1.setLayoutParams(params1) 
		//setting our own downloaded/custom image to the imageView 
		imageView1.setImageResource(R.drawable.image1) 
		linearLayout.addView(imageView1) 

		val imageView2 = ImageView(this) 
		val params2 = 
			LinearLayout.LayoutParams(ViewGroup.LayoutParams.MATCH_PARENT, 
			ViewGroup.LayoutParams.WRAP_CONTENT) 
		params2.setMargins(0, 0, 0, 30) 
		params2.gravity = Gravity.CENTER 
		imageView2.setLayoutParams(params2) 
		imageView2.setImageResource(R.drawable.image2) 
		linearLayout.addView(imageView2) 

		val imageView3 = ImageView(this) 
		val params3 = 
			LinearLayout.LayoutParams(ViewGroup.LayoutParams.MATCH_PARENT, 
			ViewGroup.LayoutParams.WRAP_CONTENT) 
		params3.setMargins(0, 0, 0, 30) 
		params3.gravity = Gravity.CENTER 
		imageView3.setLayoutParams(params3) 
		imageView3.setImageResource(R.drawable.image3) 
		linearLayout.addView(imageView3) 

		val imageView4 = ImageView(this) 
		val params4 = 
			LinearLayout.LayoutParams(ViewGroup.LayoutParams.MATCH_PARENT, 
			ViewGroup.LayoutParams.WRAP_CONTENT) 
		params4.setMargins(0, 0, 0, 30) 
		params4.gravity = Gravity.CENTER 
		imageView4.setLayoutParams(params4) 
		imageView4.setImageResource(R.drawable.image4) 
		linearLayout.addView(imageView4) 

		val linearLayout1 = findViewById<LinearLayout>(R.id.layout) 
		linearLayout1?.addView(scrollView) 
	} 
} 

```

- Run the code & see the output.

