# **Android Component**
Dokumentasi penggunaan komponen untuk pengembangan aplikasi android terutama pada user interface.

## Material Design

1. Floating Action Button
2. CollapsingLayout

Pada Layout XML yang akan diberi efek paralax seperti pada aplikasi whatsapp, tambahkan depedency design support library, 
versi yang digunakan pada saat membuat dokumentasi ini menggunakan versi 24.2.1, tambahkan depedency berikut pada <code>build.gradle</code>, yang berada pada <code>Modul:app</code>


    ``` shell
    compile "com.android.support:design:24.2.1";
    ```
Tambahkan widget <code>android.support.design.widget.CollapsingToolbarLayout</code>, letakan didalam widget AppBarLayout, seperti pada source code berikut :


    ``` xml
    <android.support.design.widget.AppBarLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:fitsSystemWindows="true"
       ">

        <android.support.design.widget.CollapsingToolbarLayout
            android:id="@+id/collapsing_toolbar"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:fitsSystemWindows="true"
            app:contentScrim="?attr/colorPrimary"
            app:expandedTitleMarginEnd="64dp"
            app:expandedTitleMarginStart="48dp"
            app:layout_scrollFlags="scroll|exitUntilCollapsed">

            <ImageView
                android:layout_width="match_parent"
                android:layout_height="200dp"
                android:src="@drawable/cover_movies"
                app:layout_collapseMode="parallax"
                android:scaleType="center" />

            <android.support.v7.widget.Toolbar
                android:id="@+id/toolbar"
                android:layout_width="match_parent"
                android:layout_height="?attr/actionBarSize"
               ></android.support.v7.widget.Toolbar>

        </android.support.design.widget.CollapsingToolbarLayout>

    </android.support.design.widget.AppBarLayout>
    ```
    pada widget CollapsingLayout terdapat properties <code> app:layout_scrollFlags </code> untuk mengaktifkan efek scroll, terdapat beberapa
    efek yang dapat dipakai yaitu <code> enterAlways </code>, <code> enterAlwaysCollapsed </code>,<code> exitUntilCollapsed </code>,<code> snap </code>,
    detailnya dapat dilihat [disini](https://guides.codepath.com/android/Handling-Scrolls-with-CoordinatorLayout#responding-to-scroll-events). Pada
    contoh ini mengunakan value <code>scroll|exitUntilCollapsed</code>.

    Bisa juga ditambahkan widget <code>ImageView</code> untuk gambar, diletakan sebelum widget <code>Toolbar</code>, dan pada widget <code>ImageView</code>,
    tambahkan properties <code>app:layout_collapseMode</code> dengan value <code>paralax</code>.
    
    Contoh penggunaan CollapsingLayout :

    <img width="300" src="https://github.com/ramdanisource/Android-Component/blob/master/screenshot/collapsing_layout.png" alt="Screenshot">
    <img width="300" src="https://github.com/ramdanisource/Android-Component/blob/master/screenshot/collapsing_layout2.png" alt="Screenshot">
    

    

## **Alert**

## **ProgressBar Loading**

1. Instance object ProgressBar

    ``` java
    ProgressBar progressBar;
    ```
2. Casting Object with id in XML, put in method onCreate() or another method
    
    in XML file you can declare like this
    ``` xml
    <ProgressBar
                android:id="@+id/progressBar"
                style="@style/Widget.AppCompat.ProgressBar"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:indeterminate="true"
                android:layout_gravity="center_vertical"/>
    ```
    and you call id component XML in java file with method <code> findViewById()</code>

    ``` java
    progressBar = (ProgressBar) findViewById(R.id.progressBar);
    ```

3. Configure ProgressBar Object
    ``` java
    progressBar.setVisibility(View.VISIBLE);
    ```
