#_**fibonacci-by-android-studio**_

  Pemrograman Mobile 1 | Teknik Informatika | Universitas Pelita Bangsa
  =====================================================================
    Nama    : Sofyan Arif Widiatko
    NIM     : 312210093 
    Kelas   : TI22B1
  
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
5. Kemudian kita buat dimens.xml dimana kita akan merubah ukuran text tampilan pada activity_main.xml
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
``` string
6. Setelah semua langkah diatas, sekarang kita buat styles.xml untuk mempercantik tampilan Fibonacci
```
``` xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <style name="GreenText" parent="TextAppearance.AppCompat">
        <item name="android:textColor">#00FF00</item>
    </style>
    <!--<style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
        ...
        <item name="android:windowBackground">@color/activityBackground</item>
    </style>-->
    <!-- Base set of styles that apply to all versions. -->
    <style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
        <item name="colorPrimary">@color/colorPrimary</item>
        <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
        <item name="colorAccent">@color/colorAccent</item>
    </style>

    <!-- Declare the theme name that's actually applied in the manifest file. -->


</resources>
```
``` string
7. Kita kembali ke menu MainActivity.java
Disini Kita masukkan fungsi-fungsi dari tombol count & toast dan fungsi dari fibonacci itu sendiri.
Berikut adalah isi dari text MainActivity.java
```
``` java
package com.example.hellotoast;

import android.content.Context;
import android.os.Bundle;
import android.view.View;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private Context context;
    private int mCount = 0;
    private TextView mShowCount;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        mShowCount = (TextView) findViewById(R.id.show_count);
    }


    private int fibonacci( int n){

        if (n <= 1) {
            return n;
        } else {
            int fib1 = 0;
            int fib2 = 1;
            int result = 0;

            for (int i = 2; i <= n; i++) {
                result = fib1 + fib2;
                fib1 = fib2;
                fib2 = result;
            }

            return result;
        }
    }
    public void showToast(View view) {
        String myString = "Hallo toast";
        Toast toast = Toast.makeText(getApplicationContext(), myString, Toast.LENGTH_LONG);
        toast.show();
    }

    public void countUp(View view) {
        // Hitung nilai Fibonacci untuk mCount saat ini
        int fibonacciValue = fibonacci(mCount);

        // Tambahkan nilai Fibonacci ke dalam TextView
        if (mShowCount != null) {
            mShowCount.setText(Integer.toString(fibonacciValue));
            // Mengubah warna teks TextView
            if (fibonacciValue % 2 == 0) {
                mShowCount.setTextColor(getResources().getColor(R.color.evenColor));
            } else {
                mShowCount.setTextColor(getResources().getColor(R.color.oddColor));
            }
        }
        mCount++;
    }
}

```
``` string
8. Setelah semua kita masukkan dari layout, desain, serta fungsi.
Sekarang kita kefolder manifests, dimana di folder tersebut kita harus merubah nama apk serta arah file java mana yang akan kita gunakan apabila banyak file java.
Berikut adalah text dari AndroidManifest.xml
```
``` xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/Fibonacci"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.Hellotoast"
        tools:targetApi="31">
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```

[Ini adalah video Tutorial singkat dari APK Fibonacci by Android Studio](https://youtu.be/rKatRT7htoI)


