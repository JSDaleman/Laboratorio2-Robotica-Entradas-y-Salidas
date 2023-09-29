# Laboratorio2-Robotica Entradas y Salidas
## Integrantes:

- Juan Sebastian Daleman
- Andres David Hernandez

## Solución planteada
Se emplean las funciones descritas a continuacion para realizar la escritura de las primeras 5 letras de los nombres de los integrantes ,incluida una decoracion; todo esto al oprimir un boton de un panel de control, haciendo uso de las entradas y salidas del robot maniplador.

En codigo se le asigna a la entrada DI_01 la accion de escritura, osea que al ser presionado este boton realice la accion descrita arriba y vuelva a su posicion home (todas las articulaciones en 0 grados), mientras que simultaneamente prende un testigo del panel de control asignado a la salida DO_03, indicando que la accion de escritura esta en proceso. Adicionalmente se imprimen en el FlexPendant mensajes indicativos de que la escritura esta en curso (_"Escribiendo"_)
y cuando ya se han escrito los nombres y dibujada la decoracion (_"Fin de escritura :)"_).

Por otra parte, se le asigna a la entrada DI_02 la accion de posicionar al brazo en una pose de mantenimiento la cual consiste en dejar la herramienta en una posicion cómoda para el operario, para el desmonte y/o cambio de herramienta; lo  anterior se logra posicionando las articualciones 1 y 5 en 60° y 45° respectivamente. Durante el posicionamiento, al igual que en la escritura, se imprimen mensajes en el FlexPendant acerca de los estados del robot que son: en movimineto hacia la  posicion deseada (_"Yendo a posicion de mantenimineto..."_) y cuando se llega al destino (_"En mantenimiento"_).

Cabe agregar que las entradas DI_01 y DI_02 junto con la salida DO_03, se econtraban todas en un mismo panel de control proporcionado en el LabSIR. Estas funciones descritas mediante el accionar de entradas digitales correspondientes a botones dentro del panel se evidencian mas adelante en la seccion de video de **Funcionamiento Real**.

## Codigo de rapid

Archivo de codigo en rapid: https://github.com/anhernadezdu/Laboratorio2-Robotica-Entradas-y-Salidas/blob/main/DI_DO.mod

**Funciones utilizadas**
* **main:** Es la función principal del código ene esta se ejecutan un bloque while infinito para que el programa corra de forma continua, un condicional if..elif...else el cual verifica primero si la entrada DI_01 se acciono si fue asi se esctiva el proceso de escritura con los mensajes correspondientes de proceso en el Flex Pendant, de no haberse accionado DI_01  se revisa si se acciono DI_02 de ser asi se inicia el proceso de posición de mantenimiento tambien con suss correspondientes mensajes en el Flex Pendant, por ultimo si ninguna condición se cumplio no se hace nada y se vuelven a verificar las condiciones en el cliclo infinito. 
* **Escribir:** Esta función ejecuta en secuencia Home_robot, Comenzar_mov, Home, Sebas, Andre, Sombrero_de_paja, Home, llevar a un punto intermedio y Home_robot. Esto para que del Home del robot  (todas las articulaciones en  0) llevar la herramienta al Home del proceso de escritura luego escribir todo lo que se desea para luego llevar la herramienta al Home del proceso de escritura y volver al Home del robot.
* **Home_robot:** Esta funcion lleva a todas las aricualaciones a 0 grados con una valocidad de 1000 mm/s y una exactitud de movimiento de 100.
* **Comenzar_mov:** Se lleva del Home del robot a un punto intermedio para evitar un limite del mecanismo para luego dirigirse por ultimo al Home del proceso de escritura todo esto con una valocidad de 1000 mm/s y una exactitud de movimiento de 100.
* **Home:** Permite llevar la herramienta al la posición del Home del porceso de escritura con una valocidad de 1000 mm/s y una exactitud de movimiento de 100.
* **Sebas:** Realiza el proceso de escritura de "Sebas" primero llevando la herramienta a una posición de acercamiento a la superficie de escritura con una valocidad de 1000 mm/s y una exactitud de movimiento de 10 luego se hace un acercamiento a la superficie con una valocidad de 500 mm/s y una exactitud de movimiento de 10 hasta el punto de contacto con la herramienta luego toda la escriura de las letras se hace el trazo con una valocidad de 200 mm/s y una exactitud de movimiento de 1 y luego de terminarse la primera letra la herramienta se a leja de la superficie con una valocidad de 1000 mm/s y una exactitud de movimiento de 10. las condiciones de movimiento de la herramienta de movimientos sin contacto, de acercamiento, alejamiento y trazo se mantienen en cada letra como se describieron anterioarmente.
* **Andre:** Realiza el proceso de escritura de "Andre" primero llevando la herramienta a una posición de acercamiento a la superficie de escritura con una valocidad de 1000 mm/s y una exactitud de movimiento de 10 luego se hace un acercamiento a la superficie con una valocidad de 500 mm/s y una exactitud de movimiento de 10 hasta el punto de contacto con la herramienta luego toda la escriura de las letras se hace el trazo con una valocidad de 200 mm/s y una exactitud de movimiento de 1 y luego de terminarse la primera letra la herramienta se a leja de la superficie con una valocidad de 1000 mm/s y una exactitud de movimiento de 10. las condiciones de movimiento de la herramienta de movimientos sin contacto, de acercamiento, alejamiento y trazo se mantienen en cada letra como se describieron anterioarmente.
* **Sombrero_de_paja:**  Realiza el proceso de dibujo de "un sombrero de paja" primero llevando la herramienta a una posición de acercamiento a la superficie de escritura con una valocidad de 1000 mm/s y una exactitud de movimiento de 10 luego se hace un acercamiento a la superficie con una valocidad de 500 mm/s y una exactitud de movimiento de 10 hasta el punto de contacto con la herramienta luego toda la escriura de las letras se hace el trazo con una valocidad de 200 mm/s y una exactitud de movimiento de 1 y luego de terminarse la primera letra la herramienta se a leja de la superficie con una valocidad de 1000 mm/s y una exactitud de movimiento de 10. las condiciones de movimiento de la herramienta de movimientos sin contacto, de acercamiento, alejamiento y trazo se mantienen en cada letra como se describieron anterioarmente.
* **Mantenimiento:** Esta función lleva al Home del robot luego a la posición de mantenimiento en la cual la ariculacion 1 esta a 60° y la articulación 5 a -45° con una valocidad de 1000 mm/s y una exactitud de movimiento de 100.

# Videos de funcionamiento
## Funcionamiento en simulación

https://github.com/anhernadezdu/Laboratorio2-Robotica-Entradas-y-Salidas/assets/70998067/863903ef-7461-4aa5-9299-8bf5431cf896

## Funcionamiento en el robot real

[![Alt text](https://img.youtube.com/vi/gwNfsEZBfac/0.jpg)](https://www.youtube.com/watch?v=gwNfsEZBfac)

**Resultado de escritura**

![Imagen de WhatsApp 2023-09-28 a las 13 53 28_5f96b356](https://github.com/anhernadezdu/Laboratorio2-Robotica-Entradas-y-Salidas/assets/70998067/3b9b706b-4106-4cdb-8f90-f2f653c12aff)


