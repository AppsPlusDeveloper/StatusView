</br><b>StatusView</b> Es un sistema que te permitira crear un sistema de visor de estados circular.
    </br> </br>
    
<img src="./Preview/preview1.gif" width=300 title="Screen">
    
## Importación
 
Agrega el archivo "StatusView.java" a tú proyecto, también agrega "StatusView_attrs.xml" a la carpeta "resources/values".

## Inicio

Crea tú Layout, StatusView solo te permite crear las lineas al rededor de una view, por lo que el diseño interior depende de tí. Aquí un ejemplo con una CircleImageView:

```xml
<RelativeLayout
 android:id="@+id/relativelayout1"
 android:layout_width="300dp"
 android:layout_height="300dp"
 android:padding="8dp">
	
  <de.hdodenhof.circleimageview.CircleImageView
   android:id="@+id/circleimageview1"
   android:layout_width="match_parent"
   android:layout_height="match_parent"
   android:layout_margin="6dp"
   android:src="@drawable/login_2_20190520045520_more_block_20190531205430"
   app:civ_border_width="0dp"
   app:civ_border_color="#008DCD"
   app:civ_circle_background_color="#FFFFFF"
   app:civ_border_overlay="true" />
				
    <your.package.StatusView
     android:id="@+id/circularStatusView"
     android:layout_width="match_parent"
     android:layout_height="match_parent"
     android:orientation="vertical"
     app:portion_spacing="4dp" />
</RelativeLayout>
```

Agrega la lista de estados a StatusView:

```java
//currentStatus = ListString
circularStatusView.setPortionsCount(currentStatus.size());
circularStatusView.setPortionsColor(getResources().getColor(R.color.colorAccent));
```

Asigna un color independiente a cada posisción:

```java
circularStatusView.setPortionColorForIndex((int) 1, 0xFF9E9E9E);
```
