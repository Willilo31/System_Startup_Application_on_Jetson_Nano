# **`Creación de una Aplicación de Inicio en Jetson Nano`**

### Crear el archivo .desktop

1. Abre una terminal en tu Jetson Nano.
2. Utiliza el comando nano para crear un archivo .desktop en la ubicación deseada. Por ejemplo:

```python
nano /path/to/your/script/directory/Auto_Start.desktop
```

### Paso 2: Agregar el script al archivo .desktop

Dentro del archivo .desktop, copia y pega el siguiente contenido:

```python
[Desktop Entry]
Name=Name of the Project
Exec=/usr/bin/python3 /path/to/your/script.py
Type=Application
StartupNotify=false
Terminal=false
```

### Paso 3: Mover el archivo de inicio al directorio del sistema

Utiliza el comando sudo mv para mover el archivo .desktop al directorio de inicio del sistema:

```python
sudo mv /path/to/your/script/directory/Auto_Start.desktop /etc/xdg/autostart/
```

### Paso 4: Asignar permisos de ejecución

Asegúrate de que el archivo .desktop tenga permisos de ejecución. Puedes hacerlo con el siguiente comando:

```python
sudo chmod +x /etc/xdg/autostart/Auto_Start.desktop

```

### Paso 5: Verificar los permisos del archivo

Para verificar los permisos del archivo .desktop, ejecuta el siguiente comando:

```python
ls -l /etc/xdg/autostart/Auto_Start.desktop
```

### Paso 5: Realizar una prueba manual

Para probar si la aplicación se inicia correctamente, ejecuta el comando manualmente en la terminal:

```python
/usr/bin/python3 /path/to/your/script.py
```
Con estos pasos, has creado una aplicación de inicio que se ejecutará automáticamente cuando inicies tu Jetson Nano.


### Nota
Asegúrate de que el archivo **script.py** sea ejecutable y que todas las rutas a los archivos sean correctas. También ten en cuenta que el entorno de tu Jetson Nano debe estar configurado correctamente para ejecutar Python 3 y el **script.py**.



### Example
```python
nano /home/jetson/Documents/AI/Gloves/start_button.desktop

[Desktop Entry]
Name=Gloves Vision System
Exec=/usr/bin/python3 /home/jetson/Documents/AI/Gloves/Gloves_V1.py
Type=Application
StartupNotify=false
Terminal=false

sudo mv /home/jetson/Documents/AI/Gloves/start_button.desktop /etc/xdg/autostart/

sudo chmod +x /etc/xdg/autostart/start_button.desktop

ls -l /etc/xdg/autostart/start_gui.desktop

/usr/bin/python3 /home/jetson/Documents/AI/Gloves/Gloves_V1.py

sudo reboot
```
