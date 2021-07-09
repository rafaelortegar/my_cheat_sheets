Requerimientos:
* USB de 4 GB

# Instalación de Ubuntu en Dual Boot con Windows 10

Para la instalación de Ubuntu, me guié de los siguientes dos videos:
* Instalación dual boot [aqui](https://www.youtube.com/watch?v=tiB3kzxK4mU)
* Partición de discos de root, swap y home [aqui](https://www.youtube.com/watch?v=yMgzz1fvVCc)

Para no hacer de nuevo la instalación de ubuntu, el tutorial va a incluir screenshots de los videos.

**En Windows:**
1. Instalar el programa [Rufus](https://rufus.ie/en_US/)
2. Descargar la [Imagen de Ubuntu](https://ubuntu.com/download/desktop). Para esta parte, recomiendo bajar la versión que dice LTS (Long Term Support).
3. Insertar USB

## Preparación del USB para la instalación
3. Ejecutar la aplicación Rufus, la cual te solicitará acceso como administrador. Permitir cambios.
![image](https://user-images.githubusercontent.com/51694410/124964377-9201dd80-dfe6-11eb-939c-fd4f0ba990fc.png)


4. En "Elección de arranque", seleccionar la opción de "Disco o imagen ISO, presionar en el botón de seleccionar y seleccionar la ISO de Ubuntu descargada en el paso 2.
![image](https://user-images.githubusercontent.com/51694410/125024027-9f01e980-e045-11eb-90c4-10f5487983f1.png)

5. En "Esquema de partición" se selecciona:
  * MBR si tienes windows 7
  * GPT si tienes windows 8 o superior

7. La opción Sistema destino se configura automáticamente.

9. En "Sistema de archivos" seleccionar "FAT32"
10. En "Tamaño del Cluster" poner 4096 bytes
11. Click en "Empezar", asegúrate de que la configuración está como en la imagen:
![image](https://user-images.githubusercontent.com/51694410/125024349-30715b80-e046-11eb-88bb-48fbd100d098.png)

13. Saldrá un recuadro, donde deberás elegir la opción "Escribir en modo imagen ISO (Recomendado) y click en "Ok"
![image](https://user-images.githubusercontent.com/51694410/125024407-5696fb80-e046-11eb-9114-fa408760acad.png)

15. Saldrá una advertencia de que la USB será formateada, click en "Aceptar"
![image](https://user-images.githubusercontent.com/51694410/125024516-8a722100-e046-11eb-8f26-f8a243583085.png)

## Partición del disco duro (o disco de estado sólido)

**En windows**
17. Click derecho en botón de inicio y seleccionar la opción de "Administración de discos"
![image](https://user-images.githubusercontent.com/51694410/125024712-f2286c00-e046-11eb-899b-0d9cc17eb313.png)

19. Click derecho en el disco local "C:"
![image](https://user-images.githubusercontent.com/51694410/125024780-0ec4a400-e047-11eb-9651-6e7b3c177f70.png)


21. Seleccionar la opción reducir volumen
![image](https://user-images.githubusercontent.com/51694410/125024919-4f242200-e047-11eb-8087-3e959ed5b684.png)


23. Abrirá una ventana, en la opción de "Tamaño del espacio que desea reducir, en MB deberás ingresar la cantidad a reducir. En la imagen siguiente se redujeron 61,440 MB
![image](https://user-images.githubusercontent.com/51694410/125025038-8db9dc80-e047-11eb-8e4a-49a273ac14d1.png)


25. a
26. a
27. a
28. a
29. a
30. a
31. a
32. a
33. a
34. a
35. a
36. 


