# Cargar nube de puntos

Funcion para cargar las nubes de puntos desde un archivo .txt con etiqueta


# TRANSFORMAR NUBE DE PUNTOS

## Separa tallo y hojas

Separa los puntos tipo tallo y los puntos tipo hoja, 
Tambien se esta encontrando el centro del tallo para econtrar los puntos mas cercanos.

![Creacion de Mascara](https://github.com/Brayanjurado1325/Angulos-de-hojas/blob/main/Imagenes/2.png)


## SEPARAR PUNTOS CERCANOS

Se crea un vector nuevo solo con los puntos detro del circulo de proximidad al tallo.

![Creacion de Mascara](https://github.com/Brayanjurado1325/Angulos-de-hojas/blob/main/Imagenes/3.png)

## Variables de salida 

Al final de este proceso las salidas son:

* Promedio en X y Y de puntos tipo tallo.
* Nube de puntos tipo hoja cercanos al tallo.
-----------------------------

* Hojascerca
* xtm 
* ytm 
* ztm 

# Calcular número de Clusters 

Elbow Method Code

```ruby
df = pd.DataFrame(data=Hojascerca, columns = ['x','y','z'])  # Volver datos DataFrame 

## PRUEBA CON RANDO DE 1 A 10 DE POSIBLES K VECINOS 
distortions = []
K = range(1,14)
for k in K:
    kmeanModel = KMeans(n_clusters=k)
    kmeanModel.fit(df)
    distortions.append(kmeanModel.inertia_)
```


