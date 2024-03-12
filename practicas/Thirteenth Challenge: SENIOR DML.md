# Actividad 2

# **Enunciado**

### Elimina todos los registros de la tabla daño.

![Untitled](Actividad%202%2086ee9283771b4994ab078f9272fd6155/Untitled.png)

```sql
DELETE FROM desperfecto;
```

### Modifica la marca y el modelo del vehículo cuyo bastidor es el *56248955632147854* a Fiat Punto.

![Untitled](Actividad%202%2086ee9283771b4994ab078f9272fd6155/Untitled%201.png)

```sql
UPDATE vehiculo
SET marca = "Fiat", modelo = "Punto"
WHERE numBastidor = "*56248955632147854";*
```

### Sin modificar la restricción ON UPDATE, que está configurado como RESTRICT, modifica el vehículo con el número del bastidor ML9KZH60ZLH180202 a NL9KZH60ZLH180202.

![Untitled](Actividad%202%2086ee9283771b4994ab078f9272fd6155/Untitled%202.png)

```sql
UPDATE vehiculo
SET numBastidor = "NL9KZH60ZLH180202"
WHERE numBastidor = "NL9KZH60ZLH180202";
```

### ¿Crees que es más eficiente que la restricción ON UPDATE tenga el valor RESTRICT o CASCADE? Justifica tu respuesta.

A mí me gusta más tener el CASCADE para que si modifico un campo de mi base de datos y es una clave foránea, se actualice en todas las tablas en las que esté,

### Sin modificar la restricción ON DELETE, que está configurado como RESTRICT, elimina el vehículo el número del bastidor NL9KZH60ZLH180202.

![Untitled](Actividad%202%2086ee9283771b4994ab078f9272fd6155/Untitled%203.png)

```sql
DELETE FROM vehiculo
WHERE numBastidor = "NL9KZH60ZLH180202";
```

### Empleando las funciones [TIMESTAMPDIFF](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_timestampdiff), [CURDATE](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_curdate) actualiza la columna edad de todos los clientes, calculando su edad real empleando la columna fechaNacimiento.

![Untitled](Actividad%202%2086ee9283771b4994ab078f9272fd6155/Untitled%204.png)

```sql
UPDATE cliente
SET edad = TRUNCATE((DATEDIFF(CURDATE(), fechaNacimiento)/365),0);
```

### En la tabla alquila, modifica la restricción de la clave foránea *dni* en ON DELETE, selecciona la opción CASCADE. Luego, elimina todos los registros de la tabla cliente cuyo dni se encuentre en la tabla alquila (inténtalo empleando una consulta en el WHERE).

```sql

```

### Elimina el alquiler del vehículo con número de bastidor 1029384756QSCEFVT y que hizo el cliente con DNI nº 10610610F.

![Untitled](Actividad%202%2086ee9283771b4994ab078f9272fd6155/Untitled%205.png)

```sql
DELETE FROM alquila
WHERE numBastidor = "1029384756QSCEFVT" AND dni = "10610610F";
```

### Elimina todos los registros de la tabla vehículo.

```sql
DELETE FROM vehiculo;
```