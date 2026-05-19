# Consulta Judicial demo

Demo estática para consulta documental del Boletín Judicial del Poder Judicial de la Ciudad de México.

## Qué cambió en esta versión

Esta versión ya no usa datos inventados ni registros simulados. El archivo `data/boletin-index.js` fue generado directamente desde el PDF local:

`assets/boletines/Boletin_Judicial_PJCDMX_2022-03-31.pdf`

Cada búsqueda opera sobre el texto extraído de las 400 páginas del PDF. Los resultados muestran página del PDF, sección inferida, líneas coincidentes, referencias tipo expediente detectadas y vínculo al PDF con `#page=`.

## Probar localmente

```bash
cd consulta_judicial_real
python -m http.server 8000
```

Abrir:

```text
http://localhost:8000
```

Credenciales demo:

```text
admin / admin
```

También puede abrir `index.html` directamente, porque el índice está empaquetado como JavaScript local y no depende de `fetch()`. Aun así, para una prueba realista se recomienda servidor local.

## Publicar en GitHub Pages

1. Crear un repositorio nuevo.
2. Subir todos los archivos y carpetas de este proyecto.
3. Ir a Settings → Pages.
4. En “Build and deployment”, elegir “Deploy from a branch”.
5. Seleccionar branch `main` y carpeta `/root`.
6. Guardar y esperar la URL pública de GitHub Pages.

## Archivos principales

- `index.html`: login demo.
- `home.html`: panel principal.
- `consulta-automatica.html`: búsqueda global.
- `boletin-electronico.html`: visor del PDF.
- `busquedas-individuales.html`: búsqueda por persona, expediente o palabra clave.
- `historial-expedientes.html`: línea de tiempo por expediente.
- `busqueda-demandados.html`: coincidencias documentales con advertencia legal.
- `reporte-ejecutivo.html`: métricas y bitácora.
- `admin-demo.html`: administración visual.
- `actualizacion-diaria.html`: roadmap de versión 2.
- `data/boletin-index.js`: índice textual generado desde el PDF real.
- `assets/boletines/Boletin_Judicial_PJCDMX_2022-03-31.pdf`: PDF fuente.

## Limitaciones

- No hay backend real.
- No hay autenticación productiva.
- No hay OCR avanzado para texto embebido como imagen si el PDF no lo expone.
- La detección de expedientes es heurística; la búsqueda principal es literal sobre el texto extraído.
- La sección se infiere a partir del índice del boletín y la paginación estimada.

