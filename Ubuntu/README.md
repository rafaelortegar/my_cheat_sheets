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


23. Abrirá una ventana, en la opción de "Tamaño del espacio que desea reducir, en MB deberás ingresar la cantidad a reducir y dar click en reducir. En la imagen siguiente se redujeron 61,440 MB. Este es el espacio que deseas que tenga UBUNTU en tu computadora. En mi caso, para una computadora de 500 GB de disco duro, yo reduje 300000 MB.


![image](https://user-images.githubusercontent.com/51694410/125025180-d2457800-e047-11eb-83e0-65bb183f19a9.png)



25. Una vez creada la partición, deberá verse de la siguiente forma:

![image](https://user-images.githubusercontent.com/51694410/125025352-23ee0280-e048-11eb-9341-c2cefd8f9fec.png)

27. Reiniciar el equipo para iniciar desde la USB. **IMPORTANTE:** Antes de reiniciar, es importante saber cómo acceder al menú de arranque de tu computadora, pues en cada equipo, modelo y marca suele ser diferente y es importante hacerlo bien en la primera vez.

![image](https://user-images.githubusercontent.com/51694410/125025484-5bf54580-e048-11eb-92f6-ad385e6b366d.png)

## Arranque para la instalación desde la USB
29. En el caso de la computadora del video, justo antes de reiniciar se usa la tecla "Esc" para entrar al menú de arranque. Te debe aparecer el siguiente menú, donde se selecciona "F9: Opciones de dispositivos de arranque"

![image](https://user-images.githubusercontent.com/51694410/125025716-c9a17180-e048-11eb-8d0e-b21fd70d4dce.png)

31. Se abrirá el menú de opciones del "Administrador de arranque", donde deberás seleccionar la USB (en el caso del video es una USB SanDisk), y presionar "ENTER".

![image](https://user-images.githubusercontent.com/51694410/125026051-72e86780-e049-11eb-8e15-538458878dd1.png)


33. Escoger la opción "Install Ubuntu" y presionar "Enter"

![image](https://user-images.githubusercontent.com/51694410/125026074-7aa80c00-e049-11eb-82f7-84df23f5da16.png)

## Instalación y Configuración de Ubuntu.
35. a
36. a
37. a
38. a
39. a
40. a
41. 


