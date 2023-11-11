# Project_Mobile_Fibonacci


![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/4944c6e8-7d43-463c-867a-4405eae296b5)

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
![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/292cabaa-02a1-4b10-a526-2cf5aa931551)

## PENJELASAN :

### 1. Package dan Import:
```
package com.example.myapplication;
import android.os.Bundle;
import android.view.View;
import android.widget.TextView;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;
```
Ini adalah bagian awal dari kode dan mendefinisikan paket (package) serta import library yang dibutuhkan.

### 2. Deklarasi Variabel:
```
public class Fibonacci extends AppCompatActivity {
    int first = 0;
    int second = 1;
    TextView Fibonacci;
```
Di sini, kita mendeklarasikan kelas Fibonacci yang merupakan turunan dari AppCompatActivity. Kedua variabel first dan second adalah dua angka pertama dalam deret Fibonacci, dan TextView Fibonacci adalah elemen tampilan untuk menampilkan angka-angka tersebut di layar.

### 3. Metode onCreate:
```
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_fibonnaci);

    Fibonacci = findViewById(R.id.show_count);
    updateFibonacciText();
```
Metode ini dipanggil ketika aktivitas (activity) dibuat. Di sini, kita mengatur tata letak (layout) aktivitas dari file XML (activity_fibonnaci.xml) dan menginisialisasi elemen tampilan Fibonacci. Kemudian, kita memanggil updateFibonacciText untuk menampilkan nilai awal.

### 4. Metode showToast:
```
public void showToast(View view) {
    Toast.makeText(this, "Fibonacci", Toast.LENGTH_SHORT).show();
```
Metode ini menampilkan pesan singkat (toast) dengan teks "Fibonacci" ketika metode ini dipanggil.

### 5. Metode countUp:
```
public void countUp(View view) {
    int next = first + second;
    first = second;
    second = next;
    updateFibonacciText();
```
Metode ini dijalankan ketika tombol di layar ditekan. Ini menghitung nilai berikutnya dalam deret Fibonacci, mengupdate nilai first dan second, dan kemudian memanggil updateFibonacciText untuk menampilkan nilai terbaru di layar.

### 6. Metode updateFibonacciText:
```
private void updateFibonacciText() {
    Fibonacci.setText(Integer.toString(first));
```
Metode ini mengatur teks pada elemen tampilan Fibonacci dengan nilai terbaru dari first dalam bentuk teks.

## HASIL DARI CODE ACTIVITY DI ATAS:

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/48e7610a-54d2-42e8-ac8b-40b52a0fe64b)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/203f8f90-ad9c-4adc-9462-96116ee74f7e)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/203f8f90-ad9c-4adc-9462-96116ee74f7e)

![Screenshot 2023-11-02 172654](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/e8b92a38-e325-492e-8f07-9f2791aa129e)

![Screenshot 2023-11-02 172714](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/1e2ce5f8-1864-4540-8c0f-70040a6a8d56)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/e56b84ae-34a1-4654-9634-e68ee1f24a76)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/d9367fa8-987b-4aaa-a43b-abb71c1aa152)

# Tugas 2

# 1. Tugasnya masih sama, hanya sajah ada sedikit perubahan yaitu sebagai berikut:

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
        android:text="0"
        android:textSize="160sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toTopOf="@id/button_count"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@id/button_toast"
        tools:ignore="RtlCompat" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/df5f8dc9-911e-4728-b030-14079e7d8b7f)

## Berikut perubahannya: Buat code pada (Java)

```
package com.example.myapplication;

import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class Fibonacci extends AppCompatActivity {
    private TextView showCount;
    private int count = 0;
    private long fibNMinus1 = 0;
    private long fibNMinus2 = 1;
    private EditText edit_max_fibonacci;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_fibonnaci);

        showCount = findViewById(R.id.show_count);
        edit_max_fibonacci = findViewById(R.id.edit_max_fibonacci);

        updateCountDisplay();

        fibNMinus1 = 0;
        fibNMinus2 = 1;
    }

    private void updateCountDisplay() {
        showCount.setText(String.valueOf(fibNMinus1));

        if (count % 4 == 0) {
            showCount.setTextColor(getResources().getColor(R.color.hijau));
        } else if (count % 4 == 1) {
            showCount.setTextColor(getResources().getColor(R.color.black));
        } else if (count % 4 == 2) {
            showCount.setTextColor(getResources().getColor(R.color.Navy));
        } else if (count % 4 == 3) {
            showCount.setTextColor(getResources().getColor(R.color.pink));
        } else {
            showCount.setTextColor(getResources().getColor(R.color.hijau));
        }
    }

    public void showToast(View view){
        Toast.makeText(this, "Bilangan Fibonacci",
                Toast.LENGTH_SHORT).show();
    }

    public void countUp(View view) {
        int maxFibonacci = Integer.parseInt(edit_max_fibonacci.getText().toString());

        if (count >= maxFibonacci) {
            Toast.makeText(this, "Maksimum Fibonacci tercapai", Toast.LENGTH_SHORT).show();
            return;
        }

        long fibCurrent;
        if (count == 0 || count == 1) {
            fibCurrent = 1;
        } else {
            fibCurrent = fibNMinus1 + fibNMinus2;
        }

        fibNMinus2 = fibNMinus1;
        fibNMinus1 = fibCurrent;
        updateCountDisplay();

        count++;
    }

    public void back1(View view) {
        count = 0;
        fibNMinus1 = 0;
        fibNMinus2 = 1;
        updateCountDisplay();
    }
}
```
![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/5463b2f8-3890-483b-b5fb-4f19209c0138)

## PENJELASAN

### 1. Variabel:
```
private TextView showCount;
private int count = 0;
private long fibNMinus1 = 0;
private long fibNMinus2 = 1;
private EditText edit_max_fibonacci;
```

-> showCount: Menunjukkan angka deret Fibonacci saat ini di layar.<br>
-> count: Menghitung berapa banyak langkah telah diambil dalam deret Fibonacci.<br>
-> fibNMinus1 dan fibNMinus2: Menyimpan dua angka sebelumnya dalam deret Fibonacci.<br>
-> edit_max_fibonacci: Digunakan untuk mengatur nilai maksimum yang ingin ditampilkan.<br>

### 2. Metode onCreate:
```
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_fibonnaci);

    showCount = findViewById(R.id.show_count);
    edit_max_fibonacci = findViewById(R.id.edit_max_fibonacci);

    updateCountDisplay();

    fibNMinus1 = 0;
    fibNMinus2 = 1;
}
```
-> Dipanggil saat aplikasi dimulai.<br>
-> Menyiapkan tampilan dan nilai awal deret Fibonacci.<br>
-> Memanggil metode updateCountDisplay untuk menampilkan nilai awal.<br>

### 3. Metode updateCountDisplay:
```
private void updateCountDisplay() {
    showCount.setText(String.valueOf(fibNMinus1));

    // Mengubah warna teks berdasarkan sisa bagi dari 'count'.
    // Memberikan efek warna yang berbeda setiap 4 langkah dalam deret Fibonacci.
}
```
-> Memperbarui tampilan dengan nilai terbaru dari deret Fibonacci.<br>
-> Mengganti warna teks berdasarkan pola tertentu.<br>

### 4. Metode showToast:
```
public void showToast(View view){
    Toast.makeText(this, "Bilangan Fibonacci", Toast.LENGTH_SHORT).show();
}
```
-> Menampilkan pesan singkat (Toast) ketika tombol tertentu ditekan.

### 5. Metode countUp:
```
public void countUp(View view) {
    // Mengambil nilai maksimum yang diinginkan.
    // Memeriksa apakah sudah mencapai nilai maksimum.
    // Menghitung dan menampilkan nilai berikutnya dalam deret Fibonacci.
}
```
-> Dipanggil ketika tombol "Hitung" ditekan.<br>
-> Mengambil nilai maksimum yang diinginkan.<br>
-> Memeriksa apakah sudah mencapai nilai maksimum.<br>
-> Menghitung dan menampilkan nilai berikutnya dalam deret Fibonacci.<br>

### 6. Metode back1:
```
public void back1(View view) {
    // Mereset variabel-variabel untuk mengembalikan deret Fibonacci ke awal.
    // Memanggil metode updateCountDisplay untuk menampilkan nilai awal.
}
```
-> Dipanggil ketika tombol "Kembali" ditekan.<br>
-> Mereset variabel-variabel untuk mengembalikan deret Fibonacci ke awal.<br>
-> Memanggil metode updateCountDisplay untuk menampilkan nilai awal deret Fibonacci.<br>

## HASIL DARI CODE ACTIVITY DI ATAS:

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/0573436f-d8a5-4732-9d87-bd90850283b7)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/f86899e5-cad3-4703-b7ef-0a819dc3a072)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/5de396a5-f1a9-4393-9bdf-400cb138da2a)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/a3eacd17-46c9-4b25-b3c5-9e9ce5c50959)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/22dbeeff-e00d-4574-b858-6e0952a6d257)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/a782c400-881d-462b-99fd-e4023cde1774)

![image](https://github.com/Aliyahasmarani/Project_Mobile_Fibonacci/assets/115197672/7b95a7c8-91ef-42d8-bbe8-23c14d7f593f)

Ketika sudah mencapai permintaan maximumnya, akan muncul tulisan diatas. 



