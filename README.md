📚 Proyecto 6: Sistema ETL de Catálogo de Libros (Scraping + API + SQL)

Este proyecto implementa un proceso completo de Extracción, Transformación y Carga (ETL). El sistema recolecta información de un sitio web, la enriquece consultando una API internacional y la almacena en una base de datos relacional normalizada.

📖 Descripción

El programa automatiza la recopilación de un catálogo de 1,000 libros. No se limita a copiar los datos; limpia los precios, convierte ratings de texto a números, busca a los autores reales en la API de Google Books y organiza todo en un modelo de base de datos profesional.

🛠️ Tecnologías y Conceptos Implementados

Web Scraping Avanzado: Uso de requests y BeautifulSoup para navegar por categorías y gestionar la paginación dinámica del sitio.

Consumo de APIs REST: Integración con la API de Google Books para obtener metadatos (autores) que no estaban presentes en el sitio original.

Procesamiento de Datos con Pandas: Transformación de datos "sucios" (strings con símbolos de moneda) en tipos de datos numéricos listos para análisis.

SQL & Bases de Datos: Diseño de un esquema con 4 tablas (Categorias, Libros, Autores, Libro_Autor) aplicando Normalización y relaciones Muchos a Muchos.

🧠 Desafíos Técnicos Superados

Enriquecimiento de Datos: El sitio original no tenía los autores. Implementé una lógica que busca cada título en la nube y asocia el autor correcto, manejando excepciones para "Autores desconocidos".

Normalización de Base de Datos: En lugar de una tabla plana, diseñé un esquema relacional que utiliza FOREIGN KEYS para optimizar el almacenamiento y la integridad de los datos.

Eficiencia y Respeto al Servidor: Implementación de pausas (time.sleep) para evitar bloqueos por parte del servidor y uso de respaldos en formato JSON para evitar consultas repetitivas a la API.

Análisis mediante Consultas SQL: Creación de reportes automáticos (libros baratos, promedio de precios por categoría) directamente desde la base de datos usando sintaxis SQL.
