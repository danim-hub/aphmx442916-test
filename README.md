# Ejercicio de práctica .Net y Angular

Muestre sus conocimientos en Angular y .Net con el siguiente laboratorio, que puede demorar alrededor de 60 minutos.

El tiempo es corto. Adminístrelo de manera que alcance a realizar un producto mínimo que muestre sus habilidades
tanto en el frontend como en el backend.

## Contexto

Tenemos el siguiente servicio activo, que regresa información sobre las ventas y gastos de distintos departamentos de una empresa:

[http://aphmx442916.azurewebsites.net/sales/data/{id}/{yyyy-MM-dd}](http://aphmx442916.azurewebsites.net/sales/data/%7bid%7d/%7byyyy-MM-dd%7d)

Este servicio regresa un siguiente JSON, como en el siguiente ejemplo:

```bash
$ curl https://aphmx442916.azurewebsites.net/sales/data/619/2015-06-12
```

```json
{
  "id":619,
  "date":"2015-06-12",
  "name":"Almacén Puebla",
  "sales":25195,
  "expenses":993.8
}
```

## Especificaciones
Realice un reporte con las siguientes especificaciones:

- Parámetros: Lista de IDs de centros de costo, separados por coma
- Fecha

Algunos ID válidos son el 619, 626 y 643, aunque el usuario podría introducir hasta 20 IDs si así lo requiere.

El reporte debe mostrar la siguiente información, con las ventas, gastos y utilidad y sus totales, únicamente para los ID introducidos por el usuario:

| C. Costos | Nombre | Ventas | Gastos | Utilidad |
| --- | --- | --- | --- | --- |
| 619 | Almacén Puebla | 12,619.42 | 372.16 | 12,1247.26 |
| 626 | Finanzas | 0.00 | 22,311.15 | (22,311.15) |
| 643 | Tienda en línea | 33,729.15 | 1,200.00 | 35,529.15 |
|     | Total | 46,348.57 | 23,883.00 | 22,465.57 |

## Actividades por realizar
El reporte deberá realizarse de la siguiente manera:

- API en .Net usando C#
  - Proyecto “NombreCandidato-API”
  - Recibe los parámetros IDs y fecha
  - Regresa los datos necesarios para mostrar el reporte
  - Registrar en la base de datos SQL Server la bitácora de la petición, incluyendo los parámetros, el resultado que se regresa y las iniciales del nombre del candidato.
  - Este proyecto debe invocar el servicio arriba mencionado tantas veces como sea necesario, por cada uno de los IDs recibidos.
  - Bonus: Dicho servicio tarda 8 segundos en responder. Asegure que el tiempo de respuesta de su API sea menor a 10 segundos aun recibiendo 3 IDs
- Interfaz de usuario en Angular
  - Proyecto “NombreCandidato-Frontend”
  - Captura de parámetros
  - Información del reporte
  - No realice cálculos ni sumas en este proyecto, debe mostrarse tal cual el resultado del API.
  - Pista: Realice un Componente para el formulario de datos, otro para el Reporte, y un Servicio para invocar el API.

## Tiempo estimado
El tiempo estimado es de 60 minutos.
