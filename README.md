# Práctica 2
<p align="justify">

## Integrantes:
- Dante Mejía Silva
- Atzin Morales Alejandre

## Introducción
En los robots Epson, como el Epson C4, los comandos GO y MOVE se utilizan para controlar el movimiento del robot, pero cada uno tiene funciones y comportamientos específicos.

**Comando MOVE**
- El comando MOVE se utiliza para realizar movimientos controlados y suaves del robot.

- Mueve el robot de una posición a otra de manera lineal (en línea recta).

- El robot sigue la trayectoria más corta, pero se mantiene dentro de los límites de velocidad y aceleración establecidos.

- Se puede utilizar para moverse a puntos definidos en el espacio o posiciones de trabajo sin colisionar con obstáculos.

**Comando GO**
- El comando GO ejecuta movimientos más rápidos y directos, pero sin control sobre la trayectoria.

- Se utiliza cuando se necesita mover el robot rápidamente de un punto a otro sin importar la trayectoria que siga.

- GO es útil en aplicaciones donde la velocidad es crítica, y la trayectoria no es importante, por ejemplo, cuando el robot necesita ir de una zona segura a otra sin importar qué tan precisa sea la trayectoria intermedia. [1]

## Instrucciones
Primero se empleó el simulador para estimar las coordenadas de los puntos clave para generar el movimiento del brazo robótico, sin embargo, al observar que sería muy complicado estimar coordenadas para generar el movimiento se optó por utilizar el brazo robótico real para tomar las coordenadas de los puntos para generar el movimiento.

![image](https://github.com/user-attachments/assets/70d517ff-50a3-42ec-8dd3-524b8f3317e8)

Posteriormente pasamos a programar el robot físico, el codigo usado es el siguiente:
```
Function main
Home
Go primero
On 2
Go segundo
Off 2
Go primero
Home
Go tercero
On 2
Home
Fend
```
Primeramente, se colocó el brazo en la posición de “Home”.

![image](https://github.com/user-attachments/assets/a9802f0f-37f8-452f-9dea-7b1c052624fb)
![Imagen de WhatsApp 2024-09-06 a las 21 06 59_a72e35e1](https://github.com/user-attachments/assets/cfe62f50-e5b8-4858-9d20-5329b783c333)

Después cuidadosamente tratando de evitar una colisión se movió el brazo a la posición “primero”, la cual corresponde al punto donde el brazo está encima del fusible, es decir, las coordenadas X y Y son las correctas, sin embargo, el brazo en la coordenada Z se encuentra desplazado un poco hacia arriba.

![image](https://github.com/user-attachments/assets/875c6652-5476-442f-8070-d74bd59e48bc)

La posición “segundo” corresponde al punto donde el brazo toma el fusible, es decir, se coloca se disminuye en Z para bajar el brazo. Para tomar el brazo es necesario cerrar la pinza del brazo, esto mediante el comando “off 2”.

![image](https://github.com/user-attachments/assets/ebf394fe-d91f-442f-b0b0-a1cd8caa1bc5)

Una vez tomado el fusible se regresa el brazo a la posición “primero” y después a “Home”.

Ahora, es necesario soltar el fusible encima de la caja, por lo que se toma la posición “tercero” la cual corresponde a donde el brazo se encuentra encima de la caja y posteriormente se suelta el fusible mediante el comando “on 2”.

![image](https://github.com/user-attachments/assets/97e77880-f3ab-4ce7-af2f-9f4b6c5daf91)

Teniendo las coordenadas necesarias para generar la trayectoria completa que seguirá el brazo se pasó a programar el robot donde se colocan los puntos a los cuales se moverá el brazo mediante el comando “go”. Inicialmente se coloca el brazo la posición de “Home” y después se coloca en orden los putos para generar la trayectoria, así como el accionamiento de la pinza cuando esta tome el fusible y lo suelte.

![image](https://github.com/user-attachments/assets/d4d6159c-69e2-4b76-863b-e2b282353a5e)

Con esto el brazo primeramente se coloca en posición “Home”, después se dirige hacia el fusible, lo toma, regresa a la posición de home y se acerca a la caja para finalmente soltar el fusible encima de la caja. 

**Comparación:**

Por cuestiones horarias no se alcanzó a probar la configuración de Home, si embargo sus principales diferencias son:

- MOVE: Movimiento lineal, más preciso, controlado, pero puede ser más lento debido a las limitaciones de velocidad y aceleración.
- GO: Movimiento más rápido, directo, sin control sobre la trayectoria intermedia, ideal para tareas que no requieran precisión en la trayectoria.
  
Ambos comandos son esenciales dependiendo de la aplicación del robot. Si buscas precisión y seguridad, utiliza MOVE; si la velocidad es más importante, entonces GO es la opción adecuada.

## Conclusiones
***Atzin Morales Alejandre:*** La práctica en el laboratorio de robótica destacó la importancia de la interacción directa con el brazo robótico para obtener resultados precisos en la programación de movimientos. Aunque el simulador permitió una primera aproximación, se demostró que trabajar con el robot físico facilita la identificación de coordenadas exactas y el ajuste necesario en cada eje, evitando así posibles errores en la estimación de posiciones clave.

El uso del brazo robótico para realizar una tarea sencilla, como tomar y soltar un fusible, reveló lo crucial que es coordinar los movimientos y la manipulación de la pinza mediante comandos apropiados. Esto no solo asegura la correcta ejecución de la tarea, sino también la repetitividad del proceso. En resumen, la práctica subraya la necesidad de una programación robusta y meticulosa para garantizar que el brazo realice las trayectorias esperadas con precisión y sin colisiones, mejorando la eficacia en aplicaciones industriales.

***Dante Mejía Silva:*** Durante la práctica en el laboratorio de robótica, se evidenció la importancia de trabajar directamente con el brazo robótico real para obtener las coordenadas precisas que permiten generar trayectorias de movimiento efectivas. Aunque el simulador se empleó inicialmente para estimar las coordenadas de los puntos clave, se comprobó que la obtención manual de las posiciones resultó más eficiente, especialmente para evitar colisiones y garantizar el correcto desplazamiento en los ejes X, Y y Z.

El proceso de manipulación del brazo robótico, desde la posición "Home" hasta la interacción con el fusible y su colocación en la caja, mostró cómo la programación secuencial de movimientos y comandos para controlar la pinza son fundamentales para completar las tareas automatizadas con precisión. Al tener las coordenadas correctas y programar la trayectoria en el sistema, se logró que el brazo realizara el ciclo completo de tomar y soltar el fusible sin errores. Esto subraya la importancia de una programación adecuada para garantizar un funcionamiento seguro y eficiente en entornos automatizados.

## Referencias Bibliográficas 
[1] 	EpsonCompany, «Especialistas en automatización industrial». 2024, https://www.epson.es/es_ES/robots

</p>

