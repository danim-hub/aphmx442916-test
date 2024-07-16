# Ejercicio de práctica .Net y Angular

Muestre sus conocimientos en Angular y .Net con el siguiente laboratorio, que puede demorar alrededor de 60 minutos.

El tiempo es corto. Adminístrelo de manera que alcance a realizar un producto mínimo que muestre sus habilidades
tanto en el frontend como en el backend.

## Contexto

Tenemos un servicio "Sales API" activo, que regresa información sobre las ventas y gastos de distintas sucursales de una empresa:

[http://aphmx442916.azurewebsites.net/sales/data/{id}/{yyyy-MM-dd}](https://aphmx442916.azurewebsites.net/sales/data/619/2015-06-12)

Este servicio regresa su resultado en formato JSON, como en el ejemplo:

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

- Parámetros: Lista de números de sucursales, separados por coma
- Fecha

Algunos números de sucursal válidos son el 619, 626 y 643, aunque el usuario podría introducir hasta 20 IDs si así lo requiere.

<table>
  <tr><td colspan=2 align=center><b>Ventas por sucursal</b></td></tr>
  <tr><td>Sucursales:</td><td>619,626,643</td></tr>
  <tr><td>Fecha:     </td><td>[2024-12-06]</td></tr>
  <tr><td colspan=2 align=center>  [ Generar ] </td></tr>
</table>

El reporte debe mostrar la siguiente información, con las ventas, gastos y utilidad y sus totales, únicamente para los números de sucursal introducidos por el usuario:

| Sucursal | Nombre | Ventas | Gastos | Utilidad |
| --- | --- | --- | --- | --- |
| 619 | Almacén Puebla | 12,619.42 | 372.16 | 12,1247.26 |
| 626 | Finanzas | 0.00 | 22,311.15 | (22,311.15) |
| 643 | Tienda en línea | 33,729.15 | 1,200.00 | 35,529.15 |
|     | Total | 46,348.57 | 23,883.00 | 22,465.57 |

## Actividades por realizar
El reporte deberá realizarse de la siguiente manera:

- API en .Net usando C#
  - Proyecto “NombreCandidato-API”
  - Recibe los parámetros: lista de números de sucursal y fecha
  - Regresa los datos necesarios para mostrar el reporte, incluyendo los totales
  - Este proyecto debe invocar el servicio arriba mencionado tantas veces como sea necesario, por cada uno de los números de sucursal recibidos.
  - SQL Server: Acumular en la base de datos los resultados obtenidos del servicio, en una tabla de ApiResult (id,date,name,sales,expenses,profit) utilizando un procedimiento almacenado que reciba estos datos, y los inserte o actualice según sea necesario.
  - Bonus: El servicio "Sales API" tarda 8 segundos en responder. Asegure que el tiempo de respuesta de su API sea menor a 10 segundos aun recibiendo 5 IDs distintos
- Interfaz de usuario en Angular
  - Proyecto “NombreCandidato-Frontend”
  - Captura de parámetros
  - Información del reporte
  - No realice cálculos ni sumas en el frontend, debe mostrarse tal cual el resultado del API.
  - Pista: Realice un Componente para el formulario de datos, otro para el Reporte, y un Servicio para invocar el API.

## Tiempo estimado
El tiempo estimado es de 60 minutos.
