# Calculo del número de hojas.


## Descripcion de codigo 



### Datos de entrada 
 


### Paso a paso

Para el cálculo del número de hojas se tomaron como entradas el vector Hojas y el vector Tallo, ya que para este método se inicia seleccionando los puntos mas cercanos al tallo como se observa en la Figura se traza un circulo de distancia uniforme al centro del tallo visto desde la parte superior


![Creacion de Mascara](https://github.com/Brayanjurado1325/Angulos-de-hojas/blob/main/Imagenes/puntosceranos.png)


Los puntos del vector tipo hoja se almacenan en un vector que contiene las coordenadas XYZ de los puntos, creando esta nueva nube de puntos se espera facilitar el conteo del numero de hojas ya que ayuda a diferenciar de mejor manera los grupos de cada hoja como se muestra en la siguiente Figura donde desde una vista lateral se aprecian tres grupos que corresponden a las tres hojas de la planta para este ejemplo.



![Creacion de Mascara](https://github.com/Brayanjurado1325/Angulos-de-hojas/blob/main/Imagenes/puntosccescanos.png)


Para determinar el numero de hojas a partir del nuevo vector es necesario determinar el número de conglomerados en este conjunto de datos, para esto se utilizó el método del codo con el que se obtienen gráficas como la que se muestra en la Figura

![Creacion de Mascara](https://github.com/Brayanjurado1325/Angulos-de-hojas/blob/main/Imagenes/ebowl.png)