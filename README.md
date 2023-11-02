# Project_Mobile_Fibonacci

# 1. Pertama, Buatlah code pada layout (.xml) yang berisikan sbb:

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="10dp"
    tools:context="com.example.myapplication.Fibonacci">

    <Button
        android:id="@+id/button_toast"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginTop="8dp"
        android:layout_marginEnd="8dp"
        android:background="@color/colorPrimary"
        android:text="@string/button_label_toast"
        android:textColor="@android:color/white"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        android:onClick="showToast" />


    <Button
        android:id="@+id/button_count"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="8dp"
        android:layout_marginEnd="8dp"
        android:layout_marginBottom="8dp"
        android:background="@color/colorPrimary"
        android:onClick="countUp"
        android:text="Count"
        android:textColor="@android:color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent" />
    <TextView
        android:id="@+id/show_count"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:layout_marginStart="8dp"
        android:layout_marginTop="8dp"
        android:layout_marginEnd="8dp"
        android:layout_marginBottom="8dp"
        android:background="#FFFF00"
        android:gravity="center_vertical"
        android:text="0"
        android:textAlignment="center"
        android:textColor="@color/colorPrimary"
        android:textSize="160sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toTopOf="@+id/button_count"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button_toast" />

</androidx.constraintlayout.widget.ConstraintLayout>
```
![image](https://github.com/Aliyahasmarani/mobile_projectUts/assets/115197672/4787c214-1a74-492b-ad0f-fba009b73a4f)


## HASIL DARI CODE LAYOUT DESIGN:

![image](https://github.com/Aliyahasmarani/mobile_projectUts/assets/115197672/0b6f0e84-f270-4216-8391-de2cdca33c8f)

# 2. Selanjutnya, Menyiapkan Activity (java) Untuk Fibonacci:

Berikut saya siapkan code yang telah saya buat:

```java
package com.example.myapplication;

import android.os.Bundle;
import android.view.View;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class Fibonacci extends AppCompatActivity {
    int first = 0;
    int second = 1;
    TextView Fibonacci;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_fibonnaci);

        Fibonacci = findViewById(R.id.show_count);
        updateFibonacciText();
    }

    public void showToast(View view) {
        Toast.makeText(this, "Fibonacci", Toast.LENGTH_SHORT).show();
    }

    public void countUp(View view) {
        int next = first + second;
        first = second;
        second = next;
        updateFibonacciText();
    }

    private void updateFibonacciText() {
        Fibonacci.setText(Integer.toString(first));
    }
}
```
![image](https://github.com/Aliyahasmarani/mobile_projectUts/assets/115197672/371b88c2-4bae-422f-9d1e-69421244ab95)

## HASIL DARI CODE ACTIVITY DI ATAS:

![image](https://github.com/Aliyahasmarani/mobile_projectUts/assets/115197672/3bd6ae14-cb66-4d10-8940-c8f6c1e18c1c)

![image](https://github.com/Aliyahasmarani/mobile_projectUts/assets/115197672/41ba9df5-8d1c-447f-bc31-091ec2681da0)

![image](https://github.com/Aliyahasmarani/mobile_projectUts/assets/115197672/575708f8-8fd3-401d-a2c3-246ec764224c)

![image](https://github.com/Aliyahasmarani/mobile_projectUts/assets/115197672/18f5f898-51de-4d7d-9009-a5f5ef71289d)

![image](https://github.com/Aliyahasmarani/mobile_projectUts/assets/115197672/f14fcd26-6b94-4e2d-8b46-6ef1e76f86e3)


