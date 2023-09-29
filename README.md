# Laboratorio2-Robotica Entradas y Salidas
## Integrantes:

- Juan Sebastian Daleman
- Andres David Hernandez

## Solución planteada
Se emplean las funciones descritas a continuacion para realizar la escritura de las primeras 5 letras de los nombres de los integrantes ,incluida una decoracion; todo esto al oprimir un boton de un panel de control, haciendo uso de las entradas y salidas del robot maniplador.

En codigo se le asigna a la entrada DI_01 la accion de escritura, osea que al ser presioando este boton realice la accion descrita arriba y vuelva a su posicion home (todas las articulaciones en 0 grados), mientras que simultaneamente prende un testigo del pane lde control asignado a la salida DO_03, indicando que la accio nde escritura esta en proceso. Adicionalmente se imprimen en el FlexPendant mensajes indicativos de que la escritura esta en curso (_"Escribiendo"_)
y cuando ya se han escrito los nombres y dibujada la decoracion (_"Fin de escritura :)"_).

Por otra parte, se le asigna a la entrada DI_02 la accion de posicionar al brazo en una pose de mantenimiento la cual consiste en dejar la herramienta en una posicion cómoda para el operario, para el desmonte y/o cambio de herramienta; lo  anterior se logra posicionando las articualciones 1 y 5 en 60° y 45° respectivamente. Durante el posicionamiento, al igual que en la escritura, se imprimen mensajes en el FlexPendant acerca de los estados del robot que son: en movimineto hacia la  posicion deseada (_"Yendo a posicion de mantenimineto..."_) y cuando se llega al destino (_"En mantenimiento"_).

Cabe agregar que las entradas DI_01 y DI_02 junto con la salida DO_03, se econtraban todas en un mismo panel de control proporcionado en el LabSIR. Estas funciones descritas mediante el accionar de entradas digitales correspondientes a botones dentro del panel se evidencian mas adelante en la seccion de video de **Funcionamiento Real**.

## Codigo de rapid

Archivo de codigo en rapid: https://github.com/anhernadezdu/Laboratorio2-Robotica-Entradas-y-Salidas/blob/main/DI_DO.mod

**Funciones utilizadas**
* **main**
* **Escribir**
* **Home_robot**
* **Comenzar_mov**
* **Home**
* **Sebas**
* **Andre**
* **Sombrero_de_paja**
* **Mantenimiento**

# Videos de funcionamiento
## Funcionamiento en simulación

https://github.com/anhernadezdu/Laboratorio2-Robotica-Entradas-y-Salidas/assets/70998067/863903ef-7461-4aa5-9299-8bf5431cf896

## Funcionamiento en el robot real

[![Alt text](https://img.youtube.com/vi/gwNfsEZBfac/0.jpg)](https://www.youtube.com/watch?v=gwNfsEZBfac)

**Resultado de escritura**

![Imagen de WhatsApp 2023-09-28 a las 13 53 28_5f96b356](https://github.com/anhernadezdu/Laboratorio2-Robotica-Entradas-y-Salidas/assets/70998067/3b9b706b-4106-4cdb-8f90-f2f653c12aff)


