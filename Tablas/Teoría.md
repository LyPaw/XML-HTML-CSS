# Guía Completa de Tablas en HTML

Las tablas en HTML permiten organizar datos en filas y columnas. Su uso principal es mostrar información tabular, pero para dominarlas necesitamos comprender **estructura, semántica, atributos y buenas prácticas**.

---

## 1. Estructura Básica de una Tabla

Una tabla se compone principalmente de:

- **Filas (`<tr>`)**: Agrupan celdas horizontales.
- **Celdas de datos (`<td>`)**: Contienen la información de cada fila.
- **Celdas de cabecera (`<th>`)**: Indican títulos de columnas o filas y aparecen en negrita por defecto.
- **Título (`<caption>`)**: Describe el contenido de la tabla (opcional).

### Ejemplo:

```html
<table>
  <caption>Tabla de Ejemplo</caption>
  <tr>
    <th>Nombre</th>
    <th>Edad</th>
    <th>Ciudad</th>
  </tr>
  <tr>
    <td>Ana</td>
    <td>25</td>
    <td>Madrid</td>
  </tr>
  <tr>
    <td>Carlos</td>
    <td>30</td>
    <td>Barcelona</td>
  </tr>
</table>

```
2. Agrupación Semántica
HTML5 permite usar etiquetas semánticas para mejorar la accesibilidad:

thead: Cabecera de la tabla.

tbody: Cuerpo principal de la tabla.

tfoot: Pie de la tabla.



```html
Copiar código
<table>
  <caption>Productos</caption>
  <thead>
    <tr>
      <th>Producto</th>
      <th>Precio</th>
      <th>Stock</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Ordenador</td>
      <td>800€</td>
      <td>15</td>
    </tr>
    <tr>
      <td>Teclado</td>
      <td>30€</td>
      <td>50</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="2">Total artículos</td>
      <td>65</td>
    </tr>
  </tfoot>
</table>
```

<table>
  <caption>Productos</caption>
  <thead>
    <tr>
      <th>Producto</th>
      <th>Precio</th>
      <th>Stock</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Ordenador</td>
      <td>800€</td>
      <td>15</td>
    </tr>
    <tr>
      <td>Teclado</td>
      <td>30€</td>
      <td>50</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td colspan="2">Total artículos</td>
      <td>65</td>
    </tr>
  </tfoot>
</table>


Nota: HTML4 también soporta <thead>, <tbody> y <tfoot>, pero HTML5 es más recomendado para accesibilidad y compatibilidad con tecnologías de asistencia.

3. Atributos de Tablas
Atributo	Descripción
border	Grosor del borde de la tabla (no recomendado en HTML5).
cellpadding	Espacio entre contenido y borde de celda.
cellspacing	Espacio entre celdas.
width	Anchura de la tabla (usar CSS en HTML5).
align	Alineación de la tabla (left, center, right) (obsoleto HTML5).
bgcolor	Color de fondo (obsoleto HTML5).
rules	Bordes internos visibles: all, cols, rows, none (HTML4).

Ejemplo usando atributos:
html
Copiar código
<table border="1" cellpadding="5" cellspacing="2">
  <tr>
    <th>Nombre</th>
    <th>Edad</th>
  </tr>
  <tr>
    <td>Laura</td>
    <td>28</td>
  </tr>
</table>
4. Atributos de Celdas
Atributo	Descripción
colspan	Expande la celda horizontalmente a varias columnas.
rowspan	Expande la celda verticalmente a varias filas.
align	Alineación horizontal: left, center, right.
valign	Alineación vertical: top, middle, bottom.

Ejemplo de colspan y rowspan:
html
Copiar código
<table border="1">
  <tr>
    <th>Nombre</th>
    <th colspan="2">Datos</th>
  </tr>
  <tr>
    <td>Juan</td>
    <td>25</td>
    <td>Madrid</td>
  </tr>
  <tr>
    <td rowspan="2">Ana</td>
    <td>30</td>
    <td>Barcelona</td>
  </tr>
  <tr>
    <td>32</td>
    <td>Valencia</td>
  </tr>
</table>
5. Estilizando Tablas con CSS
Evita atributos obsoletos como border o bgcolor. En HTML5, se recomienda usar CSS:

html
Copiar código
<table class="mi-tabla">
  <thead>
    <tr>
      <th>Producto</th>
      <th>Precio</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Monitor</td>
      <td>200€</td>
    </tr>
  </tbody>
</table>

<style>
.mi-tabla {
  border-collapse: collapse;
  width: 100%;
}
.mi-tabla th, .mi-tabla td {
  border: 1px solid #333;
  padding: 8px;
  text-align: left;
}
.mi-tabla th {
  background-color: #f4f4f4;
}
</style>
6. Buenas Prácticas
Usar <thead>, <tbody> y <tfoot> para semántica y accesibilidad.

Evitar atributos obsoletos (align, bgcolor, width).

Usar <caption> para contextualizar la tabla.

Evitar tablas anidadas excesivas.

Usar <th> siempre para cabeceras.

7. Diferencias entre HTML4 y HTML5
Característica	HTML4	HTML5
Semántica	Limitada, muchos atributos obsoletos	<thead>, <tbody>, <tfoot>, <caption> recomendados
Estilos	Atributos (border, bgcolor)	CSS para todos los estilos
Accesibilidad	Básica	Mejor soporte semántico y accesibilidad
Anidamiento	Permitido	Permitido
Validación	Estricta en etiquetas y atributos	Flexible con semántica mejorada

# Glosario de Términos Clave

| Término     | Definición                                                                 |
|------------|----------------------------------------------------------------------------|
| `<table>`  | La etiqueta principal que engloba todos los elementos de una tabla en HTML. |
| `<tbody>`  | Etiqueta utilizada para agrupar el contenido principal o el cuerpo de una tabla. |
| `<caption>`| Etiqueta que define un título o leyenda para la tabla. Se coloca dentro de `<table>`. |
| `<td>`     | (Celda de datos) Define una celda estándar en una tabla. Contiene información. |
| `<tfoot>`  | (Pie de tabla) Etiqueta utilizada para agrupar el contenido del pie de una tabla. |
| `<th>`     | (Celda de cabecera) Define una celda especial de encabezado. Por defecto, su contenido aparece en negrita. |
| `<tr>`     | (Fila de tabla) Define una fila dentro de una tabla. Contiene una o más celdas (`<td>` o `<th>`). |
| border     | Atributo de `<table>` que especifica el grosor del borde exterior de la tabla. |
| cellpadding | Atributo que define el espacio en píxeles entre el contenido de una celda y su borde. |
| cellspacing | Atributo que define la distancia o el espacio existente entre las celdas de una tabla. |
| colspan    | Atributo que se aplica a una celda (`<td>` o `<th>`) para que se expanda horizontalmente a lo largo de varias columnas. |
| rowspan    | Atributo que se aplica a una celda (`<td>` o `<th>`) para que se expanda verticalmente a lo largo de varias filas. |
| rules      | Atributo de `<table>` que especifica cuáles de los bordes internos deben ser visibles (horizontales, verticales, todos). |
| width      | Atributo que define la anchura de la tabla. Su uso no se recomienda; se prefiere CSS. |


Aunque esta técnica ofrece flexibilidad, debe usarse con moderación para mantener el código claro y fácil de mantener.
