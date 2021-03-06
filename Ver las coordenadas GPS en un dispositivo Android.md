# Ver las coordenadas GPS en un dispositivo Android
## Android, Java 
### URL: https://www.jesusninoc.com/2018/02/28/ver-las-coordenadas-gps-en-un-dispositivo-android/
```Java
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.jesusninoc.gps.MainActivity">

    <TextView
        android:id="@+id/TextGPS"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Sin posición"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</android.support.constraint.ConstraintLayout>

```
```Java
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.jesusninoc.gps">

    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>

```
```Java
package com.jesusninoc.gps;

import android.Manifest;
import android.app.Activity;
import android.content.Context;
import android.content.pm.PackageManager;
import android.location.Location;
import android.location.LocationListener;
import android.location.LocationManager;
import android.support.v4.app.ActivityCompat;
import android.os.Bundle;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends Activity implements LocationListener {

    private LocationManager locationManager;

    @Override
    protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // All Location API methods require the ACCESS_COARSE_LOCATION or ACCESS_FINE_LOCATION permissions

        // Use with getSystemService(Class) to retrieve a LocationManager for controlling location updates.

        locationManager = (LocationManager) getSystemService(Context.LOCATION_SERVICE);

        // RequestLocationUpdates(String provider, long minTime, float minDistance, LocationListener listener)

        // Register for location updates using the named provider, and a pending intent.

        // 3 segundos para volver a pedir la posición

        if (ActivityCompat.checkSelfPermission(this, Manifest.permission.ACCESS_FINE_LOCATION) != PackageManager.PERMISSION_GRANTED && ActivityCompat.checkSelfPermission(this, Manifest.permission.ACCESS_COARSE_LOCATION) != PackageManager.PERMISSION_GRANTED) {
            // TODO: Consider calling
            //    ActivityCompat#requestPermissions
            // here to request the missing permissions, and then overriding
            //   public void onRequestPermissionsResult(int requestCode, String[] permissions,
            //                                          int[] grantResults)
            // to handle the case where the user grants the permission. See the documentation
            // for ActivityCompat#requestPermissions for more details.
            return;
        }
        locationManager.requestLocationUpdates(LocationManager.GPS_PROVIDER, 3000, 10, this);
    }

    @Override
    public void onLocationChanged(Location location) {

        String str = "Latitud: " + location.getLatitude() + " Longitud: " + location.getLongitude();

        // Mostrar la latitud y la longitud en un TextView

        ((TextView)findViewById(R.id.TextGPS)).setText(str);

        // Mostrar la latitud y la longitud con Toast

        Toast.makeText(getBaseContext(), str, Toast.LENGTH_LONG).show();
    }

    @Override
    public void onProviderDisabled(String provider) {

        // GPS desactivado

        Toast.makeText(getBaseContext(), "GPS desactivado", Toast.LENGTH_LONG).show();
    }

    @Override
    public void onProviderEnabled(String provider) {

        // GPS activado

        Toast.makeText(getBaseContext(), "GPS activado", Toast.LENGTH_LONG).show();
    }

    @Override
    public void onStatusChanged(String provider, int status, Bundle extras) {
        // TODO Auto-generated method stub

    }
}

```
