#_**fibonacci-by-android-studio**_

  Pemrograman Mobile 1 | Teknik Informatika | Universitas Pelita Bangsa
  =====================================================================
   <br> Nama    : Sofyan Arif Widiatko </br>
    NIM     : 312210093 
    Kelas   : TI22B1

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
