# Exam 2

**Nombre:** Luis Alejandro Tróchez  

**Código:** A00054648

**Enlace repositorio:** https://github.com/zehcort/so-exam2


## Desarrollo

## 3.


En primer lugar, se ajusta el número de núcleos de la CPU que se usarán en la máquina virtual.


![][1]


A continuación, se crea el proceso que se va a utilizar para los puntos 3 y 4.


![][2]

Después de esto se procede a crear dos servicios con el uso del grupo de control CPUQuota, asignándole a ambos el 50% de tiempo de CPU.


![][3]


Luego de esto, se comienzan a correr ambos servicios con ayuda del systemctl y se comprueba el estado activo de ambos con el comandom status.


![][4]


Ahora, se ejecuta el comando top para revisar los procesos en ejecución actualmente y se comprueba el uso del 50%, aproximadamente, de ambos.


![][5]


Por último, se pretende mostrar que, al eliminar el proceso 2434 con ayuda del comando kill, el otro proceso mantiene su porcentaje de uso designado en el parámetro, dado por el comportamiento del grupo de control de CPUQuota.


![][6]


## 4.


Para este punto se utiliza el mismo proceso creado para el punto 3, pero en lugar del parámetro CPUQuota, se utiliza CPUShares, seguido de un entero entre 1 y 1000 donde, por ejemplo, 250 es el 25% del tiempo de CPU. Al servicio 1 se asigna 250 y al servicio 2 750. A continuación se muestra cuando ambos procesos se ponen a correr.


![][7]


A continuación, se muestran ambos procesos que están corriendo con la configuración hecha en el anterior paso.


![][8]


Por último, se puede observar que al matar uno de los 2 procesos, el comportamiento al usar CPUShares permite al otro proceso ocupar el 100% del tiempo de CPU.


![][9]


## 5.


• CPUQuota: Asigna un porcentaje de tiempo de CPU (denotado con el signo %) a un proceso dado que será ejecutado, indicando el máximo de tiempo que el proceso puede hacer uso de la CPU, relativo al tiempo total. Esta acción controla el atributo cpu.max


• CPUShares:Consiste en un grupo de control que corresponde al tiempo de CPU que se le pueda asignar a un proceso.  Si existen varios procesos ejecutándose al mismo tiempo, el porcentaje al que equivalga el valor que posee en CPUShares es lo que le dará en el tiempo de CPU.



Para concluir, cada grupo de control funciona de manera diferente. Por un lado, el CPUQuota intenta limitar el uso de la CPU, mientras que CPUShares está orientado a definir el comportamiento de un proceso con respecto al manejo de los recursos en un ambiente compartido. Por tal razón, el CPUQuota se podría usar cuando un proceso ocupa demasiado tiempo en CPU y pueda afectar el funcionamiento de otros, mientras que el CPUShares sería útil en un ambiente donde se necesita una gestión eficiente de los recursos para procesos con cargas para la CPU relativamente similares.





[1]: 1.PNG
[2]: 2.PNG
[3]: 3.PNG
[4]: 4.PNG
[5]: 5.PNG
[6]: 6.PNG
[7]: 7.PNG
[8]: 8.PNG
[9]: 9.PNG
