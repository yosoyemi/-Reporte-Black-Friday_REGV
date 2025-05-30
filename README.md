Black Friday – GlowBeauty
Script de análisis de ventas a partir de archivo CSV sin librerías externas

“Sólo podrás tomar decisiones acertadas si sabes cómo analizar e interpretar los datos.”
— Avinash Kaushik

Objetivo
Diseñar y programar un script en Python que lea un archivo de texto plano con las ventas de Black Friday, sin usar pandas, csv ni numpy, para responder:

¿Cuántos registros pertenecen a la categoría Beauty?

¿Cuál es el promedio global del campo Total Amount?

El resultado es un reporte de consola que sintetiza estos indicadores y facilita la toma de decisiones estratégicas de GlowBeauty.

Dataset
Nombre: retail_sales_dataset.csv

Ubicación en Colab:
/content/0.y2nvtoqglsp0.1ydeken3zmvretail_sales_dataset.csv

Estructura: 9 columnas delimitadas por comas; la cabecera ocupa la primera línea.

#	Columna	Ejemplo
0	Invoice ID	46035238
1	Date	2023-11-24
2	Customer ID	C-01234
3	Gender	F
4	Age	29
5	Product Category	Beauty
6	Product ID	B-778
7	Quantity	3
8	Total Amount	145.99

Restricciones técnicas
Librería estándar únicamente.

Lectura “manual” del CSV mediante open, split(',') y validaciones propias.

Cumplimiento de PEP 8 y tipado estático (anotaciones).

Arquitectura del código
El notebook se organiza en cuatro celdas de Python claramente separadas:

Celda	Contenido principal	Propósito
1	Constantes, imports, validación de ruta	Configuración e invariantes
2	iter_rows & parse_sales	Lógica de lectura y cálculo
3	print_report	Presentación del resultado
4	Bloque if __name__ == "__main__":	Punto de entrada ejecutable

Flujo de ejecución
Validación: se comprueba que el archivo exista en la ruta indicada.

Iteración: se descarta la cabecera y se procesan líneas no vacías.

Extracción de campos:

Índice 5 → Product Category

Índice 8 → Total Amount → float

Cómputo:

Contador de registros totales.

Contador específico para categoría “beauty” (case-insensitive).

Suma acumulada de Total Amount.

Promedio: división de la suma entre el total de filas válidas.

Reporte: impresión formateada con numeración y separadores.

Uso
bash
Copiar
Editar
# 1) Subir el CSV a la ruta indicada (o ajustar CSV_PATH).
# 2) Ejecutar las cuatro celdas en orden.
# 3) Leer la salida en la consola de Colab.
Ejemplo de salida:

markdown
Copiar
Editar
----------------------------------------------
  Reporte Black Friday – GlowBeauty
----------------------------------------------
Número de registros analizados ..........    1000
Registros en la categoría «Beauty» ......     307
Promedio global de «Total Amount» .... $456.00
----------------------------------------------
(Los valores variarán según el dataset que se suministre.)
