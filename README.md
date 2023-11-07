#_**fibonacci-by-android-studio**_

  <h1> Pemrograman Mobile 1 | Teknik Informatika | Universitas Pelita Bangsa </h1>h1>
  =====================================================================
   <br> Nama    : Sofyan Arif Widiatko </br>
   <br> NIM     : 312210093 </br>
   <br> Kelas   : TI22B1 </br>
  
  ``` string
  1. Buat Project Baru dengan nama hellotoast
  2. Kita buat Layout di activity_main.xml
  Berikut isi dari text activity_main.xml
  ```
  activity_main.xml
  ``` xml
  <?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context="com.androidstudiobos.twoactivities.MainActivity">

    <Button
        android:id="@+id/button_toast"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="@color/colorPrimary"
        android:text="@string/btn_label_toast"
        android:onClick="showToast"
        android:textColor="@android:color/white"
        tools:ignore="OnClick"
        android:layout_marginLeft="6dp"
        android:layout_marginTop="6dp"
        android:layout_marginRight="6dp"/>

    <TextView
        android:id="@+id/show_count"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_weight="2"
        android:gravity="center"
        android:text="@string/count_initial_value"
        android:textColor="@color/colorPrimary"
        android:textSize="@dimen/count_text_size"
        android:background="@color/myBackgroundColor"
        android:textStyle="bold"
        android:layout_marginLeft="6dp"
        android:layout_marginTop="6dp"
        android:layout_marginRight="6dp"/>

    <Button
        android:id="@+id/button_count"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:onClick="countUp"
        android:background="@color/colorPrimary"
        android:layout_marginBottom="6dp"
        android:layout_marginLeft="6dp"
        android:layout_marginTop="6dp"
        android:layout_marginRight="6dp"
        android:text="@string/btn_label_count"
        android:textColor="@android:color/white"
        tools:ignore="OnClick" />
</LinearLayout>

```
``` string
3. Kemudian kita buat text tampilan yang ada di activity_main.xml
Berikut adalaha isi dari text yang ada di layout
```
string.xml
``` xml
<resources>
    <string name="app_name">Hello Toast</string>
    <string name="btn_label_toast">TOAST</string>
    <string name="count_initial_value">0</string>
    <string name="btn_label_count">COUNT</string>
    <string name="toast_message">"Hello Toast!".</string>

    <string name="Fibonacci">Fibonacci</string>
    <string name="fibonacci">Fibonacci</string>
</resources>
```
``` string
4. Kemudian kita buat ids.xml
````
``` xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <item name="editTextTextPersonName" type="id" />
    <item name="editText" type="id" />
    <item name="textView" type="id" />
    <item name="recyclerView" type="id" />
    <item name="fibonacciRecyclerView" type="id" />
    <item name="Fibonacci" type="id" />
</resources>
```

``` string
````

``` xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <!-- Default screen margins, per the Android Design guidelines. -->
    <dimen name="activity_horizontal_margin">16dp</dimen>
    <dimen name="activity_vertical_margin">16dp</dimen>
    <dimen name="count_text_size">160dp</dimen>
</resources>
```








