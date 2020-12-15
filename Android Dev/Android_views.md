# Layouts and resources for UI
## Views

The UI consists of a hierarchy of objects called views — every element of the screen is a **View**. The View class represents the basic building block for all UI components, and the base class for classes that provide interactive UI components such as buttons, checkboxes, and text entry fields.

A View has a location, expressed as a pair of left and top coordinates, and two dimensions, expressed as a width and a height. The unit for location and dimensions is the density-independent pixel (dp).

The Android system provides hundreds of predefined View subclasses. Commonly used View subclasses described over several lessons include:
* <a href="http://developer.android.com/reference/android/widget/TextView.html">TextView</a> for displaying text
* <a href="https://developer.android.com/reference/android/widget/EditText.html">EditText</a> to enable the user to enter and edit text
* <a href="https://developer.android.com/reference/android/widget/Button.html">Button</a> and other clickable elements (such as RadioButton, CheckBox, and Spinner) to provide interactive behavior
* <a href="https://developer.android.com/reference/android/widget/ScrollView.html">ScrollView</a> and <a href="https://developer.android.com/reference/android/support/v7/widget/RecyclerView.html">RecyclerView</a> to display scrollable items
* <a href="https://developer.android.com/reference/android/widget/ImageView.html">ImageView</a> for displaying images
* <a href="https://developer.android.com/reference/android/support/constraint/ConstraintLayout.html">ConstraintLayout</a> and <a href="https://developer.android.com/reference/android/widget/LinearLayout.html">LinearLayout</a> for containing other views and positioning them

You can define a View to appear on the screen and respond to a user tap. A View can also be defined to accept text input, or to be invisible until needed.

You can specify View elements in layout resource files. Layout resources are written in XML and listed within the **layout** folder in the **res** folder in the **Project > Android** pane.
## ViewGroup groups
View elements can be grouped inside a <a href="https://developer.android.com/reference/android/view/ViewGroup.html">ViewGroup</a>, which acts as a container. The relationship is parent-child, in which the parent is a ViewGroup, and the child is a View or another ViewGroup. The following are commonly used ViewGroup groups:
* <a href="https://developer.android.com/reference/android/support/constraint/ConstraintLayout.html">ConstraintLayout</a>: A group that places UI elements (child View elements) using constraint connections to other elements and to the layout edges (parent View)
* <a href="https://developer.android.com/reference/android/widget/ScrollView.html">ScrollView</a>: A group that contains one other child View element and enables scrolling the child View element.
* <a href="https://developer.android.com/reference/android/support/v7/widget/RecyclerView.html">RecyclerView</a>: A group that contains a list of other View elements or ViewGroup groups and enables scrolling them by adding and removing View elements dynamically from the screen.

## Layout ViewGroup groups
The View elements for a screen are organized in a hierarchy. At the root of this hierarchy is a ViewGroup that contains the layout of the entire screen. The ViewGroup can contain child View elements or other ViewGroup groups as shown in the following figure.

![ViewGroup](https://google-developer-training.github.io/android-developer-fundamentals-course-concepts-v2/images/1-2-c-layouts-and-resources-for-the-ui/dg_viewgroup_hierarchy.png)

In the figure above:
* The root ViewGroup.
* The first set of child View elements and ViewGroup groups whose parent is the root.

Some ViewGroup groups are designated as layouts because they organize child View elements in a specific way and are typically used as the root ViewGroup. Some examples of layouts are:
* <a href="http://tools.android.com/tech-docs/layout-editor">ConstraintLayout</a>: A group of child View elements using constraints, edges, and guidelines to control how the elements are positioned relative to other elements in the layout. ConstraintLayout was designed to make it easy to click and drag View elements in the layout editor.
* <a href="https://developer.android.com/reference/android/widget/LinearLayout.html">LinearLayout</a>: A group of child View elements positioned and aligned horizontally or vertically.
* <a href="https://developer.android.com/reference/android/widget/RelativeLayout.html">RelativeLayout</a>: A group of child View elements in which each element is positioned and aligned relative to other elements within the ViewGroup. In other words, the positions of the child View elements can be described in relation to each other or to the parent ViewGroup.
* <a href="https://developer.android.com/reference/android/widget/TableLayout.html">TableLayout</a>: A group of child View elements arranged into rows and columns.
* <a href="https://developer.android.com/reference/android/widget/FrameLayout.html">FrameLayout</a>: A group of child View elements in a stack. FrameLayout is designed to block out an area on the screen to display one View. Child View elements are drawn in a stack, with the most recently added child on top. The size of the FrameLayout is the size of its largest child View element
* <a href="https://developer.android.com/reference/android/widget/GridLayout.html">GridLayout</a>: A group that places its child View elements in a rectangular grid that can be scrolled.

**Tip:** Learn more about different layout types in <a href="https://developer.android.com/guide/topics/ui/layout-objects.html">Common Layout Objects</a>.

A simple example of a LinearLayout with child View elements is shown below as a diagram of the layout file (activity_main.xml), along with a hierarchy diagram and a screenshot of the actual finished layout .

![Layout](https://google-developer-training.github.io/android-developer-fundamentals-course-concepts-v2/images/1-2-c-layouts-and-resources-for-the-ui/dg_layout_diagram_and_hierarchy.png)
<ol>
<li>LinearLayout, the root ViewGroup, contains all the child View elements in a vertical orientation.</li>
<li>Button (button_toast). The first child View element appears at the top in the LinearLayout.</li>
<li>TextView (show_count). The second child View element appears under the first child View element in the LinearLayout.</li>
<li>Button (button_count). The third child View element appears under the second child View element in the LinearLayout.</li>

The layout hierarchy can grow to be complex for an app that shows many View elements on a screen. It's important to understand the hierarchy, as it affects whether View elements are visible and how efficiently they are drawn.

## Using attributes pane

The Attributes pane offers access to all of the XML attributes you can assign to a UI element. You can find the attributes (known as properties) common to all views in the <a href="http://developer.android.com/reference/android/view/View.html">View</a> class documentation.

To show the Attributes pane, click the Attributes tab on the right side of the layout editor. The Attributes pane includes a square sizing panel called the view inspector. The symbols inside the view inspector represent the height and width settings.

![Attribute pane](https://google-developer-training.github.io/android-developer-fundamentals-course-concepts-v2/images/1-2-c-layouts-and-resources-for-the-ui/as_layout_width_height_box_annot.png)

The figure above shows the Attributes pane:
<ol>
<li> <b>Vertical view size control</b> The vertical size control, which appears on the top and bottom of the view inspector, specifies the layout_height property. The angles indicate that this size control is set to wrap_content, which means the UI element expands vertically as needed to fit its contents. The "8" indicates a standard margin set to 8 dp.</li>
<li><b>Horizontal view size control</b> The horizontal size control, which appears on the left and right of the view inspector, specifies the layout_width. The angles indicate that this size control is set to wrap_content, which means the UI element expands horizontally as needed to fit its contents, up to a margin of 8 dp.</li>
<li>Attributes pane close button. Click to close the pane.</li>
</ol>

The layout_width and layout_height attributes in the Attributes pane change as you change the inspector's horizontal and vertical size controls. These attributes can take one of three values for a ConstraintLayout:
* The match_constraint setting expands the UI element to fill its parent by width or height up to a margin, if a margin is set. The parent in this case is the ConstraintLayout.
* The wrap_content setting shrinks the UI element to the size of its content. If there is no content, the element becomes invisible.
* To specify a fixed size that's adjusted for the screen size of the device, set a number of dp (density-independent pixels). For example, 16dp means 16 density-independent pixels.

The Attributes pane offers access to all of the attributes you can assign to a View element. You can enter values for each attribute, such as the android:id, background, textColor, and text attributes.

## Editing XML directly

It is sometimes quicker and easier to edit the XML code directly, especially when copying and pasting the code for similar views.

To view and edit the XML code, open the XML layout file. The layout editor appears with the Design tab at the bottom highlighted. Click the Text tab to see the XML code. The following shows the XML code for a LinearLayout with two Button elements with a TextView in the middle:

```XML
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context="com.example.android.hellotoast.MainActivity">

    <Button
        android:id="@+id/button_toast"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginEnd="8dp"
        android:layout_marginStart="8dp"
        android:layout_marginTop="8dp"
        android:background="@color/colorPrimary"
        android:onClick="showToast"
        android:text="@string/button_label_toast"
        android:textColor="@android:color/white" />

    <TextView
        android:id="@+id/show_count"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center_vertical"
        android:layout_marginBottom="8dp"
        android:layout_marginEnd="8dp"
        android:layout_marginStart="8dp"
        android:layout_marginTop="8dp"
        android:background="#FFFF00"
        android:text="@string/count_initial_value"
        android:textAlignment="center"
        android:textColor="@color/colorPrimary"
        android:textSize="160sp"
        android:textStyle="bold"
        android:layout_weight="1"/>

    <Button
        android:id="@+id/button_count"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginBottom="8dp"
        android:layout_marginEnd="8dp"
        android:layout_marginStart="8dp"
        android:background="@color/colorPrimary"
        android:onClick="countUp"
        android:text="@string/button_label_count"
        android:textColor="@android:color/white" />
</LinearLayout>
```
## XML attributes

Views have properties that define where a view appears on the screen, its size, how the view relates to other views, and how it responds to user input. When defining views in XML or in the layout editor's Attributes pane, the properties are referred to as attributes.

For example, in the following XML description of a TextView, the `android:id`, `android:layout_width`, `android:layout_height`, `android:background`, are XML attributes that are translated automatically into the TextView properties:

```XML
<TextView
       android:id="@+id/show_count"
       android:layout_width="match_parent"
       android:layout_height="wrap_content"
       android:background="@color/myBackgroundColor"
       android:textStyle="bold"
       android:text="@string/count_initial_value" />
       
```
Attributes generally take this form:

android:attribute_name="value"

If the value is a resource, such as a color, the @ symbol specifies what kind of resource. For example:

`android:background="@color/myBackgroundColor" `

The background attribute is set to the color resource identified as `myBackgroundColor`, which is declared to be `#FFF043`.

Every View and ViewGroup supports its own variety of XML attributes:
* Some attributes are specific to a View subclass. For example, the TextView subclass supports the textSize attribute. Any elements that extend the TextView subclass inherit these subclass-specific attributes.
* Some attributes are common to all View elements, because they are inherited from the root View class. The `android:id` attribute is one example.