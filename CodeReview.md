# Code Review - Rodrigo Valori

## 1 - [Lombok](https://projectlombok.org/)
Es una librería Java basada en anotaciones que permite reducir el código repetitivo (boilerplate code). Lombok ofrece varias anotaciones destinadas a reemplazar el código Java que es bien conocido por ser estándar, repetitivo o tedioso de escribir y que no aporta lógica al negocio (getter, setter, equals, hashcode, constructores y otros).

Este sería un ejemplo de uso de las anotaciones de Lombok en la clase PublicAd.java:
```
@Getter
@Setter
@NoArgsConstructor
@AllArgsConstructor
@ToString
public class PublicAd {

    private Integer id;
    private String typology;
    private String description;
    private List<String> pictureUrls;
    private Integer houseSize;
    private Integer gardenSize;
}
```

De esta forma, el codigo és mucho mas limpio y escalable.

## 2 - [Swagger UI](https://swagger.io/tools/swagger-ui/)
Permite que cualquier persona, ya sea su equipo de desarrollo o sus consumidores finales, visualice y interactúe con los recursos de la API sin tener implementada ninguna lógica de implementación. Se genera automáticamente a partir de su especificación OpenAPI (anteriormente conocida como Swagger), con la documentación visual que facilita la implementación de back-end y el consumo del lado del cliente.

El código no está documentado, por lo que el Swagger UI sería una buena opción para una documentación visual sencilla en la que cualquier persona pueda interactuar con los endpoints de la API.

Ejemplo de una documentación hecha en Swagger UI: [**Petstore**](https://petstore.swagger.io/?_ga=2.225198749.622144049.1667318149-1220241046.1667318149)

## 3 - Comentarios
Idealmente, el código debería explicarse por sí mismo y ni siquiera necesitaria ningún comentario. Sin embargo, a veces no es posible expresar algo simplemente usando código. 

El código presentado no es lo más limpio y legible posible debido a la cantidad de comentarios innecesarios presentes, ya que en muchas clases el código es bastante claro y no sería necesario agregarlos.

## 4 - Logging
Es el proceso de imprimir o registrar las actividades en una aplicación que ayuda a los desarrolladores a comprender y analizar cuando hay errores inesperados en el sistema. Ademas los logs se pueden clasificar en función de su gravedad en forma de niveles de registro.

Por lo tanto, no se está aplicando ninguna trazabilidad (logs)
