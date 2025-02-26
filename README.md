# calculator
it is a simple program of calculator in android kotlin
package com.example.as_2_calculator

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import android.widget.Toast
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AppCompatActivity
import androidx.core.view.ViewCompat
import androidx.core.view.WindowInsetsCompat

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContentView(R.layout.activity_main)
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main)) { v, insets ->
            val systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars())
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom)
            insets
        }

        val eno1 : EditText=findViewById(R.id.editTextno1)
        val eno2: EditText=findViewById(R.id.editTextno2)
        val buttonadd : Button = findViewById(R.id.buttonadd)
        val buttonsub: Button = findViewById(R.id.buttonsub)
        val buttondiv: Button= findViewById(R.id.buttondiv)
        val buttonmul: Button= findViewById(R.id.buttonmul)
        val tv : TextView = findViewById(R.id.textView)

        buttonadd.setOnClickListener {
            var no1 = eno1.text.toString().toInt()
            var no2 = eno2.text.toString().toInt()
            var ans = no1+no2

            tv.setText(ans.toString())

            Toast.makeText(this,"Addition is : + $ans", Toast.LENGTH_LONG).show()
        }

        buttonsub.setOnClickListener {
            var no1 = eno1.text.toString().toInt()
            var no2 = eno2.text.toString().toInt()
            var ans = no1-no2

            tv.setText(ans.toString())

            Toast.makeText(this, "Substraction is : + $ans", Toast.LENGTH_LONG).show()
        }

        buttondiv.setOnClickListener {
            var no1 = eno1.text.toString().toInt()
            var no2 = eno2.text.toString().toInt()
            var ans = no1/no2

            tv.setText(ans.toString())

            Toast.makeText(this, "Division is : + $ans", Toast.LENGTH_LONG).show()
        }

        buttonmul.setOnClickListener {
            var no1 = eno1.text.toString().toInt()
            var no2 = eno2.text.toString().toInt()
            var ans = no1*no2

            tv.setText(ans.toString())

            Toast.makeText(this, "Multiplication is : + $ans", Toast.LENGTH_LONG).show()
        }
    }
}
