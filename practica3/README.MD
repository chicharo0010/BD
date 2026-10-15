Práctica 3: Transformación del modelo entidad-relación extendido al modelo relacional

Instituto Politécnico Nacional - ESCOM
Ingeniería en Sistemas Computacionales (Plan 2020)
Unidad de aprendizaje: Bases de Datos


Integrantes del equipo y enlaces a los Issues:

- César (chicharo0010): https://github.com/chicharo0010/BD/issues/1
- saul  (ZArias17): https://github.com/chicharo0010/BD/issues/2


Información de los proyectos y gestor utilizado:

- Proyecto propio: Sistema de gestión para un taller mecánico (base de datos: taller_propio_p3).
- Proyecto asignado: Sistema web de taller mecánico y refacciones (base de datos: merch, archivo mech.sql).
- Sistema gestor de base de datos: MySQL 8.0.40 levantado en contenedor con Docker Compose.
- Herramientas de apoyo: dbdiagram.io y DBeaver.


Cambios y correcciones al modelo EER de la Práctica 2:

Antes de pasar el modelo a tablas, hicimos estas correcciones sobre el diagrama EER de la práctica pasada:
1. En la jerarquía de Persona (Cliente y Mecánico) definimos que es total y solapada, porque cualquier registro en esa entidad debe ser cliente o mecánico, y además un mecánico del taller también puede meter su propio carro como cliente.
2. En la jerarquía de Pieza (Motor, Suspensión/Frenos y Químico) la dejamos como parcial y disjunta, ya que una refacción no puede ser de dos subtipos a la vez y existen piezas generales que no entran en esas tres categorías.
3. Separamos los atributos compuestos de dirección y nombre completo en columnas simples, dejamos el teléfono como atributo multivaluado en su propia tabla y el costo total de la orden quedó como atributo derivado para que no se desactualice.


Organización de las carpetas:

En la carpeta proyecto-propio están los PDFs del inventario EER, el proceso de transformación aplicando las 9 reglas, el diccionario de datos, la imagen del diagrama relacional y la carpeta sql con el esquema y las pruebas de los INSERT que el gestor rechaza.

En la carpeta proyecto-asignado están los PDFs con el análisis del esquema de mech.sql, la tabla comparativa entre el modelo EER y el relacional, y la carpeta cambios con el script SQL y el PDF individual de cada integrante.

En la carpeta evidencias están las capturas de pantalla de la creación de las tablas, los errores de las restricciones probadas y la ejecución de los cambios individuales.


Declaración de uso de IA generativa:

Para esta práctica nos apoyamos en Google Gemini para revisar la sintaxis de las restricciones CHECK y FOREIGN KEY en MySQL 8.0 y para dar formato a las tablas de los documentos. Las pruebas y la ejecución de los scripts se hicieron directamente en nuestros contenedores de Docker.


Bibliografía:

Elmasri, R., & Navathe, S. B. (2016). Fundamentals of database systems (7th ed.). Pearson.

Oracle Corporation. (2025). MySQL 8.0 reference manual: Data definition statements. https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html

Silberschatz, A., Korth, H. F., & Sudarshan, S. (2019). Database system concepts (7th ed.). McGraw-Hill Education.