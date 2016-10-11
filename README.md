# **Android Component**

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
