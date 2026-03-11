# 📚 Proyecto: Sistema ETL de Catálogo de Libros (Scraping + API + SQL)

Este proyecto implementa un proceso completo de **Extracción, Transformación y Carga (ETL)**. El sistema recolecta información de un sitio web, la enriquece consultando una API internacional y la almacena en una base de datos relacional normalizada.



---

## 📖 Descripción

El programa automatiza la recopilación de un catálogo de **1,000 libros**. El flujo de trabajo no se limita a la captura de datos, sino que realiza un procesamiento integral:

* **Limpieza:** Conversión de precios y ratings de texto a formato numérico.
* **Enriquecimiento:** Consulta de metadatos adicionales mediante la API de Google Books.
* **Persistencia:** Almacenamiento en un modelo de base de datos relacional profesional.

---

## 🛠️ Tecnologías y Conceptos Implementados

* **Web Scraping Avanzado:** Uso de `requests` y `BeautifulSoup` para navegar por categorías y gestionar la paginación dinámica del sitio.
* **Consumo de APIs REST:** Integración con la **API de Google Books** para obtener autores y metadatos no presentes en la fuente original.
* **Procesamiento de Datos con Pandas:** Transformación de datos "sucios" (limpieza de símbolos de moneda y casting de tipos) para asegurar la calidad de la información.
* **SQL & Bases de Datos:** Diseño de un esquema relacional con 4 tablas (**Categorías, Libros, Autores, Libro_Autor**) aplicando Normalización y relaciones Muchos a Muchos.



---

## 🧠 Desafíos Técnicos Superados

### 1. Enriquecimiento de Datos y Manejo de APIs
El sitio original carecía de información sobre los autores. Implementé una lógica de búsqueda que consulta cada título en la nube, asocia el autor correcto y gestiona excepciones para registros con información incompleta.

### 2. Normalización de Base de Datos (3NF)
En lugar de utilizar una tabla plana, diseñé un esquema relacional utilizando **FOREIGN KEYS** para optimizar el almacenamiento y garantizar la integridad referencial de los datos.

### 3. Eficiencia y Ética de Scraping
* **Políticas de Cortesía:** Implementación de pausas (`time.sleep`) para evitar bloqueos por parte del servidor.
* **Caché Local:** Uso de respaldos en formato **JSON** para evitar consultas repetitivas a la API, optimizando el tiempo de ejecución y respetando las cuotas de uso.

### 4. Análisis mediante Consultas SQL
Desarrollo de scripts de reporte automáticos directamente desde la base de datos para obtener:
* Promedio de precios por categoría.
* Identificación de libros por rangos de precio competitivos.
* Estadísticas de autores con mayor presencia en el catálogo.

---

## 🚀 Cómo Ejecutarlo

1.  **Instalar Dependencias:**
    ```bash
    pip install requests beautifulsoup4 pandas sqlalchemy
    ```

2.  **Ejecutar el Pipeline:**
    ```bash
    python "nombredelarchivo".py
    ```

3.  **Consultar Resultados:**
    El sistema generará una base de datos SQL que puedes explorar con cualquier cliente (como SQLite Browser) para ver el catálogo final normalizado.
