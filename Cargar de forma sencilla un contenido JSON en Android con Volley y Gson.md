# Cargar de forma sencilla un contenido JSON en Android con Volley y Gson
## Android, Java 
### URL: https://www.jesusninoc.com/2018/02/27/cargar-de-forma-sencilla-un-contenido-json-en-android-con-volley-y-gson/
```Java
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.jesusninoc.json.MainActivity">

    <TextView
        android:id="@+id/TextResult"
        android:layout_width="315dp"
        android:layout_height="0dp"
        android:text="Resultado de JSON"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintHorizontal_bias="0.507"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="1.0" />

</android.support.constraint.ConstraintLayout>

```
```Java
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.jesusninoc.json">

    <uses-permission android:name="android.permission.INTERNET"/>

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity
            android:name=".MainActivity"
            android:label="@string/app_name"
            android:theme="@style/AppTheme.NoActionBar">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>

```
```Java
package com.jesusninoc.json;

import android.app.ProgressDialog;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.widget.ListView;
import android.widget.TextView;
import android.widget.Toast;

import com.android.volley.Request;
import com.android.volley.Response;
import com.android.volley.VolleyError;
import com.android.volley.toolbox.StringRequest;
import com.android.volley.toolbox.Volley;

import com.google.gson.Gson;

import java.util.List;
import java.util.Map;

public class MainActivity extends AppCompatActivity {

    List<Object> list;
    Gson gson;
    ProgressDialog progressDialog;
    ListView postList;
    Map<String,Object> mapPost;
    Map<String,Object> mapTitle;
    int postID;
    String postTitle[];

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        RealizarPost();
    }

    public void RealizarPost() {

        StringRequest request = new StringRequest(Request.Method.GET, "https://www.jesusninoc.com/wp-json/wp/v2/posts/", new Response.Listener<String>() {
            @Override
            public void onResponse(String s) {
                gson = new Gson();
                list = (List) gson.fromJson(s, List.class);
                postTitle = new String[list.size()];

                for(int i=0;i<list.size();++i){
                    mapPost = (Map<String,Object>)list.get(i);
                    mapTitle = (Map<String, Object>) mapPost.get("title");
                    postTitle[i] = (String) mapTitle.get("rendered");
                    ((TextView)findViewById(R.id.TextResult)).append(postTitle[i]+"\n");
                }
            }
        }, new Response.ErrorListener() {
            @Override
            public void onErrorResponse(VolleyError volleyError) {
                Toast.makeText(MainActivity.this, "Error al procesar el JSON", Toast.LENGTH_LONG).show();
            }
        });
        
        Volley.newRequestQueue(this).add(request);
    }
}

```
```Java
apply plugin: 'com.android.application'

android {
    compileSdkVersion 26
    defaultConfig {
        applicationId "com.jesusninoc.json"
        minSdkVersion 15
        targetSdkVersion 26
        versionCode 1
        versionName "1.0"
        testInstrumentationRunner "android.support.test.runner.AndroidJUnitRunner"
    }
    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
        }
    }
}

dependencies {
    implementation fileTree(dir: 'libs', include: ['*.jar'])
    implementation 'com.android.support:appcompat-v7:26.1.0'
    implementation 'com.android.support.constraint:constraint-layout:1.0.2'
    testImplementation 'junit:junit:4.12'
    androidTestImplementation 'com.android.support.test:runner:1.0.1'
    androidTestImplementation 'com.android.support.test.espresso:espresso-core:3.0.1'
    compile 'com.android.volley:volley:1.0.0'
    compile 'com.google.code.gson:gson:2.2.+'
}

```
