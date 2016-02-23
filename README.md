# SwipeSelector
A nicer-looking and more intuitive alternative for radio buttons and dropdowns for Android.

# Demo
<img src="https://raw.githubusercontent.com/roughike/SwipeSelector/master/swipeselector_demo.gif" width="278" height="492" />


## What and why?

Bored of dull looking radio buttons and dropdowns? Me too. I started looking for a more sophisticated way of offering user a choice, and came up with [this beautiful dribble](https://dribbble.com/shots/2343630-Create-Shipment).

Unfortunately, there were no ready-made solutions to achieve this, so I spent a good day working on this very thing I call SwipeSelector.

## How do I use it?

The usage is really simple.

**First, add the dependency using Gradle:**

```
compile 'com.roughike:swipe-selector:1.0.1'
```

**Or maven:**
```
<dependency>
  <groupId>com.roughike</groupId>
  <artifactId>swipe-selector</artifactId>
  <version>1.0.1</version>
  <type>pom</type>
</dependency>
```

**Then add SwipeSelector to your layout file:**

```xml
<com.roughike.swipeselector.SwipeSelector
    android:id="@+id/swipeSelector"
    android:layout_width="match_parent"
    android:layout_height="wrap_content" />
```

**Then get a hold of it and do something with it:**

```java
SwipeSelector swipeSelector = (SwipeSelector) findViewById(R.id.swipeSelector);
swipeSelector.setItems(
  // The first argument is the value for that item, and should in most cases be unique.
  // You can use the value later on to check what the selected item was.
  // The value can be any Object, here we're using ints.
  new SwipeItem(0, "Slide one", "Description for slide one."),
  new SwipeItem(1, "Slide two", "Description for slide two."),
  new SwipeItem(2, "Slide three", "Description for slide three.")
);
```

**Whenever you need to know what is the currently showing SwipeItem:**
```java
SwipeItem selectedItem = swipeSelector.getSelectedItem();

// The value is the first argument provided when creating the SwipeItem.
int value = selectedItem.value;

// for example
if (value == 0) {
  // The user selected slide number one.
}
```

## Customization

```xml
<com.roughike.swipeselector.SwipeSelector
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/conditionSelector"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    app:swipe_indicatorSize="10dp"
    app:swipe_indicatorMargin="12dp"
    app:swipe_indicatorInActiveColor="#DDDDDD"
    app:swipe_indicatorActiveColor="#FF00FF" />
```

**Attribute explanations**

* **swipe_indicatorSize** the size for the circle indicators.
* **swipe_indicatorMargin** how far the indicators are from each other.
* **swipe_indicatorInActiveColor** the color for normal unselected indicators.
* **swipe_indicatorActiveColor** the color for selected indicator.

## Contributions

Feel free to create issues / pull requests.

## Apps using SwipeSelector

Contact me at iiro.krankka@gmail.com to get a shoutout!

## License

```
SwipeSelector library for Android
Copyright (c) 2016 Iiro Krankka (http://github.com/roughike).

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
