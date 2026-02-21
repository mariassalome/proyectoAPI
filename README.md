# PROYECTO API: Gestión de inventario de totebags 

## Estudiantes: Maria Salomé Alzate Pamplona - Paulina Londoño Díaz

[URL de la API:](https://6987b995780e8375a686e28f.mockapi.io/totebags)

*1- Modelo de datos diseñado con mockAPI:*
    *-Se configura el modelo totebags con la siguiente estructura de datos:*
      
  ```
  [
    {
    "nombre": "nombre 1",
    "precio": "precio 1",
    "caracteristicas": {

    },
    "clasificacion": [],
    "enInventario": false,
    "id": "1"
  },
  {
    "nombre": "nombre 2",
    "precio": "precio 2",
    "caracteristicas": {

    },
    "clasificacion": [],
    "enInventario": false,
    "id": "2"
  }
  ]
  ```
  
  *2- Operaciones CRUD y respuesta de Postman*

  *a-. Obtención de registros GET:*
    
    - Status code: 200 OK
    
    -Respuesta de Postman:
```      
[
    {
        "nombre": "nombre 1",
        "precio": "precio 1",
        "caracteristicas": {},
        "clasificacion": [],
        "enInventario": false,
        "id": "1"
    },
    {
        "nombre": "nombre 2",
        "precio": "precio 2",
        "caracteristicas": {},
        "clasificacion": [],
        "enInventario": false,
        "id": "2"
    }
]
```
  
*b-. Creación de un nuevo registro POST:*

    - Status code: 201 Created

- Cuerpo enviado a Postman:
```    
{
        "nombre": "Totebag Singapur",
        "precio": "130.000 COP",
        "caracteristicas": {
            "Tamaño": "Mediano",
            "Color": "Beige"
        },
        "clasificacion": ["Tendencias", "Bestseller"],
        "enInventario": true
}
```

- Respuesta de Postman: 

```    
{
    "nombre": "Totebag Singapur",
    "precio": "130.000 COP",
    "caracteristicas": {
        "Tamaño": "Mediano",
        "Color": "Beige"
    },
    "clasificacion": [
        "Tendencias",
        "Bestseller"
    ],
    "enInventario": true,
    "id": "3"
}
```

*c-. Consulta del registro individual GET:*

    - Endpoint: /totebags/3
    - Status code: 200 OK

    -Respuesta de Postman:
```
{
    "nombre": "Totebag Singapur",
    "precio": "130.000 COP",
    "caracteristicas": {
        "Tamaño": "Mediano",
        "Color": "Beige"
    },
    "clasificacion": [
        "Tendencias",
        "Bestseller"
    ],
    "enInventario": true,
    "id": "3"
}
```

*d-. Actualización de un registro PUT:*

    - Status code: 200 OK
    - Modificación: Actualización del stock y el precio de la totebag 

    -Respuesta de Postman:
```
{
    "nombre": "Totebag Singapur",
    "precio": "150.000 COP",
    "caracteristicas": {
        "Tamaño": "Mediano",
        "Color": "Beige"
    },
    "clasificacion": [
        "Tendencias",
        "Bestseller"
    ],
    "enInventario": false,
    "id": "3"
}
```

*e-. Eliminación de un registro DELETE:*

    -Status Code 200 OK
    
    -Respuesta Postman: 

```
{
    "nombre": "Totebag Singapur",
     "id": "3"
}
```

*f-. Validación de recurso inexistente GET 404:*

    - Status Code: 404 Not Found

    - Respuesta Postman: 
    
```
"Not found"
```

*3 Resumen del endpoitn y del HTTP*

| Acción           |       Metodo        |          Enpoint       |          HTTP        |
 ------------------|:-------------------:|:----------------------:|:--------------------:
|  listar todo     |        GET          |        `/totebags`     |         200 OK       |
 ------------------|:-------------------:|:----------------------:|:--------------------:
|  Crear           |        POST         |        `/totebags`     |         201 Created  |
 ------------------|:-------------------:|:----------------------:|:--------------------:
|  Ver por ID      |        GET          |        `/totebags/3`   |         200 OK       |
 ------------------|:-------------------:|:----------------------:|:--------------------: 
|  Actualizar      |       PUT           |       `/totebags/3`    |        200 OK        |
 ------------------|:-------------------:|:----------------------:|:--------------------: 
|  Borrar          |       DELETE        |       `/totebags/3`    |         200 OK       |
 ------------------|:-------------------:|:----------------------:|:--------------------: 
|  Error           |       GET           |       `/totebags/3`    |     404 Not Found    |