# Code Review - Rodrigo Valori

## 1 - Lombok
Lombok podría haberse utilizado para reemplazar el código Java que es bien conocido por ser estándar, repetitivo o tedioso de escribir y que no trae lógica comercial (getter, setter, equals, hashcode, constructores y otros).

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

## 2 - Swagger UI
El código no está documentado, por lo que el Swagger UI sería una buena opción para una documentación visual sencilla en la que cualquier persona pueda interactuar con los endpoints de la API.

Ejemplo de una documentación hecha en Swagger UI: [**Petstore**](https://petstore.swagger.io/?_ga=2.225198749.622144049.1667318149-1220241046.1667318149)

## 3 - Comentarios
Idealmente, el código debería explicarse por sí mismo y ni siquiera necesitaria ningún comentario. El código presentado no es lo más limpio y legible posible debido a la cantidad de comentarios innecesarios presentes, ya que en muchas clases el código es bastante claro y no sería necesario agregarlos.

Lo ideal seria remover todos los comentarios innecesarios y describir mejor los metodos y variables con nombres mas significativos. De esta forma el código es más limpio y conciso.

## 4 - Logging
Sería aconsejable agregar logs informativos de aviso de inicio y fin de procesos, como por ejemplo al inicio y fin de una requisicion. También sería muy útil tener logs de aviso de errores en caso de excepciones. Se podría implentar fácilmente la trazabilidad con la anotación ``` @Slf4j ``` de Lombok.

## 5 - Testing
La cobertura de las pruebas es solo del 52%, que es muy baja. Para que una aplicación tenga una tasa de cobertura de prueba considerada óptima, debe mantenerse en un mínimo del 70%. Aparte de eso, solo se prueba la clase AdsServiceImpl.java, por lo que todas las demás no tienen ningún tipo de prueba. Por último, solo se realizan pruebas unitarias y no pruebas de integración, lo que hace con que el código no sea ni un poco confiable.

## 6 - Nombres significativos
Muchos parámetros y variables tienen nombres que no muestran su verdadera intención, provocando desinformación y dudas a la hora de leer el código.
Por lo tanto, se podrían cambiar muchos nombres por algo más claro y descriptivo, como por ejemplo:

- ``` public boolean equals(Object o) {} ``` -> ``` public boolean equals(Object object) {} ```
- ``` List<String> wds = Arrays.asList(description.split(" ")); ``` -> ``` List<String> words = Arrays.asList(description.split(" ")); ```
- ``` List<PublicAd> result = new ArrayList<>(); ``` -> ``` List<PublicAd> publicAdsList = new ArrayList<>(); ```
- ``` List<QualityAd> result = new ArrayList<>(); ``` ->``` List<QualityAd> qualityAdsList = new ArrayList<>(); ```

## 7 - Correcciones
1 - AdsServiceImpl.java#calculateScore
```
if (ad.isComplete()) {
    score = Constants.FORTY;
}
```
Falta el '+' para sumar 40 puntos al score, por lo tanto lo correcto sería:
```
if (ad.isComplete()) {
    score += Constants.FORTY;
}
```

## 8 - Constantes
La clase Constants.java no es nada descriptiva. por lo que los nombres de las constantes deberian hacer referencia a su significado y no al valor de su contenido.

Por ejemplo, la constante ``` public static final int THIRTY = 30; ``` sería mucho más claro si fuera así: ``` public static final int LARGE_FLAT_SCORE = 30; ```.

Todas las constantes de esta clase deberían tener sus nombres revisados, pero este es solo un ejemplo de cómo un nombre mas descriptivo haría mucho más fácil comprender el propósito de la constante.


