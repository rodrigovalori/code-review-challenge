# Code Review - Rodrigo Valori

## 1 - [Lombok]([url](https://projectlombok.org/))
Es una librería Java basada en anotaciones que permite reducir el código repetitivo (boilerplate code). Lombok ofrece varias anotaciones destinadas a reemplazar el código Java que es bien conocido por ser estándar, repetitivo o tedioso de escribir y que no aporta lógica al negocio (getter, setter, equals, hashcode, constructores y otros).

Este sería un ejemplo de uso de las anotaciones de Lombok en la clase PublicAd.java:
```
@Data
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

## 2 - [Swagger UI]([url](https://swagger.io/tools/swagger-ui/))
Permite que cualquier persona, ya sea su equipo de desarrollo o sus consumidores finales, visualice y interactúe con los recursos de la API sin tener implementada ninguna lógica de implementación. Se genera automáticamente a partir de su especificación OpenAPI (anteriormente conocida como Swagger), con la documentación visual que facilita la implementación de back-end y el consumo del lado del cliente.

Ejemplo de una documentación hecha en Swagger UI: [**Petstore**]([url](https://petstore.swagger.io/?_ga=2.225198749.622144049.1667318149-1220241046.1667318149))
