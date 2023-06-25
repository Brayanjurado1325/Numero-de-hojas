# Cargar nube de puntos

Funcion para cargar las nubes de puntos desde un archivo .txt con etiqueta



# CALCULO DE ANGULOS 
Calculo de angulo con dos vectores 


![Creacion de Mascara](https://github.com/Brayanjurado1325/Angulos-de-hojas/blob/main/Imagenes/1.png)


```ruby
def angulo(u,v):
  x = u.dot(v)
  y = np.linalg.norm(u)*np.linalg.norm(v)
  an = acos(x/y)   # Angulo en radianes
  a = math.degrees(an)  # Angulo en grados
  return a
```
Calculo de angulo usando 3 puntos

```ruby
def anguloFin(b,t,p):
  u= t - b
  v= p - b
  a = angulo(u,v)
  return a
```

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

# CALCULAR ANGULOS POR ALTURA

1. Sacar los cluster en el eje z
2. Separar los grupos en diferentes grupos
3. Seleccionar el menor valor en Z de cada punto para que sea el punto base. 
4. Seleccionar los puntos mas alejados del punto base en cada closter.
5. usando como referencia el el centro X y Y, y desplazando en segun el punto de cada closter identificado en el punto 3
6. Calcular los angulos de cada punto y detarminar un promedio.

## Calcular número de Clusters 

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