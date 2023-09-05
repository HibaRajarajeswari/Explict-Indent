# Workshop - 2:
# Create a simple application for division of two number using explicit intent in android studio.
## Aim:
 To create a simple application for division of two number using explicit intent in android studio.
## EQUIPMENTS REQUIRED:
Latest Version Android Studio.
## Program:
```
Developed By: Hiba Rajarajeswari
Reg.No:212221040056
```

## activity_main.xml
```
package com.example.divide;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.widget.TextView;



public class resultActivity extends AppCompatActivity {
    private TextView resultTextView;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_result);
        resultTextView = findViewById(R.id.button);
        Intent intent = getIntent();
        double result = intent.getDoubleExtra("result", 0);
        resultTextView.setText("Result: " + result);
    }}

```
## MainActivity.java 
```
package com.example.divide;

import androidx.appcompat.app.AppCompatActivity;

import android.annotation.SuppressLint;
import android.os.Bundle;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
public class MainActivity extends AppCompatActivity {
    private EditText firstNumberEditText, secondNumberEditText;
    private Button calculateButton;
    private TextView resultTextView;
    @SuppressLint("MissingInflatedId")
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        firstNumberEditText = findViewById(R.id.et_first_number);
        secondNumberEditText = findViewById(R.id.et_second_number);
        calculateButton = findViewById(R.id.btn_calculate);
        resultTextView = findViewById(R.id.button);
        calculateButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String firstNumberString =
                        firstNumberEditText.getText().toString();
                String secondNumberString =
                        secondNumberEditText.getText().toString();
                double firstNumber = Double.parseDouble(firstNumberString);
                double secondNumber =
                        Double.parseDouble(secondNumberString);
                double result = firstNumber / secondNumber;
                Intent intent = new Intent(MainActivity.this, resultActivity.class);
                intent.putExtra("result", result);
                startActivity(intent);
            }
        });
    }
}
```
## activity_result.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".resultActivity">
    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="result: "
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.456"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
## resultActivity.java
```
package com.example.divide;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.widget.TextView;



public class resultActivity extends AppCompatActivity {
    private TextView resultTextView;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_result);
        resultTextView = findViewById(R.id.button);
        Intent intent = getIntent();
        double result = intent.getDoubleExtra("result", 0);
        resultTextView.setText("Result: " + result);
    }}


```
## Output:
![image](https://github.com/HibaRajarajeswari/Explict-Indent/assets/129970809/c3a12642-cbdc-4ba0-976c-876ec7c9989a)
![image](https://github.com/HibaRajarajeswari/Explict-Indent/assets/129970809/12d5fcaf-9d5f-4ed2-aeb0-811b8b2a3885)



## Result:
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.

