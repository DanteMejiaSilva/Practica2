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

- GO es útil en aplicaciones donde la velocidad es crítica, y la trayectoria no es importante, por ejemplo, cuando el robot necesita ir de una zona segura a otra sin importar qué tan precisa sea la trayectoria intermedia.

## Instrucciones
Primero se empleó el simulador para estimar las coordenadas de los puntos clave para generar el movimiento del brazo robótico, sin embargo, al observar que sería muy complicado estimar coordenadas para generar el movimiento se optó por utilizar el brazo robótico real para tomar las coordenadas de los puntos para generar el movimiento.
<p align="justify">
![image](https://github.com/user-attachments/assets/70d517ff-50a3-42ec-8dd3-524b8f3317e8)
</p>
</p>
