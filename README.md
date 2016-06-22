# AndSes5Ass1
Main Activity.java
package me.rk.andses5ass1;

import android.app.SearchManager;
import android.content.Intent;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity implements View.OnClickListener{

    private Button enterbutton;
    private EditText mEdit;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        enterbutton=(Button)findViewById(R.id.implcitButton);
        enterbutton.setOnClickListener(this);

        mEdit=(EditText) findViewById(R.id.editSearch);
    }

    @Override
    public void onClick(View v) {
        String q=mEdit.getText().toString();

        if(q.equals(null)||q.equals("")){
            Toast.makeText(this, "Enter text to search !!!", Toast.LENGTH_SHORT).show();
        }else{
            Intent search=new Intent(Intent.ACTION_WEB_SEARCH);
            search.putExtra(SearchManager.QUERY,q);
            startActivity(search);
        }
    }
}

activity_main.xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingBottom="@dimen/activity_vertical_margin"
    android:paddingLeft="@dimen/activity_horizontal_margin"
    android:paddingRight="@dimen/activity_horizontal_margin"
    android:paddingTop="@dimen/activity_vertical_margin"
    tools:context="me.rk.andses5ass1.MainActivity">

    <Button
        android:id="@+id/implcitButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Press Implicit button to search"
        android:layout_centerHorizontal="true"
        android:layout_centerInParent="true"
        android:background="@android:color/holo_orange_dark"/>

    <EditText
        android:id="@+id/editSearch"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:hint="What do you want to goggle"
        android:layout_centerHorizontal="true"/>
</RelativeLayout>

