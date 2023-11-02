# Project_Mobile_Fibonacci

# Tugas Pertama 



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
![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/f91209e7-409d-4bfb-9445-0cbc245e3ed9)


## HASIL DARI CODE LAYOUT DESIGN:

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/49fc0d31-6204-4d6d-9ba7-6cb4ac7fdec0)

# 2. Selanjutnya, Menyiapkan Activity (java) Untuk Fibonacci:

## Berikut saya siapkan code yang telah saya buat:

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
![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/06f7e2ec-9c4c-4ed5-8512-6c51d12de608)

## HASIL DARI CODE ACTIVITY DI ATAS:

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/48e7610a-54d2-42e8-ac8b-40b52a0fe64b)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/203f8f90-ad9c-4adc-9462-96116ee74f7e)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/203f8f90-ad9c-4adc-9462-96116ee74f7e)

![Screenshot 2023-11-02 172654](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/e8b92a38-e325-492e-8f07-9f2791aa129e)

![Screenshot 2023-11-02 172714](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/1e2ce5f8-1864-4540-8c0f-70040a6a8d56)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/e56b84ae-34a1-4654-9634-e68ee1f24a76)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/d9367fa8-987b-4aaa-a43b-abb71c1aa152)

# Tugas 2

# 1. Tugasnya masih sama, hanya sajah ada sedikit perubahannya sebagai berikut:

## Berikut perubahannya: Buat code pada layout (.xml)

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.example.myapplication.Fibonacci">

    <EditText
        android:id="@+id/edit_max_fibonacci"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginEnd="8dp"
        android:layout_marginTop="8dp"
        android:hint="Maksimum Fibonacci"
        android:inputType="number"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:ignore="MissingTranslation"/>

    <Button
        android:id="@+id/button_toast"
        android:layout_width="190dp"
        android:layout_height="48dp"
        android:layout_marginStart="8dp"
        android:layout_marginTop="8dp"
        android:background="@color/colorPrimary"
        android:onClick="showToast"
        android:textColor="@android:color/white"
        android:text="@string/button_label_toast"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />


    <Button
        android:id="@+id/button_count"
        android:layout_width="190dp"
        android:layout_height="48dp"
        android:layout_marginStart="8dp"
        android:layout_marginEnd="8dp"
        android:layout_marginBottom="8dp"
        android:background="@color/colorPrimary"
        android:onClick="countUp"
        android:text="@string/button_label_count"
        android:textColor="@android:color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        tools:ignore="UsingOnClickInXml,VisualLintButtonSize" />

    <Button
        android:id="@+id/button_finish"
        android:layout_width="190dp"
        android:layout_height="48dp"
        android:layout_marginStart="8dp"
        android:layout_marginEnd="8dp"
        android:layout_marginBottom="8dp"
        android:background="@color/colorPrimary"
        android:onClick="back1"
        android:text="@string/button_label_finish"
        android:textColor="@android:color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toStartOf="parent"
        tools:ignore="UsingOnClickInXml" />

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
        android:textAlignment="center"
        android:textColor="@color/colorPrimary"
        android:textSize="160sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toTopOf="@id/button_count"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@id/button_toast"
        tools:ignore="RtlCompat" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/a43fac5f-0fdc-483c-b335-13b3c0235df0)

## Hasil dari code diatas:

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/f531c9da-fccc-434b-9168-0480f4a7890e)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/0573436f-d8a5-4732-9d87-bd90850283b7)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/f86899e5-cad3-4703-b7ef-0a819dc3a072)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/5de396a5-f1a9-4393-9bdf-400cb138da2a)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/a3eacd17-46c9-4b25-b3c5-9e9ce5c50959)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/22dbeeff-e00d-4574-b858-6e0952a6d257)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/a782c400-881d-462b-99fd-e4023cde1774)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/7b95a7c8-91ef-42d8-bbe8-23c14d7f593f)



