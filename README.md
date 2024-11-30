- 👋 Hi, I’m @istapanoglu
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
istapanoglu/istapanoglu is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
cd /path/to/your/project

git init

https://github.com/username/MySchoolApp.git

MySchoolApp/
    ├── app/
        ├── src/
            ├── main/
                ├── java/
                    ├── com/
                        ├── myschoolapp/
                            ├── MainActivity.java
                            ├── DataModel.java
                ├── res/
                    ├── layout/
                        ├── activity_main.xml
                    ├── values/
                        ├── strings.xml
                        ├── colors.xml
package com.myschoolapp;

import android.os.Bundle;
import android.view.View;
import android.widget.ArrayAdapter;
import android.widget.ListView;

import androidx.appcompat.app.AppCompatActivity;

import java.util.ArrayList;

public class MainActivity extends AppCompatActivity {

    private ListView scheduleListView;
    private ArrayList<String> schedule;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        scheduleListView = findViewById(R.id.scheduleListView);
        
        // Örnek Ders Programı Verisi
        schedule = new ArrayList<>();
        schedule.add("09:00 - 10:00 Matematik");
        schedule.add("10:00 - 11:00 Türkçe");
        schedule.add("11:00 - 12:00 Kimya");
        schedule.add("12:00 - 13:00 Öğle Arası");
        schedule.add("13:00 - 14:00 Biyoloji");
        schedule.add("14:00 - 15:00 Fizik");

        // Listeyi ekrana bas
        ArrayAdapter<String> adapter = new ArrayAdapter<>(this, android.R.layout.simple_list_item_1, schedule);
        scheduleListView.setAdapter(adapter);
    }
}
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView
        android:id="@+id/titleText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Ders Programı"
        android:textSize="20sp"
        android:layout_marginBottom="20dp"
        android:textStyle="bold"/>

    <ListView
        android:id="@+id/scheduleListView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>
</LinearLayout>

package com.myschoolapp;

public class DataModel {
    private String courseName;
    private double grade;
    private String date;

    public DataModel(String courseName, double grade, String date) {
        this.courseName = courseName;
        this.grade = grade;
        this.date = date;
    }

    public String getCourseName() {
        return courseName;
    }

    public double getGrade() {
        return grade;
    }

    public String getDate() {
        return date;
    }

    @Override
    public String toString() {
        return courseName + ": " + grade + " (" + date + ")";
    }
package com.myschoolapp;

import android.os.Bundle;
import android.widget.ArrayAdapter;
import android.widget.ListView;

import androidx.appcompat.app.AppCompatActivity;

import java.util.ArrayList;

public class GradesActivity extends AppCompatActivity {

    private ListView gradesListView;
    private ArrayList<DataModel> gradesList;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_grades);

        gradesListView = findViewById(R.id.gradesListView);

        // Örnek Notlar
        gradesList = new ArrayList<>();
        gradesList.add(new DataModel("Matematik", 85.5, "01/11/2024"));
        gradesList.add(new DataModel("Türkçe", 90.0, "01/11/2024"));
        gradesList.add(new DataModel("Kimya", 78.0, "02/11/2024"));

        // Listeyi ekrana bas
        ArrayAdapter<DataModel> adapter = new ArrayAdapter<>(this, android.R.layout.simple_list_item_1, gradesList);
        gradesListView.setAdapter(adapter);
    }
}
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView
        android:id="@+id/titleText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Öğrenci Notları"
        android:textSize="20sp"
        android:layout_marginBottom="20dp"
        android:textStyle="bold"/>

    <ListView
        android:id="@+id/gradesListView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>
</LinearLayout>
